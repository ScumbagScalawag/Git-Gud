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

## How do I contribute to your project?
Here's a high-level overview: 

1. [Fork this repo](#fork)
2. [Clone this repo (`git clone`)](#clone)
3. [Make changes locally](#local)
4. [Commit those changes locally](#committing)
5. [Pull from *my* upstream (to make sure you you are up to date with whats upstream, or
in the cloud)](#pulling)
    - [Setting Your Upstream(s)](#upstream)
6. [Remedy merge conflicts locally](#merge-conflicts)
7. [Push your changes to *your* forked repo.](#pushing)

Then comes the actual contribution to **my** project. Up to this point, you've done
everything on your own machine and your own GitHub project (the remote). 

8. [Do a pull request (often balled a PR)](#pull-request)
9. This stage is where we might hop on a call or be active in chat to discuss your changes. 
Sometimes PR's are trivial, but sometimes they requre deep discussion about what direction
the project is going, what need work, what needs patches, and what features need to be added
or removed. 
10. Next, I (the repo maintainer) will either deny or accept these changes. This could mean you have
to work on some stuff locally before merging your repo into mine, or maybe I (the maintainer) 
can edit your file manually on my end, and immediately remedy the conflicts and such. 
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
After you've forked my repo, "clone" it onto your local machine. 
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
are included in your working directory. 

I'll let you guys do the git clone thing, and figure out how you get stuff locally. 
I'll add more on how you commit, leave commit messages, merge, and do Pull Requests later.  

The Idea behind me setting you up on your local machines first, is so that you can now practice
making local commits, local merges, and all that fun stuff in an environment that I can easily
pivot into working with a team. 

Essentially: welcome to your sandbox. Your sandbox will grow.  

<a name="local"></a>
### 3. Making changes locally (Committing)
*hint: "local" means on your personal computer, and "remote" refers to a cloud server
or a code hosting tool (in this case, GitHub, but there are others that exist)*

<a name="committing"></a>
### 4. Making Commits

<a name="pulling"></a>
### 5. Pulling from Upstream 
"Upstream" referes to the remote location thats hosting your code.
In our case, "upstream" is either your forked repo, or my repo. 
It depends on which one you ran `git clone` on. 
You can set your upstream manually though.
Before we do that, lets take a look at what your upstream is right now.
Run this: 

```
git remote show origin
```

You should see something like this if you've [forked](#fork) and [cloned](#clone) 
your repo correctly. 

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

Pulling is actually a compound operation. Essentially:

pull = fetch + merge

<a name="fetching"></a>
#### Fetching

More soon. 
