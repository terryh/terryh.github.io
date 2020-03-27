+++
title = "ORM and SQL"
date = 2007-06-04T21:39:00Z
updated = 2008-01-31T23:05:15Z
tags = ["wxPython", "Python", "Django"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

在有 Database 的應用裡，寫多了 SQL（Structure Query Language） 會覺得他是一種累贅，讓你的邏輯不斷的，在程式語言，及 SQL 之間轉換，所以後來，就有了，很流行的 Database ORM (Object Relational Mapper) 來幫助我們開發，一來，可以用相同的邏輯思考方式，用物件的方式，去對應資料庫的元件，一來，可以有資料庫的抽象層，對一個系統的開發有很大的助益，但是，如果，要寫的 code ，比一般的 SQL 還要複雜，還要隴長，你該怎麼作呢？<br /><br />寫回去 SQL 嗎？還是就去適應這樣的物件對應方式？<br /><br />這也許沒有一定的答案，不過，我來分享一下，我用 **Django ORM** 到目前所遇到的問題，和解決的方法，所以，裡面有一些是個人好惡的選擇<br /><br />* 現在Unicode 的branch 還沒有 merge 到 truck 裡，如果用 wxPython unicode 的版本，自己要處理，string to unicode 及 unicode to string 的問題<br /><br />* ManytoManyField 的欄位，Q object OR 沒有辦法套用，在 djangosnippets 有解決辦法，連結是 http://www.djangosnippets.org/tags/m2m/ 不過還是希望有官方的<br /><br />* 目前如果是用 truk 的 Django， 用 groupu_by() 只能在對應該物件的 database table 裡分 group，無法使用別的欄位作 group_by 的條件，在別的 branch 有解決了，可是基於，愛乾淨不要混用，太多 branch 的原則，我是用 extra 的解法，算是走 SQL 的回頭路，不過， "GROUP BY" 在 SQL 也是標準的語法，不至於破壞了資料庫的抽象層，不過，如果有用 GROUP BY 的話，不可以混用 filter 的功能，不然，產生的 SQL 語法不對，我們要決定所有的 where 條件，第一個例子，是有 where 的 group by，第二個，是沒有 whehe 可是要強加 grouop by 在不同欄位，這樣就還可以在 DB 上只用一個 query，在 Django 上還是傳回 QuerySet 的作法，不過，這一個 QuerySet 不可以再用 filter 的方式，因為這樣會讓 group by 及 where 的位置錯了<br /><br />範例1::<br /><code><br />qset = Stock.objects.extra(select={'totalsum':'sum(volume)'},where=["customer_id='%s' group by product_id" %(customerid)])<br /></code><br /><br />範例2::<br /><code><br />qset = Stock.objects.extra(select={'totalsum':'sum(volume)'},where=["1 group by product_id"])<br /></code><br />以上，是目前，我遇到的一些限制，及解決辦法，也許對您有參考的價值，在 Desktop 的應用程式上， 如果，還有更複雜的的需求， SQLAlchemy 應該是不錯的選擇<br /><br />.. -*- mode: rst -*-
