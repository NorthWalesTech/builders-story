Tips and Tools
==============

# Tools

* TortoiseGit: Great for browsing through history (in Windows). 
  http://code.google.com/p/tortoisegit/
* SourceTree - great browser/manager for OSX (free)

# Scripts

* git-wtf is a script to tell you wtf is going on with your repository
  http://git-wt-commit.rubyforge.org/

# Apps

* gitg is a Linux app a bit like gitx on OSX. 
  https://github.com/jessevdk/gitg or apt-get install gitg

# Pull vs Fetch

Pull merges changes automatically (but may fail). Fetch doesn't merge, but grabs the changes. That way you can run a **git merge** to merge the changes at a later point.

git pull is effectively:

* git fetch
* git merge