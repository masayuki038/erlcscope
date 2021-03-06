Introduction
============

`erlcscope` builds a cscope compatible database for erlang files. The database can be used with any
program which supports cscope along with the standard `cscope -d ` command.


Installation
============

Requires Erlang and `escript` installed.

```
git clone https://github.com/syed/erlcscope.git
cd erlcscope
```
By default erlcscope will install the binary in `/usr/local/bin`. If you want to change the default
location edit the `DEST_BIN` variable in the Makefile. 

erlcscope uses `rebar` present in its directory for compilation. If you want to use a different
version of `rebar` or add some extra paramaters, edit the `REBAR` variable in the Makefile

After making the necessary changes, compile and install by 

```
make clean 
make 
make install
```


Usage
=====

```
cd /path/to/code
erlcscope .
```

by default erlcscope will look for a file named `cscope.files` which contains a list of all 
the source files that need to be processed. If no such file is present, it recursively scans
the directory for erlang files and builds the database. It also stores the files found in
`cscope.files`.

Right now erlcscope supports lookup of atoms,variables and functions. The main advantage of cscope
over ctags is that it can also lookup where a function is called from instead of just the function 
definition.

If you are using vim and want to setup cscope, [this](http://cscope.sourceforge.net/cscope_vim_tutorial.html) tutorial details the process very nicely.
[This](http://emacswiki.org/emacs/CScopeAndEmacs) is the link for emacs users.


Screenshots
===========

With `cscope -d`
---------------

![alt text][erlcscope1]


With vim
--------

![alt text][erlcscope2]


[erlcscope1]: http://dl.dropbox.com/u/43993452/imgs/erlcscope1.png "erlcscope with cscope -d"
[erlcscope2]: http://dl.dropbox.com/u/43993452/imgs/erlcscope2.png "erlcscope with vim"
