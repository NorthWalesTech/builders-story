Undoing and working with remotes
================================

The aim of this session is to roll back uncommitted changes from various states. It should last about 15 minutes.

All commands are run from within the _builders-story_ directory.

## Undoing things
Also see [Pro Git 2.4](http://git-scm.com/book/en/Git-Basics-Undoing-Things). 

### Unstage a staged file 
At the end of the last session you updated the _attendees.md_ file and staged it. Nicknames aren't good to have in an attendees list, so let's pull the staged changes back into the working directory. As usual, the output of **git status** is helpful, telling us that **git reset** will unstage changes:

**git reset HEAD attendees.md**

Running **git status** again we can now see the changes to this file are in the "changed but not updated" state. Open the file and swap your nickname for your middle name, or nothing at all. Finally, stage and commit your changes (if there are any):

1. **git add attendees.md**
2. **git commit -m "Adding my middle name"**

### Undo a modification 
At the end of the basic hands-on session you added your favourite film to your _participant-[YOURNAME].md_ file. In hindsight that was a poor move, and will trigger hours of argument and debate. Fortunately you didn't stage or commit your changes, so it should be easy to undo. If you run **git status** it will even tell you what you need to do to revert:

**git checkout -- participant-[YOURNAME]**

Try **git status** again and you'll see the changes have gone. This is a dangerous command! Changes which are reverted and haven't been committed cannot be recovered. Be very sure you don't want those changes before you use this command, and consider the consequences of changing your mind later!

From Pro Git:

_Remember, anything that is committed in Git can almost always be recovered. Even commits that were on branches that were deleted or commits that were overwritten with an --amend commit can be recovered (see Chapter 9 for data recovery). However, anything you lose that was never committed is likely never to be seen again._

### Amend the last commit 
If you mess up the commit, for example by forgetting to add a key file, you can amend the commit. In the last commit we added the message "Adding [YOURNAME] to the list of attendees.", but that didn't capture the entire commit. To amend the commit you use the **--amend** switch:

**git commit --amend -m "Adding [YOURNAME] to the list of attendees and adding a little about myself."**

This will combine the commit and your current staging area to form the new commit. As your staging area has no changes the only change will be the commit message.

If you look at the history (more information can be found at http://git-scm.com/book/en/Git-Basics-Viewing-the-Commit-History):

**git log**

You will see the message of the last commit has been changed.

## Working with remotes
Also see [Pro Git 2.5](http://git-scm.com/book/en/Git-Basics-Working-with-Remotes).

### Pulling
To update your local repository with the changes from another repository (in this case GitHub), you need to pull:

**git pull**

There's a good chance there won't be any changes if you're the (lucky) first person to get to the push step below.

You can also "fetch" which doesn't attempt to merge the changes into your working copy. See Pro Git for more information.

### Push changes

OK, so you've done all this work and you want to share it. This can be done simply with:

**git push**

If you have a complex set up with multiple remotes or multiple branches you may want to specify them as follows:

**git push origin master**

### Tips

1. We've omitted tagging from this tutorial because we feel that most of the time it will be done by a build system rather than manually. See [here](http://git-scm.com/book/en/Git-Basics-Tagging) to find out how to do it.
2. There are a couple of tips sections in Pro Git which are worth reading to help get your environment set up: http://git-scm.com/book/en/Getting-Started-First-Time-Git-Setup and  http://git-scm.com/book/en/Git-Basics-Tips-and-Tricks. 