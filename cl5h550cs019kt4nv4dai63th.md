# Understanding version control and mastering git: Resolving  Merge conflicts, cherry-picking..!!

Welcome to the 4th post in the series [Understanding version control and mastering git](https://blog.nandan.dev/series/the-git-pro-series). (This comes after a long gap; I have been a bit caught up with work.) 

Right now, I am parallelly working on multiple requirements and bugs to make sure, The release items are delivered on time. This involves switching between branches and taking recent pulls from the master branch as well as cherry-picking commits to merge the changes to different branches. One issue I am currently facing and which we all face very frequently is  ***merge conflict***.


### So, what is a merge conflict? When can a merge conflict happen?

As we have already covered in the previous blog, when working with Git, users add their commits from two different branches to a common branch, through an action called **merging** or a git merge.  During a merge, files are automatically merged unless there are conflicting sets of changes (i.e. the commits update the same line of code differently).

![pull-push.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1657555250017/yyIo5Qe2z.jpg align="center")

A merge conflict is an event that occurs when Git is unable to automatically resolve differences in code between two commits.

When all the changes in the code occur on different lines or in different files, Git will successfully merge commits without any human intervention.

But, when there are changes that are conflicting on the same lines, a **merge conflict** occurs, Because Git doesn’t understand which code to keep and which to discard.

As I mentioned earlier in the blog, merge conflicts can happen when merging a branch, rebasing a branch, or cherry-picking a commit.

![conflicts.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1657487944288/jsZfhTlR2.gif align="center")

Once Git detects a conflict, it will highlight the conflicted code and ask which code you wish to keep. 

Once confirmed, you can save the file and proceed with the merge, rebase, or cherry-pick.

Whenever a merge conflict is observed, the developers should ideally, sit together and try to resolve the merge conflict; This is so that they don't end up overriding each other's code.

### Git commands to resolve conflicts:
I have listed below the commands that come in handy to resolve a merge conflict. Few of them are already covered in the previous blogs.

- Using the git log --merge command to produce the list of commits that are causing the conflict
```
git log --merge
```
- The git diff command helps to identify the differences between the states' repositories or files
```
git diff
```
- The git checkout command is used to undo the changes made to the file, or for changing branches
```
git checkout
```
- The git reset --mixed command is used to undo changes to the working directory and staging area
```
git reset --mixed
``` 
- The git merge --abort command helps in exiting the merge process and returning to the state before the merging began
```
git merge --abort
```
- The git reset command is used at the time of merge conflict to reset the conflicted files to their original state
```
git reset
```
### Pro Tip: 
Most of the code editors provide their own git conflict resolution tools, either through an inbuilt plugin or extensions. Attaching images here for Visual Studio and Visual Studio Code to help you find such instances easily. 

- **Visual Studio Code**
![visual-studio-code.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657558840542/dzDQt2Auo.png align="left")

- **Visual Studio**
![Visual-studio.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657559007059/N_hDtG_jx.png align="left")

### What is a Cherry-pick?
Imagine you come across a bug in the production environment and an immediate fix is required. This kind of immediate fix is termed a hotfix or a patch. The process to the resolution looks something like this :

1. You work on solving the bug, in your local Dev environment.
2. Once the bug is fixed, You commit it to your daily development branch and test it.
3. After completing the testing you get a go-ahead for the hotfix (Which is to raise a merge/pull request to your release branch) 

Now, to promote your changes to the production/release, it is not feasible to merge the whole daily development branch to the prod/release, because you might end up adding a lot of unnecessary changes. This will increase the testing scope and add so many complications.

Of course, your alternative is to copy-paste all your changes to the new branch. 

![ctrl+paste.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657562813750/GpfOlx_Wf.png align="center")

This is where cherry-picking comes as a lifesaver. 

What cherry-pick does is, it enables arbitrary Git commits to be picked by reference and appended to the current working HEAD.  Therefore, Cherry picking is the act of picking a commit from a branch and applying it to another.

![stand-back-im-going-to-try-git-cherry-picking.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1657562832930/zUqU3xL7h.jpg align="center")

Chill, It's just a meme. Cherry-picking is much easier. All you need is -

-  A freshly created branch from the branch you finally want to merge your changes to.
-  Your original commit hash, which looks something like *3cf741bbdbcdeed65e5371912742e854a035e665*. (Don't worry, you only need the first 8 characters of the whole hash i.e. *3cf741bb*)

Now switch to your newly created branch and run the following command.

```
git cherry-pick <commitSHA>  ---> i.e. git cherry-pick 3cf741bb

``` 
And you are done! 
A fresh commit is created to your new branch, with all the same content and commit message.

You can run the command in a sequence to cherry-pick multiple commits.
```
git cherry-pick <commitSHA1>  
git cherry-pick <commitSHA2>  
git cherry-pick <commitSHA3>  
.
.
git cherry-pick <commitSHAn>  
``` 

Or if you have a series of commits to be cherry-picked, i.e. they are in a sequence. 
To cherry-pick all the commits from commit A to commit B (where A is older than B), run:

```
git cherry-pick A^..B
```
or If you want to ignore A itself, run:

```
git cherry-pick A..B
```
git cherry-pick can also be passed with some execution options. I am listing some of them below.

**-edit**: Passing the -edit option will cause git to prompt a commit message before applying the cherry-pick operation
```
git cherry-pick <commitSHA> -edit 
 I.e. git cherry-pick 3cf741bb -edit
``` 

**--no-commit**: The --no-commit option will execute the cherry-pick. But, instead of making a new commit, it will move the contents of the target commit into the working directory of the current branch.
```
git cherry-pick <commitSHA> --no-commit  
I.e. git cherry-pick 3cf741bb --no-commit
``` 

**--signoff**: The --signoff option will add a 'signoff' signature line to the end of the cherry-pick commit message.
```
git cherry-pick <commitSHA> --signoff 
I.e. git cherry-pick 3cf741bb --signoff
``` 
In case, you come across a merge conflict during the cherry-picking process (which is likely), you can easily resolve a merge conflict as illustrated above at the start of this blog. 

The only catch, if you come across a merge conflict during a cherry-pick, you will have to resolve the merge conflict. Only then, you can continue with cherry-picking. Once you have cherry-picked all the changes, you can commit the same.

Now that we have covered, merge conflicts and cherry-pick as well as merge conflicts during cherry-picking; let's take a pause here. 

I wanted to cover .gitignore in this blog. But we can ignore that for now (*pun intended*). I will try to cover it in another blog. 

If you have any questions on Git, please feel free to reach out to me at [connect@nandan.dev](mailto:connect@nandan.dev).

That's all for now folks.
Stay tuned & connect with me on my social media channels. 
Do make sure to subscribe to my newsletter to get regular updates on my upcoming posts.










