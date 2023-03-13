# Git-Gud
Learning Git and GitHub with Noah and friends!

## Here's the Roadmap
### 1. Basics:
You're going to fix all the errors in my commits that pertain to you.
I can't seem to remember how to spell your guys' names...
Here's my working list of participants:
1. Chris Ragland 👨‍💻 
2. Cristana Hindenburg
3. Pedros Botina 
4. Murvan Oranzo

Fix (only) your name for me. Thanks :)

### 2. `.gitignore`
1. Create some super secret file that you don't want everyone on the team to see. 
2. Add this file to your `.gitignore` file. (Create the file first: `touch .gitignore`)
3. Use the information on this page get to the point of a [Pull Request](#pr)
4. Sign off in the list below that you've finished Challenge 2: 

- 

### Some Nuances as You Read
- The terms "master" and "main" are used synonymously to refer to the primary branch
that all features are merged into. **This branch should not be actively worked in on 
your local machine.**
- "Machine" or "local machine" as I use it just means your computer. It's just my way
of being explicit as to when something is happening on a "remote" server, like GitHub, or on
your computer. 

<a name="top"></a>
# How do I Contribute to Your project?
I'm glad you asked. Here's a high-level overview (with links!).

1. [Fork the repo](#fork)
2. [Clone your forked repo](#clone) (`git clone`)
3. You can optionally do step 6 at this point. Continue with step 4 if you want to get started working right away
and deal with the GitHub side of things later. 
4. [Create a new branch](#branch) locally and navigate to it or navigate to the appropriate existing branch
5. Make changes locally: in this branch and [commit](#commit) along the way. 

Pause. Ok so you've done all your changes locally and your ready to share your code
with the team. Nice. Grab some Tea. Good work. 
Now, before you push your code, you'll need to make sure you account for anything
that has changed in **my** remote repo since you've started working. 

6. [Set your upstream location(s)](#upstream) 
    - [Method 1](#m1)
    - [Method 2](#m2)
7. [Pulling from Upstream](#pull): account for changes in the project since you've started your feature.
    1. Make sure you've made a commit in your feature branch at this point. 
    There's nuance as to when you might *not* want to commit at this point, but, just... okay? 
    2. Switch over to main: `git checkout main`
    3. [Pull](#pull) from origin: `git pull origin main` or `git pull upstream main`, depending on if you
    used [Method 1](#m1) or [Method 2](#m2), respectively. [Resolve merge conflicts](#merge-conflicts).
    4. [Merge](#merge) your changes to the new-and-improved main. 
    While you're in "main", run `git merge branch-with-new-features`.
        - You'll need to once again resolve *these* [merge conflicts](#merge-conflicts) locally. 
        Get your featurs into main and make sure everything in main works with your new changes. 
8. [Push](#push) these changes to ***your*** (forked) remote repo.

Then comes the actual contribution to **my** project.
Up to this point, you've been pulling stuff from *my* 
repo and pushing to *your* repo. 

9. [Create a **Pull Request**](#pr)
10. Profit.

<a name="fork"></a>
## 1. Fork this repo
Forking this repo is like `git clone`, but it creates the "clone" in a 
*remote* location (on GitHub) that you can use as (one of) your "upstream" 
locations. More on upstream locations [here](#upstream). 

From the Home Page of the Project (the one with ScumbagScalawag/Git-Gud
in the top left) go ahead and click the button that says "Fork". 
Go through this dialog and set it up with all its defaults for now. 
You can even change the name of your fork, but it might be best to leave 
it as-is in most cases. 

<a name="clone"></a>
## 2. How do I get these files onto my computer? (spoiler: `git clone`)
After you've forked **your** repo, "clone" it onto your local machine. 
Go ahead and run in your terminal. 

```
git clone https://github.com/Your-username-and-Repo-here
```

For me (and this GitHub project) this is what **I** run: 

```
git clone https://github.com/ScumbagScalawag/Git-Gud
```

*Hint in GitHub, hover over the code block and click "copy" on the far right.*

**You'll `git clone...` *your* repo!**

This will put a `Git-Gud` folder in the place you run `git clone...`.
That is, unless you didn't re-name the project of your fork, in which case
it would display that name. Makes sense.  

If you want this project to be located in your `/home/yourlocalusername/Documents/coding-programming` folder, 
navigate to that folder, and run the `git clone...` command. 

This command essentially downloads the stuff on the cloud to your local computer.

It does this, while also letting your computer know that this is indeed a `git` project,
which means you can run any `git ...` command. The `.gitignore` and `.git` files 
are then included in your working directory.  

I'll let you guys do the git clone thing, and figure out how you get stuff locally. 
I'll add more on how you commit, leave commit messages, merge, and do Pull Requests later.  

I'm showing you all this stuff in a particular order.
The Idea behind me setting you up on your local machines first, is so that you can now practice
making local commits, local merges, and all that fun stuff in an environment that I can easily
incorporate into a project that exists outside of your local machine. 

Essentially: welcome to your sandbox. Your sandbox will grow.  

## 3. To Upstream or Not to Upstream
You can optionally do [step 6](#step-six) at this point. 
Continue with step 4 if you want to get started working locally right away
and deal with the GitHub side of things later.

<a name="step-four"></a>
<a name="branch"></a>
## 4. Creating Branches
Making a branch means you create a copy of the branch you're on. 
The original branch will be unaffected by changes in your new branch until you [merge](#merge)
the new branch into your main branch. 

**All your work you do locally should be done in branches that aren't "main" or "master**

Let's make sure we're actually *in* the main branch before we create a branch of main: 

```
git checkout main
```

Let's "checkout", or switch, to a new branch aptly called `new-branch`.

```
git checkout -b new-branch
```

<a name="commit"></a>
## 5. Making Changes Locally: Committing and Merging
Along the way, you'll need to commit things. Committing is like saving
Commits are just you saving your project (akin to `ctrl`+`s`), but you can revert 
*all* your files in your project back to different commits in case you do something 
unintended. 

go to the branch you want to make a commit in and run: 

```
git commit -m "Your commit message"
```

`-m` is for "message". 

Commits should be done frequently. They should be made when you've made any kind of milestone 
like making a new function, figuring out a bug, adding some new objects, or anything else you 
think is significant. More is more in this case. 

Make them as descriptive and concise as possible.

If you run into weird behavior, make sure you've committed your changes in your
feature branch and see if that fixes it.

Sometimes I forget to commit the changes in my local feature branch before I "[merge](#merge) my changes", 
only to arrive to the file whose contents should have changed in my other branch and be
disappointed and confused. 

<a name="merge"></a>
#### Merging 
Merging branches sounds kinda like what it is. 
When branch B is merged **into** branch A, that means there are features in branch B
that you'd like branch A to have. 

Lets merge `branch-b` into `branch-a`. Remember: this has to be done within `branch-a`,
which is the destination branch. 
*moving to `branch-a`:*

```
git checkout branch-a
```

*merging `branch-b` into `branch-a`*
```
git merge branch-b
```

<a name="merge-conflicts"></a>
##### Merge Conflicts 
Merge conflicts happen. Thats ok. They look like this:

```
Some content in A. 
Um uh...
Like uh.. 
ok so here's some more content in A.
You get the idea. 
Some content in B. 
Much more concise. 
``````

The `=======` divides the content in `branch-a` (on the top),
and the content in `branch-b` (on the bottom).

Remember, `branch-a` is the branch you're in, and `branch-b` is the branch 
whose content you want to include. New stuff is on the bottom. 

<a name="step-six"></a>
<a name="upstream"></a>
## 6. Setting Upstream Location(s) 
TLDR: use either method:
- [Method 1](#m1): `git remote set-url --pull origin`
- [Method 2](#m2): `git remote add`

Before you get any funny ideas of pulling from and pushing to a remote repo, lets
make sure you'll be doing so from/to the right locations. Run this:

```
git remote -v
```

*Note: in the CLI, `-v` often mean `--verbose`*

This outputs:

```
origin  https://github.com/YourUsernameHere/Git-Gud (fetch)
origin  https://github.com/YourUsernameHere/Git-Gud (push)
```

You should see something like this if you've [forked](#fork) and [cloned](#clone) 
your repo as I've listed it in these instructions.

*note: pull = fetch + merge, so just consider "[fetch](#fetch)" to be the location
your getting updates from. Your fork (for the sake of this project) remains unchanged.
More on this [here](#pull)*

Ok cool, but you'll need to [pull](#pull) from ***my*** repo to get the latest changes. 
Remember, everyone has their own fork, and they're all doing what your doing, and then 
having their changes added. That said, you'll still need to keep your Fetch URL as **mine**, 
because you'll always want to be getting the most up-to-date version of the codebase. 
You don't need any special permissions to pull. You can pull all the livelong. 

There are two main ways I set upstream location(s). 

<a name="m1"></a>
### Method 1 ("No thinky thinky" method)
TLDR: `git remote set-url --pull origin`

The following one-liner sets your "origin" **for pulling** to *my* repo, 
hence the --pull option. The advantage here is that once you've set it up, you 
can just call "origin" to refer to some remote location, and your computer (clever as it is)
will know to **pull** from my repo and **push** to yours. 

```
git remote set-url --pull origin https://github.com/ScumbagScalawag/Git-Gud
```

This setup is nice in general becuase now you don't have to worry about calling *my* repo 
something like "upstream": you can just say `git push origin main` and `git pull origin main`
and all the legwork is setup to **pull** from my repo and **push** to yours. 

Before we move on, lets make sure your've done this correctly. Run this command again:

```
git remote -v
```

That should now output something like this:

```
origin  https://github.com/ScumbagScalawag/Git-Gud (fetch)
origin  https://github.com/YourUsernameHere/Git-Gud (push)
```

Notice how your pull/fetch URL has now changed. Nice. 

*more on fetch [here](#fetch).*

<a name="m2"></a>
### Method 2 ("Ouch. Thinky hurt brain" method)
TLDR: `git remote add`

If you'd like to keep a more finely-tuned arrangement of push and pull 
locations, use this method. The advantage here is you have more manual control
over where you push to and pull from every time you do so. 

**This method is also preferred if you have a setup that's more complicated than
pulling from one place and pushing to another.** For example, if you wanted to 
be able to push to and/or pull from two or three different locations, you'd probably 
want to use this method. 

To keep your "origin" tied to *your* URL for both pushing and pulling, you'll 
need to configure a different location that represents *my* branch. 

Let's call it "upstream". 

```
git remote add upstream https://github.com/ScumbagScalawag/Git-Gud
```

Remember, you can check your upstream locations with `git remote -v`.
Yours should look like this if you're going the Method 2 route: 

```
origin  https://github.com/YourUsernameHere/Git-Gud (fetch)
origin  https://github.com/YourUsernameHere/Git-Gud (push)
upstream  https://github.com/ScumbagScalawag/Git-Gud (fetch)
upstream  https://github.com/ScumbagScalawag/Git-Gud (push)
```

If you've skipped steps 4 and 5, you should [return back to them now](#step-four).

<a name="pull"></a>
## 7. Pulling from Upstream 
Theoretically, you haven't touched the "main"
branch, so any conflicts that arrise from comparing your "main" branch with the remote ("origin main")
should completely *exclude* your additional features. 

Pulling is actually a compound operation. Essentially:

**[pull](#pull) = [fetch](#fetch) + [merge](#merge)**

But let's not get ahead of ourselves. 

Lets switch over to main: `git checkout main`

Go ahead and pull those changes from upstream. 
`git pull origin main` or `git pull upstream main`, depending on if you 
used [Method 1](#m1) or [Method 2](#m2), respectively. 

Youll need to [resolve any merge conflicts](#merge-conflicts) now. 

Now, [merge](#merge) the changes you've made on your feature branch with main 
(while staying in main): `git merge branch-with-new-features`

You guessed it: [resolve those merge conflicts](#merge). 

Boom. Now that you've done that, you should test out the code and make sure
everything is working okay. 

<a name="fetch"></a>
### Fetching 
Fetch allows you to simply download the most up-to-date version of the project to 
your local machine **without** merging it with the changes that you've made. 

Fetch is totally safe and won't ever have conflicts with anything on your local
machine.

The following command downloads the latest version of the stuff in "origin". 

```
git fetch origin
```

This command would download the stuff in the "master" branch (only) from "origin".


```
git fetch origin master
```

**This command will put a new branch named `origin/master` in your local folder.**
This branch can be checked out (`git checkout origin/master`) like any other
branch. You can then review the most up-to-date version of the project in a safe 
evironment that *doesn't* include the changes you've made. 

Once you're ready, you can then `git checkout branch-with-new-features` and `git merge origin/master`. 
At that point, you'll find yourself in a familiar place. Congrats: you just did
a pull, but manually. 

Remember: [pull = fetch + merge](#pull)

I think using fetch is better than pull in most cases, I'll leave it up to you
as to whether or not you want to fetch + merge, or just pull. 

### Whose Repo Is it Anyway? More on Upstream and Best Practices
If you've cloned ***my*** repo, your "origin" is automatically set to the URL
of ***my*** repo.

If you've [cloned](#clone) one of ***your*** repos, `git remote -v` will show the URL of your repo's homepage
(i.e. where the README.md is displayed) for fetching and pushing. Makes sense. 

#### Some Context: Working in Different Branches
TLDR: Work in other branches -> merge to main -> send pull request -> repeat.
*[skip this rant](#push)

In a real-world production environment, you do all your work on local branches, pull from 
the repo everyone else is sending their work to in order to get the most up-to-date codebase, 
[merge](#merge) your changes into this updated code, push to your local repo, then send 
[pull requests](#pr) to have your work included in that "shared" repo. 

You ideally would never really actively work in the master branch, but for now we're just gonna merge master. 

To show this, take a look at [this repos](https://github.com/johannesjo/super-productivity) branches when
I run `git remote show origin`, which shows me the URL locations for push and pull and the branches that exist
at that location.

```
* remote origin
  Fetch URL: https://github.com/johannesjo/super-productivity
  Push  URL: https://github.com/johannesjo/super-productivity
  HEAD branch: master
  Remote branches:
    JustAPhrog-pl-translation               tracked
    bytrangle-feat_smart-date-parser        tracked
    dependabot/npm_and_yarn/fs-extra-10.1.0 tracked
    feat/all-task-list                      tracked
    feat/android-backup                     tracked
    feat/automerge                          tracked
    feat/awesome-bar                        tracked
    feat/blockstack                         tracked
    feat/calendar                           tracked
    feat/complexity-points                  tracked
    feat/dexie                              tracked
    feat/done-sound                         tracked
    feat/dropbox                            tracked
    feat/electron-service-worker            tracked
    feat/focus-mode                         tracked
    feat/global-metrics                     tracked
    feat/gun                                tracked
    feat/ical-timeline                      tracked
    feat/new-db-layer                       tracked
    feat/ng-13                              tracked
    feat/open-project                       tracked
    feat/re-style-task-list                 tracked
    feat/remoteStorage                      tracked
    feat/rxdb                               tracked
    feat/solid                              tracked
    feat/timeline                           tracked
    feat/upgrade-ng10                       tracked
    feat/watermelonDB                       tracked
    feat/webdav                             tracked
    master                                  tracked
    test-github-actions                     tracked
    test/git-actions                        tracked
    thetric-build/angular-10-upgrade        tracked
    upgrade-ng12                            tracked
    v1-branch                               tracked
  Local branch configured for 'git pull':
    master merges with remote master
  Local ref configured for 'git push':
    master pushes to master (up to date)
```

This setup is not managable, because I don't have permission to replace their code.
Makes sense. To contribute to their project, I'll need to set *my* upstream push 
location to be **my forked repo** (with [Method 1](#m1)) or add a new remote location (with
[Method 2](#m2)) and [send pull requests](#pr) to this person for them to potentially incorporate
my changes.

<a name="push"></a>
8. Pushing 
*note: I usually [pull](#pull) from any location I push to just to be super sure I'm pushing
changes that are up to date, even if I "know" I haven't changed anything*

You'll be pushing to ***your** repo (that was forked from mine, in this case). 

a. Run `git remote -v` to double-check that you've set your push location to *your* repo.

**`git remote -v` for [method 1](#m1):**

```
origin  https://github.com/ScumbagScalawag/Git-Gud (fetch)
origin  https://github.com/YourUsernameHere/Git-Gud (push)
```

**`git remote -v` for [method 2](#m2):**
```
origin  https://github.com/YourUsernameHere/Git-Gud (fetch)
origin  https://github.com/YourUsernameHere/Git-Gud (push)
upstream  https://github.com/ScumbagScalawag/Git-Gud (fetch)
upstream  https://github.com/ScumbagScalawag/Git-Gud (push)
```

b. Now push your changes to your repo:

```
git push origin main
```

There you go! You should double-check on GitHub that your push went through. 

<a name="pr"></a>
## 9. Pull Requests - How Your Code is Added to My Code
**Why's it called a pull request?**
It's called that becase it is a request by you (a contributor) to have me (the maintainer)
pull your changes/additions/features into my project. 
Remember: [pull = fetch + merge]. So by sending a pull request, you're asking me to download 
(fetch) your changes, and merge them into my project. 

Make sure you've done all the steps 1-9 before you do a PR. 

Make sure your feature branch was correctly merged into the main branch in its most
current state with no errors or remaining merge conflicts locally before you initiate a PR. 

This stage is where we might hop on a call or be active in chat to discuss your changes. 
Sometimes PR's are trivial, but sometimes they requre deep discussion about what direction
the project is going, what needs work, what needs patches, and what features need to be added
or removed. 

Next, I (the repo maintainer) will either deny or accept these changes. This could mean you have
to work on some stuff locally before merging your repo into mine, or maybe I (the maintainer) 
can edit your file manually on my end and immediately remedy the conflicts and merge.

Thanks for reading! I hope you learned something new. 
Feel free to use the [top of this guide](#top) as a reference for the git workflow. 
