+++
title = "expressjs conditional CSRF"
date = 2013-08-21T19:46:00Z
updated = 2013-08-21T20:07:32Z
tags = ["創業", "Express", "Node.js"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

現在一般基本的網路服務，為了安全性，會加上 CSRF 的保護，如果<br /><br />用  ajax 的方式傳資料，一般可以跳過，或是，加在 ajax 的 header 裏面<br /><br /><br />在 Django 下面的話，如果不檢查的話，會加個 decorator @csrf_exempt<br /><br />在 expressjs 下面，加 ajax header 是可行的，不過懶一點，目前 API 路徑的<br />請求，先跳過，以下筆記<br /><br /><pre><code class="language-javascript"><br /><br /> /**<br /> * Module dependencies.<br /> */<br /><br />var express = require('express')<br />  , csrf = express.csrf()<br />  , fs = require('fs')<br />  , mongoStore = require('connect-mongo')(express)<br />  , flash = require('connect-flash')<br />  , helpers = require('view-helpers')<br />  , mongoose = require('mongoose')<br />  , http = require('http')<br />  , path = require('path')<br />  , i18n = require('i18n');<br /><br /><br />  // I olny cut the block of csrf setup<br /><br />  // adds CSRF support<br />  if (process.env.NODE_ENV !== 'test') {<br /><br />    // conditinal CSRF<br />    <br />    var conditionalCSRF = function(req, res, next){<br />      <br />      // bypass urlpath start with api and moreurl<br /><br />      if (! /^\/(api|moreurl)/.test(req.path)){<br />        csrf(req, res, next);<br />      } else {<br />        next();<br />      }<br />    }<br />    //app.use(express.csrf());<br />    app.use(conditionalCSRF);<br />  }<br /><br />  // This could be moved to view-helpers :-)<br />  app.use(function(req, res, next){<br />    res.locals.csrf_token = req.session._csrf<br />    next()<br />  })<br /><br /></code><br /></pre>參考<br /><a href="http://stackoverflow.com/questions/13516898/disable-csrf-validation-for-some-requests-on-express">http://stackoverflow.com/questions/13516898/disable-csrf-validation-for-some-requests-on-express</a><br /><br /><a href="http://stackoverflow.com/questions/11200068/how-to-implement-csrf-protection-in-ajax-calls-using-express-js-looking-for-com">http://stackoverflow.com/questions/11200068/how-to-implement-csrf-protection-in-ajax-calls-using-express-js-looking-for-com</a>
