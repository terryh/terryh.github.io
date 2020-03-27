+++
title = "Multiple Site"
date = 2019-12-02T10:14:47+08:00
tags = ["golang"]
+++

自從有了 [Let's Encrypt](https://letsencrypt.org/)  以後，網站的 ssl 憑證都是用他們家

免費的憑証，原本的設定都是把 nginx 擺在前面，利用 virtual host 

的方式，可以對應到多個站點，用 [acme.sh](https://github.com/Neilpang/acme.sh)

command line 的工具去管理，多個站點的 ssl 憑証更新，時間久了，還是

覺得麻煩，後來乾脆，直接只跑一個 golang 的 server 同時 host 多個站點

<!--more-->

這一個範例選用的是 [gorilla mux](https://github.com/gorilla/mux)

單純就是他已經有 Host 的功能可以直接用

還有很多其他的選擇，一般來說都會比較快，像是介面同 

golang standard library 的 [go-zoo/bone](https://github.com/go-zoo/bone)

或是 [go-chi](https://github.com/go-chi/chi) 都是小而美的選擇，盡量如果標準的

library 介面的能解決，就不需要用 framework 來解，很容易陷入學習 

framework 的寫法，而不是語言本身的寫作方式

寫起來大概像是這樣(實際請還是自己看一下文件，程式只有大概)

<pre>
<code class="language-go">

    import (
      "crypto/tls"
      "net/http"
      "github.com/gorilla/mux"
      "golang.org/x/crypto/acme/autocert"
    )

    func Index(w http.ResponseWriter, r *http.Request) {
        fmt.Fprintf(w, "Hello World")
    }

    func main(){
       
        r := mux.NewRouter()
        blogRouter := r.Host("blog.yours.net").Subrouter()
        appRouter := r.Host("coolapp.net").Subrouter()

        blogRouter.PathPrefix("/").Handler(http.FileServer(http.Dir("./public")))
        appRouter.HandleFunc("/", Index).Methods("GET")

        certManager := autocert.Manager{
                Prompt:     autocert.AcceptTOS,
                HostPolicy: autocert.HostWhitelist("blog.yours.net", "coolapp.net"),
                Cache:      autocert.DirCache("certs"), //folder for storing certificates
        }

        server := &http.Server{
                Addr:    ":443",
                Handler: r,
                TLSConfig: &tls.Config{
                        GetCertificate: certManager.GetCertificate,
                },
        }

        go func() {
                log.Printf("Starting HTTPS service on :443 ...")
                server.ListenAndServeTLS("", "") //key and cert are comming from Let's Encrypt
        }()

        log.Printf("Starting HTTP service on :80")
        http.ListenAndServe(":80", certManager.HTTPHandler(r))

    }

</code>
</pre>
