tschaume.github.io
==================

pushing short commit messages to the jekyll _data folder from all my git
repositories spread over https://github.com/tschaume,
http://gitlab.the-huck.com and http://cgit.the-huck.com
=> Generate a feed and possibly some interesting git stats


in local work-dir of each tracked repo with remote on github, gitlab or cgit:  
-> have public "global_gitfeed_data" as submodule (= tschaume.github.io/_data)  
   all tracked repos need access to it  
-> init a repo-logfile in submodule when cloned  
-> on repo post-commit:  
   update(regenerate?) repo-logfile and commit changes in submodule  
-> on repo post-push:  
   * regenerate commits.yml in submodule  
   * commit and push changes to submodule remote  

in tschaume.github.io: add submodule to track master branch  
$ git submodule add -b master [URL to Git repo]  
$ git submodule update --remote  

TODO: link <sha1> to commit (possibly protected)  
TODO: include --shortstat in commit log?  
TODO: analysis (#repos, lines, files, punchcard, ...)  
