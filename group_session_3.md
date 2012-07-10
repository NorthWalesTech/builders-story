Branching and git-flow
======================

The aim of this session is to get to grips with git flow, and will take us to the end of the day.

These commands assume you've got a clean, empty directory to work in, for example on your desktop. If you haven't, now's a good time to create one! 

We will be using text from https://raw.github.com/NorthWalesDevs/builders-story/master/story.md.

### Create a local repository

Let's call our project "woeful-builder":

**git init woeful-builder**

Move into the newly created repository directory:

**cd woeful-builder**

Now lets initialise the project for git-flow:

**git flow init -d**

_Note you can omit the "-d" if you don't want to use the defaults and it will ask you what you want each set of branches to be called._

You are now in the "develop" branch. Now we need to add some things to the repository.

### Adding the basic files

We'll add the following files to the project to start, both in the woeful-builder directory:

1. metadata.txt
2. the-story.md

Inside _metadata.txt_ add a line with the version number: "VERSION = 0.1-SNAPSHOT", and then add and commit the files:

1. **git add metadata.txt the-story.md**
2. **git commit -m "adding basic files and version 0.1-SNAPSHOT metadata."**

We're now ready to add our first feature for version 0.1, which is the first verse of the story. Let's use a feature branch:

**git flow feature start verse1**

You will notice from the output of the command that you've been moved into the "verse1" branch.

Now copy the first verse from https://raw.github.com/NorthWalesDevs/builders-story/master/story.md to the-story.md. Once that's done commit your changes:

1. **git add the-story.md**
2. **git commit -m "adding the first verse"**

### Update the files in features
Then we'll add the second verse into the file in a similar fashion and commit that:

1. **git add the-story.md**
2. **git commit -m "adding the second verse"**

That will do for the first feature, so let's merge this back into develop and finish up:

**git flow feature finish verse1**

If you look at the list of current branches you'll see that verse1 has been deleted and merged back in.

We need another feature branch for the rest of the poem, so do the same steps as above but call it "verse2". Add the remainder of the story to that feature, commit the changes and then finish that feature.

### Release!
We're ready now to do our first release, so lets create the release branch for the feature-freeze:

**git flow release start 0.1**

We'll do a couple of manual steps to get the version numbers right:

Firstly, the release branch can have the version in _metadata.txt_ bumped to 0.1. Stage and commit that change.

Once that's done we need to switch to the development branch and move that to the next version snapshot before switching back:

1. **git checkout develop**
2. Bump the _metadata.txt version to 0.2-SNAPSHOT_.
3. Stage and commit the change.
4. **git checkout release/0.1**

Our terrible editing skills are coming to light, and there's a plethora of typos in the document. Please fix as many as you can find and check the fixes in (with as many commits as you like).

Finally let's release:

**git release finish 0.1**

### Hotfixing



