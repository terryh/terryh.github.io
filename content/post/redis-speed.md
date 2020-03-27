+++
title = "Redis Speed"
date = 2010-06-08T22:02:00Z
updated = 2010-06-08T22:29:05Z
tags = ["Python", "Redis"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<a href="http://www.digitaldragoon.com/blog/testing-speed-redis-py/">http://www.digitaldragoon.com/blog/testing-speed-redis-py/</a><br /><br />have pget and pset inside, I change to this<br /><br /><code><br />import cPickle as pickle<br />import zlib<br />import new<br /><br />####################################<br /># gzip header<br />gzip_header = zlib.compress('')[:2]<br />####################################<br />#       CUSTOM COMMANDS for Redis<br />####################################<br /><br />def _pset(self, name, object, compress=False):<br />        """ pickle set for redis client, with compress flag<br />        """<br />        pobj = pickle.dumps(object, pickle.HIGHEST_PROTOCOL)<br />        if compress:<br />                pobj = zlib.compress(pobj)<br /><br />        self.set(name, pobj)<br />        <br />def _pget(self, name):<br />        """ pickle get for redis client, automatic to check compress flag<br />        """<br />        pobj = self.get(name)<br />        if pobj is None: # No value for this key, let's go home  :-(<br />                return None<br />        else:<br />                if pobj[:2] == gzip_header:<br />                        # it compressed data<br />                        pobj = zlib.decompress(pobj)<br />                <br />                load_object= pickle.loads(pobj)<br />                return load_object<br /><br />redis.Redis.pset = new.instancemethod(_pset, None, redis.Redis)<br />redis.Redis.pget = new.instancemethod(_pget, None, redis.Redis)<br /><br /></code>
