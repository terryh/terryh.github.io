+++
title = "groupcache"
date = 2014-09-16T07:14:00Z
updated = 2014-09-16T18:04:40Z
tags = ["Golang"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

這一個 golang 裡面非常帥氣的 library ，作者是原 memcached 的作者之一，主要就是讓 cache 機制再簡化<br /><br />集群的部署能力也還不錯，完全不用再管 server instance ，我對這種，以簡單為名的 library 最沒有招架能力了<br /><br /><a href="https://github.com/golang/groupcache">https://github.com/golang/groupcache</a><br /><br />使用上也是非常的帥氣，可以參考 OSCON 的簡報<br /><br /><a href="http://talks.golang.org/2013/oscon-dl.slide#1">http://talks.golang.org/2013/oscon-dl.slide#1</a><br /><br />詳細的使用上可以參考， source code ，或是 test case，還有很多種用法 <br /><br />以下是我用的範例，您可以用在很多地方，像是外部 url fetch ，或是很重的 query 或是檔案 IO 之類的<br />就是平常，你 cache 怎麼用，就可以怎麼用，cache 只有支援 拿，和寫，<br /><br />以下的例子用這樣拿資料，我的 cache key 大概到小時，就用自己算每小時不同的 key<br />FileInfoCache.Get(nil, cacheFileInfo, groupcache.AllocatingByteSliceSink(&data))<br /><br />另外，FileInfoFetch 就是另外一個做很多 disk IO 的工作<br />dest.SetBytes(FileInfoFetch(path))<br /><br /><br /><pre><code class="language-markup"><br />// Example for groupcache<br />// snip from my code<br /><br />var (<br />        FileInfoCache  *groupcache.Group<br />)<br /><br />func init(){<br /><br />        //////////////////////////////////////////<br />        // init book query cache<br />        //cacheAddr := "127.0.0.1:55555"<br />        //peers := groupcache.NewHTTPPool("http://" + cacheAddr)<br />        // the cache key is compose with timestamp hour<br />        // 2006-01-02 15!!!url<br />        getter := groupcache.GetterFunc(func(ctx groupcache.Context, key string, dest groupcache.Sink) error {<br />                keys := strings.SplitN(key, "!!!", 2)<br />                //ts := keys[0]<br />                path := keys[1]<br />                dest.SetBytes(FileInfoFetch(path))<br />                return nil<br />        })<br /><br /><br />        if FileInfoCache == nil {<br />                // cache not been init<br />                // allocate 64 MB memory for groupcache<br />                FileInfoCache = groupcache.NewGroup("FileInfo", 64<<20, getter)<br />        }<br />        <br /><br />}<br /><br /><br /></code></pre><br /><br />你看，帥不帥氣，完全不需要另外跑，cache server daemon ，如果要組成 cluster 就直接在程式裡用 HTTPPool 的服務<br />
