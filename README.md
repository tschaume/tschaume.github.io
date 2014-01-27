tschaume.github.io
==================

Idea
----

pushing short commit messages to the jekyll _data folder from all my git
repositories spread over https://github.com/tschaume,
http://gitlab.the-huck.com and http://cgit.the-huck.com
=> Generate a feed and possibly some interesting git stats

Details
-------

in local work-dir of each tracked repo with remote on github, gitlab or cgit
(includes tschaume.github.io):  

- import public *global_gitfeed_data* as submodule in *_data*  
  (all tracked repos need push access to it)  
  `$ git submodule add -b master https://github.com/tschaume/global_gitfeed_data.git _data`
  `$ git submodule update --remote` 
- on repo post-commit (see *_data/post-commit*, mv to .git/hooks):  
  regenerate repo-logfile, regenerate commits.yml, commit (and push submodule changes)
 
TODO
----

- don't regenerate log-file on each commit, only append resp. commit
- link <sha1> to commit (possibly protected)  
- include --shortstat in commit log?  
- analysis (#repos, lines, files, punchcard, ...)  

Requirements
------------

Git > 1.8.2
