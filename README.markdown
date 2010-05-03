home-base
=========

A starting point for a Unix-like home directory structure which can be shared
across multiple machines.

*Note:* this is currently in draft, and likely to be revised heavily over the
next couple of weeks. Use it as a basis for your home directory only if you
like having broken things to fix.


Philosophy
----------
There are two basic tenets I abide by when I structure my home directory.

1. _Mimic the long-established Unix file system hierarchy._

  I do not like hidden (dot) files. System-wide configuration settings are not
  hidden like this (they are stored in /etc). So why should my configuration
  files be hidden? 
  
  Wherever possible I keep configuration files in ~/etc. If the location of a
  configuration file is hard-coded in a program, I keep as short a stub file
  as I can get away with there, and source the settings from elsewhere. If the
  configuration format doesn't allow for other files to be included, I create
  the dotfile as a symlink to the real settings file.
  
  Scripts are kept in ~/bin. Library code is kept in ~/lib. Data files in
  ~/var. Documentation and example code in ~/share.
  
2. _Keep separate settings in separate files._

  Rather than have one huge file full of aliases, environment variables and
  functions in my .bashrc, making it hard to find and update things, I keep
  related things together and unrelated things apart by breaking them down
  into separate files.


Rationale
---------
I like to keep the more useful parts of my Unix home directory under revision
control. I exposed this as the [homedir][homedir] project on github, which got
a fair amount of attention and several forks as people used it as a basis for
their own home directory.

The problem with that is that your settings, aliases and so forth are very
personal. Forking my specific settings is not likely to be that great a 
starting point for many people. In all likelihood, what they are actually
forking it for is the structure I impose upon my bash startup.

So I thought I would break this out into its own project which can be more 
easily forked as a starting point without then needing to delete all of my
stuff.

-- Mark Norman Francis.

[homedir]:http://github.com/norm/homedir/
