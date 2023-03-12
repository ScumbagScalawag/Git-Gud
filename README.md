# Git-Gud
Learning Git and GitHub with Noah and friends!

## Here's the Roadmap
### 1. Basics:
You're going to fix all the errors in my commits that pertain to you.
I can't seem to remember how to spell your guys' names...
Here's my working list of participants:
1. Kris Ragband 
2. Cristana Hindenburg
3. Pedros Botina 

Fix (only) your name for me. Thanks. :)

## Some Nuances as You Read
- The terms "master" and "main" are used synonymously to refer to the primary branch
that all features are merged into. **This branch should not be actively worked in.**

# How do I contribute to your project?
Here's a high-level overview: 

1. [Fork this repo](#fork)
2. [Clone your fork (`git clone`)](#clone)
3. [Make changes locally](#local)
4. [Commit those changes locally](#commit)
5. [Pull from *my* upstream (to make sure you you are up to date with whats upstream, or
in the cloud)](#pull)
    - [Setting Your Upstream(s)](#upstream)
6. [Remedy merge conflicts locally](#merge-conflicts)
7. [Push your changes to *your* forked repo.](#pushing)

Then comes the actual contribution to **my** project. Up to this point, you've done
everything on your own machine and your own GitHub project (the remote). 

8. [Do a pull request (often balled a PR)](#pr)
9. This stage is where we might hop on a call or be active in chat to discuss your changes. 
Sometimes PR's are trivial, but sometimes they requre deep discussion about what direction
the project is going, what needs work, what needs patches, and what features need to be added
or removed. 
10. Next, I (the repo maintainer) will either deny or accept these changes. This could mean you have
to work on some stuff locally before merging your repo into mine, or maybe I (the maintainer) 
can edit your file manually on my end, and immediately remedy the conflicts and merge.
11. [I'll continue this list and expand on these points once we get close to this phase. Stay tuned.]

<a name="fork"></a>
### 1. Fork this repo
Forking this repo is like `git clone`, but it creates the "clone" in a 
*remote* location (on GitHub) that you can use as (one of) your "upstream" 
locations. More on upstream locations in a later section. 

From the Home Page of the Project (the one with ScumbagScalawag/Git-Gud
in the top left, go ahead and click the button
that's says "Fork". Go through this dialog and set it up with all its defaults for now. 
You can even change the name of your fork, but it might be best to leave it as-is in most 
cases. 

<a name="clone"></a>
### 2. How do I get these files onto my computer? (spoiler: `git clone`)
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
That is, unless youu didn't re-name the project of your fork, in which case
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
pivot into working with a team. 

Essentially: welcome to your sandbox. Your sandbox will grow.  

<a name="local"></a>
### 3. Making changes locally (Committing)
*hint: "local" means on your personal computer, and "remote" refers to a cloud server
or a code hosting tool (in this case, GitHub, but there are others that exist)*

<a name="commit"></a>
### 4. Making Commits 
Commits are just you saving your project (akin to `ctrl`+`s`). 

```
git commit -m "Your commit message"
```

`-m` for "message". 

Commits should be done frequently. They should be made when you've made any kind of milestone 
like making a new function, figuring out a bug, adding some new objects, or anything else you 
think is significant. More is more in this case. 

Make them as descriptive and concise as possible.

If you run into weird behavior, make sure you've committed your changes in your
feature branch and see if that fixes it.
Sometimes I forget to commit my local feature branch changes before I "merge my changes", 
only to arrive to the file whose contents should have changed in my other branch and be
disappointed and confused. 

<a name="pull"></a>
### 5. Pulling from Upstream 
Pulling is actually a compound operation. Essentially:

**[pull](#pull) = [fetch](#fetch) + [merge](#merge)**

But let's not get ahead of ourselves. 

"Upstream" referes to the remote location that's hosting your code.
In our case, "upstream" is either your forked repo, or my repo. 
It depends on which one you ran `git clone` on. 
You can set your upstream manually though.
Before we do that, lets take a look at what your upstream is right now.
Run this: 

```
git remote show origin
```

You should see something like this if you've [forked](#fork) and [cloned](#clone) 
your repo correctly:

```
* remote origin
  Fetch URL: https://github.com/ScumbagScalawag/Git-Gud
  Push  URL: https://github.com/ScumbagScalawag/Git-Gud
  HEAD branch: main
  Remote branch:
    main tracked
  Local branch configured for 'git pull':
    main merges with remote main
  Local ref configured for 'git push':
    main pushes to main (up to date)
```

The main difference between this output and yours is your URL will be the URL
location of ***your*** project. This (unsurprisingly) is true for any project that exists
on your repo, and that you've "cloned" onto your local machine. 

Ok cool, but you'll need to [pull](#pull) from ***my*** repo to get the latest changes. 
Remember, everyone has their own fork, and they're all doing what your doing, and then 
having their changes added. That said, you'll still need to keep your 

#### Setting Upstream Location(s) 
The following one-liner sets your upstream (of the branch you
run this command in) to:
1. Whatever repo "origin" is set to (which is a URL)
2. Whatever branch is listed after the location (which is a branch in
that repo)

```
git set upstream origin main
```

I believe if you've cloned ***my*** repo, your "origin" is automatically set to the URL
of ***my*** repo, which is 

https://github.com/ScumbagScalawag/Git-Gud . 

If you've cloned one of *your* repos, it will show the URL of your repo's homepage
(i.e. where the README.md is displayed).

#### Whats the point of Setting Upstream? 
In a real-world production environment, you do all your work on local branches, pull from 
the repo everyone else is sending their work to, push to your local repo, then send 
[pull requests](#pr) to have your work included in that "shared" repo. 

You ideally would never really touch the master branch. 

To show this, take a look at [this repos](https://github.com/johannesjo/super-productivity) branches when
I run `git remote show origin`. 

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
Makes sense. I'll need to set *my* upstream push location to be *my* forked repo,
and [send pull requests](#pr) to this person for them to potentially incorporate
my changes. 

If you are a developer who wants to contribute to this project, you would: 
1. [Fork the repo](#fork)
2. [Clone your forked repo](#clone)
3. [Create a new branch](#branch) and navigate to it or navigate to the appropriate, 
existing branch
4. Make all your changes locally, [committing](#commit) along the way to "save"
your progress (in the "git" sense of the word, that is). 

Pause. Ok so you've done all your changes locally and your ready to share your code
with the team. Nice. Grab some Tea. Good work. 
Now, before you push your code, you'll need to make sure you account for anything
that has changed since the commit that your changes diverged from the remote (origin).

5. Account for changes in "origin main" (the remote location for your project). 
In our case, you'll have to make sure you correctly set your upstream locations. 
    1. Make sure you've made a commit in your feature branch at this point. 
    There's nuance as to when you might *not* want to commit at this point, but, just... okay? 
    2. Switch over to main: `git checkout main`
    3. Pull(#pull) from origin: `git pull origin main`. 
    Theoretically, you haven't touched the "main"
    branch, so any conflicts that arrise from comparing your "main" branch with the remote ("origin main")
    should completely exclude your additional features. 
    4. While you're in "main", run `git merge branch-with-new-features`.
        1. You'll need to resolve these conflicts now. This usually requires some communication with
        your team to make sure you're not stepping on anyone's toes. 
6. [Push](#push) these changes to ***your*** remote repo.
7. [Create a **Pull Request**](#pr)


<a name="fetch"></a>
#### Fetching 


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
<<<<<<< HEAD
Some content in A. 
Um uh...
Like uh.. 
ok so here's some more content in A.
You get the idea. 
=======
Some content in B. 
Much more concise. 
>>>>>>> commit-hash-for-branch-B
``````

The `=======` divides the content in `branch-a` (on the top),
and the content in `branch-b` (on the bottom).

Remember, `branch-a` is the branch you're in, and `branch-b` is the branch 
whose content you want to include. 

More soon. 
