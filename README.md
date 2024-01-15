<a name="br1"></a> 

1/10/24, 12:55 AM

Exercise: Git and GitLab

**Outline**

Introduction

Step 1: Git Basics

Step 2: Branching and Merging

Step 3: Following a Workflow and Code Review

Step 4: Issues and Scheduling Milestones

Step 5: Submission

Bonus Steps - Additional Features to Save Your Skin

**Introduction**

By this point, you have already used and understand the basics of version control, and you have

specifically used either git or svn while managing a small team project. In this exercise, you will

demonstrate how to use some of the features of modern version control along with how to use

integrated tools that can assist in coordinating and enforcing tasks like code review, scheduling, and

issue tracking in a team development environment. The skills that you use in this exercise are core

essentials of modern software development practices. Not only will you be expected to use these

techniques, and the features of GitLab, while developing your semester projects, any work that you

do outside of these workflows simply may not be taken into account during grading.

There are many outside sources of information on using git. The git website has an excellent [book](http://git-scm.com/book/en/v2/)

along with introductory [videos](http://git-scm.com/videos)[ ](http://git-scm.com/videos)that provide an excellent and thorough introduction. They also have

numerous [tutorials](http://git-scm.com/doc/ext). Much of the information in this exercise comes from these tutorials or expects

you to first follow these tutorials and then demonstrate your understanding. Some of the tasks in the

exercise are based on those developed by Ted Kirkpatrick.

**Step 1:** git **Basics**

As you already know, a version control system (VCS) tracks the changes in files over time. Thus, if

you want to know when or why a particular change was made to a file, the VCS should hold the

answer. Managing these versions also means that the VCS can coordinate and track the changes

made by multiple developers, ensuring that changes from multiple developers do not (textually)

interfere with one another. In a modern VCS, a set of selected changes to files is applied *atomically*.

That is, if the changes do not interfere with other changes concurrently made by another developer,

then the changes are all applied simultaneously, otherwise, they are not applied.

One distinguishing feature of git and other distributed version control systems is that you *locally*

batch together groups of changes to files into atomic commits. That is, you make your changes on

your own computer. Then, you can choose to share these batches of changes with others by

*pushing* them to a *remote* repository, likely on a different machine.

In order to gain a better understanding, read the following portions of the git book:

[1.3](http://git-scm.com/book/en/v2/Getting-Started-Git-Basics)[ ](http://git-scm.com/book/en/v2/Getting-Started-Git-Basics)[Git](http://git-scm.com/book/en/v2/Getting-Started-Git-Basics)[ ](http://git-scm.com/book/en/v2/Getting-Started-Git-Basics)[Basics](http://git-scm.com/book/en/v2/Getting-Started-Git-Basics)

[2.1](http://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)[ ](http://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)[Getting](http://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)[ ](http://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)[a](http://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)[ ](http://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)[Git](http://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)[ ](http://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)[Repository](http://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)

[2.2](http://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)[ ](http://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)[Recording](http://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)[ ](http://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)[Changes](http://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)[ ](http://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)[to](http://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)[ ](http://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)[a](http://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)[ ](http://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)[Repository](http://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)

https://www2.cs.sfu.ca/~wsumner/teaching/373/exercise-git-and-gitlab.html

1/5



<a name="br2"></a> 

1/10/24, 12:55 AM

Exercise: Git and GitLab

[2.3](http://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)[ ](http://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)[Viewing](http://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)[ ](http://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)[the](http://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)[ ](http://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)[Commit](http://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)[ ](http://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)[History](http://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)

[2.4](http://git-scm.com/book/en/v2/Git-Basics-Undoing-Things)[ ](http://git-scm.com/book/en/v2/Git-Basics-Undoing-Things)[Undoing](http://git-scm.com/book/en/v2/Git-Basics-Undoing-Things)[ ](http://git-scm.com/book/en/v2/Git-Basics-Undoing-Things)[Things](http://git-scm.com/book/en/v2/Git-Basics-Undoing-Things)

[2.5](http://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Pushing-to-Your-Remotes)[ ](http://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Pushing-to-Your-Remotes)[Pushing](http://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Pushing-to-Your-Remotes)[ ](http://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Pushing-to-Your-Remotes)[to](http://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Pushing-to-Your-Remotes)[ ](http://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Pushing-to-Your-Remotes)[Remotes](http://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Pushing-to-Your-Remotes)[ ](http://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Pushing-to-Your-Remotes)[&](http://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Pushing-to-Your-Remotes)[ ](http://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Pushing-to-Your-Remotes)[Inspecting](http://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Pushing-to-Your-Remotes)[ ](http://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Pushing-to-Your-Remotes)[Remotes](http://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Pushing-to-Your-Remotes)

You should now know about and understand:

git clone

git add, git rm, and git mv

git commit

git status, git diff, and git log

git reset HEAD ...

git checkout -- ...

git push and git pull

.gitignore

What a staging area is, what a commit is, and how to share commits.

Most likely, all of this is actually review from CMPT 276, but we are better off taking no chances.

**Action Items**

Create a new personal project repository using GitLab. Give me(BigOrange233) Developer access to

the repository through the GitLab member settings for the project. This is required for your exercise

to receive a grade. You will use this repository for all tasks

completed in this exercise and submit a cloneable URL of the repository at the end.

The repository must contain exactly two commits. The first commit to the repository must have a

master branch with exactly one file called student.txt, and file must contain exactly one line with your

SFU user ID without the @uci.edu suffix.

The second commit must rename/move student.txt to username.txt and add a second file called

readme.md. The second file may contain anything you want.

These two commits must (naturally) be pushed to the remote GitLab server.

**Step 2: Branching and Merging**

If you have experience using another VCS, you may shudder at the word *branching*. Branching in a

VCS refers to the ability to create a divergent history for a project. The main history of the project

can continue normally on the main branch, and you can make experimental modifications to a

second branch without affecting other developers' ability to use the main one. In fact, they may be

entirely unaware of the changes that you make to the second branch. Once the second branch is in

a desired state, you can merge the histories again, applying the desired changes from the second

branch into the main one. [Back](http://www.imdb.com/title/tt0088763/)[ ](http://www.imdb.com/title/tt0088763/)[to](http://www.imdb.com/title/tt0088763/)[ ](http://www.imdb.com/title/tt0088763/)[the](http://www.imdb.com/title/tt0088763/)[ ](http://www.imdb.com/title/tt0088763/)[Future](http://www.imdb.com/title/tt0088763/)[ ](http://www.imdb.com/title/tt0088763/)is recommended viewing when learning about

branching.

A primary distinguishing feature of git is that branching is easy and lightweight enough that it

becomes one of the primary tools for tracking and managing changes to a software project. We will

explore this more in step 3. In order to gain a better understanding, read the following portions of the

git book:

https://www2.cs.sfu.ca/~wsumner/teaching/373/exercise-git-and-gitlab.html

2/5



<a name="br3"></a> 

1/10/24, 12:55 AM

Exercise: Git and GitLab

[3.1](http://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)[ ](http://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)[Branches](http://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)[ ](http://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)[in](http://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)[ ](http://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)[a](http://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)[ ](http://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)[Nutshell](http://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)

[3.2](http://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)[ ](http://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)[Basic](http://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)[ ](http://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)[Branching](http://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)[ ](http://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)[and](http://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)[ ](http://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)[Merging](http://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)

[3.3](http://git-scm.com/book/en/v2/Git-Branching-Branch-Management)[ ](http://git-scm.com/book/en/v2/Git-Branching-Branch-Management)[Branch](http://git-scm.com/book/en/v2/Git-Branching-Branch-Management)[ ](http://git-scm.com/book/en/v2/Git-Branching-Branch-Management)[Management](http://git-scm.com/book/en/v2/Git-Branching-Branch-Management)

[3.4](http://git-scm.com/book/en/v2/Git-Branching-Branching-Workflows)[ ](http://git-scm.com/book/en/v2/Git-Branching-Branching-Workflows)[Branching](http://git-scm.com/book/en/v2/Git-Branching-Branching-Workflows)[ ](http://git-scm.com/book/en/v2/Git-Branching-Branching-Workflows)[Workflows](http://git-scm.com/book/en/v2/Git-Branching-Branching-Workflows)

You may also try one of the online [tutorials](http://pcottle.github.io/learnGitBranching/?demo). You should now know about and understand:

git branch ..., git checkout ..., and git checkout -b ...

HEAD

What happens to the staging area on checkout. (See stashing)

git merge ...

What a merge conflict is and how to resolve it.

**Action Items**

Create a second branch called feature in your repository. Add a new file called diary.txt to this branch

that contains anything you want.

Merge the feature branch into master. After this, master should now contain diary.txt.

You should now be on the master branch. Create a file called recipes.txt and commit it. Create

another branch called roguechef and modify recipes.txt on that branch. Make sure to then commit it.

Don't merge yet! Back on the master branch, modify recipes.txt differently before committing it. Now

merge roguechef into master. This will cause a conflict because the changes in the two branches

interfere. Resolve the conflict and finish merging roguechef into master.

**Step 3: Following a Workflow and Code Review**

As you saw in [chapter](http://git-scm.com/book/en/v2/Git-Branching-Branching-Workflows)[ ](http://git-scm.com/book/en/v2/Git-Branching-Branching-Workflows)[3.4](http://git-scm.com/book/en/v2/Git-Branching-Branching-Workflows), branching can be used to manage the experimental work associated with

developing a single feature, maintaining legacy versions and new development versions, and more.

In addition, as we shall see shortly, branching can also be used to manage and even enforce peer

review of all code before it is committed to the repository. From now on, you should be following this

latter practice for your projects this semester.

However, there are also some risks that ought to be recognized. In particular, maintaining many

different branches can become undesirably confusing for developers, and the longer a branch lives

without being merged into its eventual targets, the less likely the branch is to merge with few

conflicts and little rework. The benefits and trade-offs of these workflow options need to be

assessed and balanced in order to design a workflow that fits best for your project. Many companies

shift to a [trunk](https://trunkbaseddevelopment.com/)[ ](https://trunkbaseddevelopment.com/)[based](https://trunkbaseddevelopment.com/)[ ](https://trunkbaseddevelopment.com/)[approach](https://trunkbaseddevelopment.com/)[ ](https://trunkbaseddevelopment.com/)to manage the risks of stale branches.

For projects this semester, you will follow a simple GitLab Flow. You can find a full explanation of

GitLab workflows in the [GitLab](https://docs.gitlab.com/ee/topics/gitlab_flow.html)[ ](https://docs.gitlab.com/ee/topics/gitlab_flow.html)[Documentation](https://docs.gitlab.com/ee/topics/gitlab_flow.html). Read this documentation for a full explanation of the

workflow. You can also find [videos](https://www.youtube.com/watch?v=raXvuwet78M)[ ](https://www.youtube.com/watch?v=raXvuwet78M)[online](https://www.youtube.com/watch?v=raXvuwet78M)[ ](https://www.youtube.com/watch?v=raXvuwet78M)illustrating a simple use of the GitLab flow along with

integrated features like merge request management and code review. Watch this video. It contains a

clear illustration of the steps to follow for every change that you make to the repository. Roughly, the

usual steps are as follows:

1\. Perform your development of a feature, refactoring, or whatever on a separate branch.

https://www2.cs.sfu.ca/~wsumner/teaching/373/exercise-git-and-gitlab.html

3/5



<a name="br4"></a> 

1/10/24, 12:55 AM

Exercise: Git and GitLab

2\. When you are ready to merge this feature, push the branch to origin.

3\. Visit the page for the repository in GitLab and click on the button presented to create a *merge*

*request* from the branch you pushed. Merge requests are GitLab's way of organizing changes

to the code that have not yet been approved and merged (to the master branch).

4\. Assign at least one peer of your team to review the code and provide feedback.

5\. Your team member then reviews the code, and you can continue to discuss and improve it

until it is eventually approved and merged to the repository. Under GitLab flow, the source

branch is removed upon merging.

Note, I will track the merge requests as one metric of measuring your overall contributions to your

semester projects. Do not delete the source branches as you proceed, as I can use these to give

you credit and resolve issues in your group.

For your semester projects, you will receive credit for work that makes its way into your master or

develop branch. This provides extra incentives to keep your branches short lived and focused.

**Action Items**

Create a new branch topsecret containing a single file called secrets.txt. Create a GitLab merge request

for the branch. From the merge request management page in GitLab, approve the merge request to

finally merge the branch into the repository. NOTE: In a real project, you should not approve your

own merge requests! In this case, you are doing so simply to learn how the system works. For your

term project, your merge requests should be reviewed and approved by another team member

before being merged.

**Step 4: Issues and Scheduling Milestones**

GitLab also has the ability to identify units of work called *issues*. An issue can be a bug fix, a

documentation change, a feature addition planned for a future sprint, or any other unit of work. The

issue tracking page provides a convenient way of organizing these issues along with a platform for

discussing them, assigning them to developers, and monitoring their progress. Using this system for

your semester projects can help to ensure that you do not forget a task or lose track of it amongst

the many requirements you must fulfill.

Issues can also be assigned to *milestones*, which are commonly used to identify deadlines or

iteration/sprint boundaries in a project. By having both issue tracking and milestone scheduling,

GitLab allows you to flexibly keep track of the tasks that need to be performed and schedule or

*reschedule* them as necessary.

**Action Items**

Create a new milestone titled "Exercise Due" in GitLab and set its due date to September 28.

Create a new issue titled "Add more cats to the readme" and schedule it for the milestone you just

created.

Now modify readme.md by adding the word cat to it (anywhere you like) and commit it to the

repository with a commit message that includes the words "Fixes #N" where N is the number of the

https://www2.cs.sfu.ca/~wsumner/teaching/373/exercise-git-and-gitlab.html

4/5



<a name="br5"></a> 

1/10/24, 12:55 AM

Exercise: Git and GitLab

issue you created. Push the change on a new branch in order to create a merge request. Accept the

merge request and note that the issue is now closed.

**Step 5: Submission**

To submit your exercise, you must submit the cloneable URL of your repository via [CourSys](http://coursys.sfu.ca/). You

can find this on your repository main page. Click the "Clone" button and select the "Clone with

HTTPS" option.

For instance, my submission might be

1 https://csil-git1.cs.surrey.sfu.ca/wsumner/exercise2.git

**Bonus Steps: Additional Features to Save Your Skin**

git includes many additional features that allow you to more conveniently change, navigate, and

extract useful information from the history of a project. Three particularly useful features are

interactive staging, stashing, and tools for debugging. In addition, recall that we spoke in class about

how analyzing git logs could help you to identify problem areas in your project.

**Interactive Staging**

[Interactive](http://git-scm.com/book/en/v2/Git-Tools-Interactive-Staging)[ ](http://git-scm.com/book/en/v2/Git-Tools-Interactive-Staging)[staging](http://git-scm.com/book/en/v2/Git-Tools-Interactive-Staging)[ ](http://git-scm.com/book/en/v2/Git-Tools-Interactive-Staging)allows you to look at the changes in your working directory as diffs and select

exactly the combination of changes you want for a commit. This means that you can choose to

commit only part of the changes to a file if you made changes to the same file that semantically

belong to different commits.

**Stashing**

You probably noticed that checking out a branch required a clean working directory (with no

uncommitted changes). Sometimes you might have changes in your working directory that you do

not yet wish to commit. In this case, you can [stash](http://git-scm.com/book/en/v2/Git-Tools-Stashing-and-Cleaning)[ ](http://git-scm.com/book/en/v2/Git-Tools-Stashing-and-Cleaning)the changes for later, change branches to do your

work, change back to the original branch, and unstash your uncommitted changes on the original

branch. It may sound complicated, but it is quite straightforward to use.

**Debugging**

Git contains some commands that can greatly simplify [debugging](http://git-scm.com/book/en/v2/Git-Tools-Debugging-with-Git)[ ](http://git-scm.com/book/en/v2/Git-Tools-Debugging-with-Git)your code. In particular, you'll find

that use git blame to identify the last commit (and developer) that touched a particular line of code.

Sometimes, though, you'll want to perform a binary search on the history of a project in order to

discover when a bug was first introduced. This can be done either interactively or automatically

using git bisect. These are powerful tools to have in your arsenal.

https://www2.cs.sfu.ca/~wsumner/teaching/373/exercise-git-and-gitlab.html

5/5

