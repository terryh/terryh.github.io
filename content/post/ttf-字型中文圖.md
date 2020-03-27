+++
title = "TTF 字型中文圖"
date = 2008-01-09T06:49:00Z
updated = 2008-01-31T22:55:25Z
tags = ["Python"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

有時候想畫一下kuso 的圖片，卡片，或是名片的應用，可以用的上<br />，拿來作 <a href="http://en.wikipedia.org/wiki/Captcha">Captcha</a> 的功能時，也可以用上，當然不用一定要中文的，在加上一些 PIL 的濾鏡特效，及背景即可，這裡用的範例是firefly前輩的美美中文字型<br /><code><br />#!/usr/bin/env python<br /># -*- encoding: utf-8 -*-<br /><br />import Image, ImageDraw, ImageFont<br />font = ImageFont.truetype('/usr/share/fonts/truetype/fireflysung.ttf',36)<br />im = Image.new( "RGB", (200,200))<br />draw = ImageDraw.Draw( im )<br />draw.text( (40,40), unicode("寶貝"), font=font )<br />im.save("test.jpeg")<br /></code><br />請參考<br /><a href="http://tech.seety.org/python/python_imaging.html">http://tech.seety.org/python/python_imaging.html</a>
