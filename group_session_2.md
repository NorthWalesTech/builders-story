Undoing and working with remotes
================================

The aim of this session is to roll back uncommitted changes from various states. It should last about 15 minutes.

All commands are run from within the _builders-story_ directory.

## Undoing things
Also see [Pro Git 2.4](http://git-scm.com/book/en/Git-Basics-Undoing-Things). 

### Unstage a staged file 

### Undo a modification 
At the end of the basic hands-on session you added your favourite film to your _participant-[YOURNAME]_ file. In hindsight that was a poor move, and will trigger hours of argument and debate. Fortunately you didn't stage or commit your changes, so it should be easy to undo. If you run **git status** it will even tell you what you need to do to revert:

**git checkout -- participant-[YOURNAME]**

Try **git status** again and you'll see the changes have gone. This is a dangerous command! Changes which are reverted and haven't been committed cannot be recovered. Be very sure you don't want those changes before you use this command, and consider the consequences of changing your mind later!

From Pro Git:

_Remember, anything that is committed in Git can almost always be recovered. Even commits that were on branches that were deleted or commits that were overwritten with an --amend commit can be recovered (see Chapter 9 for data recovery). However, anything you lose that was never committed is likely never to be seen again._

### Amend the last commit 
If you mess up the commit, for example by forgetting to add a key file, you can amend the commit. In the last commit we added the message "Adding [YOURNAME] to the list of attendees.", but that didn't capture the entire commit. To amend the commit message you use the **--amend** switch:

**git commit --amend -m "Adding [YOURNAME] to the list of attendees and adding a little about myself."**

## Working with remotes
Also see [Pro Git 2.5](http://git-scm.com/book/en/Git-Basics-Working-with-Remotes).

### Push changes 

### Pulling

### Tips

1. We've omitted tagging from this tutorial because we feel that most of the time it will be done by a build system rather than manually. See [here](http://git-scm.com/book/en/Git-Basics-Tagging) to find out how to do it.
2. There are a couple of tips sections in Pro Git which are worth reading to help get your environment set up: http://git-scm.com/book/en/Getting-Started-First-Time-Git-Setup and  http://git-scm.com/book/en/Git-Basics-Tips-and-Tricks. 