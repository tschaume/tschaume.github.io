tschaume.github.io
==================

Idea
----

pushing short commit messages to the jekyll _data folder from all my git
repositories => Generate a feed and possibly some interesting git stats

Details
-------

on post-commit in each tracked repo (see *_data/post-commit*, symlink in repo's .git/hooks):  

- regenerate repo-logfile, regenerate commits.yml
- commit and push changes back
 
TODO
----

- don't regenerate log-file on each commit, only append resp. commit
- link <sha1> to commit (possibly protected)  
- include --shortstat in commit log?  
- analysis (#repos, lines, files, punchcard, ...)  
- currently only supports all tracked repos being on the same machine

Requirements
------------

Git > 1.8.2
