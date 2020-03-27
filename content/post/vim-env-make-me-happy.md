+++
title = "Vim env make me happy"
date = 2009-12-27T00:46:00Z
updated = 2010-02-24T18:43:47Z
tags = ["Debian", "Python", "Vim"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

自己的小筆記<br /><br /><a href="http://blog.dispatched.ch/2009/05/24/vim-as-python-ide/">http://blog.dispatched.ch/2009/05/24/vim-as-python-ide/</a><br /><br /><a href="http://blog.tplus1.com/index.php/2007/08/29/how-to-use-vimdiff-as-the-subversion-diff-tool/">http://blog.tplus1.com/index.php/2007/08/29/how-to-use-vimdiff-as-the-subversion-diff-tool/</a><br /><br />vimdiff<br /><a href="http://www.ibm.com/developerworks/cn/linux/l-vimdiff/index.html">http://www.ibm.com/developerworks/cn/linux/l-vimdiff/index.html</a><br /><br /><a href="http://www.vim.org/scripts/script.php?script_id=1542">http://www.vim.org/scripts/script.php?script_id=1542</a> put this file under  ~/.vim/plugin/  C-x  C-o get the tips<br /><br />taglist (vim-scripts debain package)<br /><br />minibufexplorer (vim-scripts debain package)<br /><br /><br />under debian require package<br /><br />vim vim-lesstif vim-nox vim-scripts vim-gtk vim-gnome exuberant-ctags<br /><br />simple .vimrc<br /><br /><code><br />set tabstop=4 <br />set shiftwidth=4<br />set softtabstop=4<br />set autoindent<br />set ignorecase<br />set nowrapscan<br />set et<br />set number<br />set noswapfile<br /><br />nnoremap &lt;F8&gt; :Tlist&lt;CR&gt;<br />nnoremap &lt;F9&gt; &lt;ESC&gt; zi<br /><br /><br />colors delek<br /><br />syntax on<br />filetype on<br />filetype plugin on<br />au Syntax python set omnifunc=pythoncomplete#Complete<br />au Syntax python set completefunc=pythoncomplete#Complete<br /><br />setglobal fileencoding=utf8<br />set fileencoding=utf8<br />set termencoding=utf8<br />set fileencodings=utf-8,big5,latin1<br />set guifont=Arial\ 16<br />set vb<br /><br />map &lt;ESC&gt;&lt;C-Left&gt; :tabprev&lt;CR&gt;<br />map &lt;ESC&gt;&lt;C-Right&gt; :tabnext&lt;CR&gt;<br />map &lt;C-t&gt;n &lt;ESC&gt;:tabnext&lt;CR&gt;<br />map &lt;C-t&gt;p &lt;ESC&gt;:tabprev&lt;CR&gt;<br />map &lt;C-t&gt;t &lt;ESC&gt;:tabnew&lt;CR&gt;&lt;ESC&gt;:e<br />map &lt;C-b&gt;b &lt;ESC&gt;:tabclose&lt;CR&gt;<br /><br /><br /></code>
