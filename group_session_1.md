Git basics
==========

The aim of this session is to get to grips with the basics of Git and to try some of the basic commands. It should last about 20 minutes.

These commands assume you've got a clean, empty directory to work in, for example on your desktop. If you haven't, now's a good time to create one! Once you've got a local copy, all commands are run from within the _builders-story_ directory.

### Get a repository

See also [Pro Git 2.1](http://git-scm.com/book/en/Git-Basics-Getting-a-Git-Repository).

You will need to clone this repository to take part in the tutorial. If you've got this far then you'll probably have noticed the links to clone the repository on the main page. To clone the project you'll need to use 'git clone [url]', e.g.:

**git clone https://github.com/NorthWalesDevs/builders-story.git**

In your working directory you'll now have a _builders-story_ directory containing this file and the others useful for this tutorial. Have a look around, and you'll also see the .git directory containing the Git repository information.

### Adding files to Git
 
See also [Pro Git 2.2](http://git-scm.com/book/en/Git-Basics-Recording-Changes-to-the-Repository)

Inside the _builders-story_ directory you can see the state of the repository by looking at the status:

**git status**

You should see a message saying there's nothing to commit. Let's add a change and see the effect it has.

Create a file within _builders-story_ named _participant-[YOURNAME]_, replacing _[YOURNAME]_ for your name. Add a line inside the file with your favourite quote.

Once you've saved your new file, check the status again:

**git status**

You should now see that your newly created file is "untracked", i.e. Git isn't tracking the changes. Fortunately for us, the Git commands are very informative, and it has given us a solution: using "git add [file]". Tell Git to track your new file:
	
**git add participant-[YOURNAME]**

Running **git status** again will show you the file is under "Changes to be committed".

### Editing existing files

See also [Pro Git 2.2](http://git-scm.com/book/en/Git-Basics-Recording-Changes-to-the-Repository)

Please add your first name to the _attendees.md_ file underneath the company you work for. If the company isn't listed, just add it in in the same fashion.

Once that's saved you can "stage" the file to be committed. Running **git status** will show the file to "changed but not updated". Staging a file is the same as the initial add:

**git add attendees.md**

This is an important difference to Subversion or CVS. The staging area is used to prepare a set of files for commit, and contains the files in the state they were **at the point they were staged**. If you subsequently make changes to the file and want it to be included in the commit you will need to run **git add [file]" again.

Add your surname to the _attendees.md_ file, save it and run **git status** to see this in action. 

### Viewing changes

See also [Pro Git 2.2](http://git-scm.com/book/en/Git-Basics-Recording-Changes-to-the-Repository)

It's all very well seeing which files have changed, but often you'll want to see the specific changes which have been made. 

To see the changes which have been made but not staged:

**git diff**

You should see the addition of your surname as the only change.

To see the changes which have been stages but not yet committed:

**git diff --staged**

This should show the addition of your first name, but not your surname.

Before we go any further let's stage your latest changes:

**git add attendees.md**

### Committing your changes

See also [Pro Git 2.2](http://git-scm.com/book/en/Git-Basics-Recording-Changes-to-the-Repository)

Committing changes is as simple as using **git commit**. Your editor will fire up requesting a commit message. You can also streamline this using the *-m* switch:

**git commit -m "Adding [YOURNAME] to the list of attendees and adding a little about myself."**

Your changes are now all in the repository. 

Before we finish up, take a second to do the following:

1. Add a nickname to the _attendees.md_ file. Don't worry, you can make it up. Stage this change but don't commit it.
2. Add your favourite film to the _participant-[YOURNAME]_ file. Don't stage this change.
3. Run **git status** to see the effect your changes have had. Use **git diff** and **git diff --staged** to dig a bit deeper.

### Tips

1. You can omit the staging area and commit changed files directly by using **git commit -a**.
2. You can move files around using **git mv [file] [target]**.
3. You can delete files by using **git rm [file]**.