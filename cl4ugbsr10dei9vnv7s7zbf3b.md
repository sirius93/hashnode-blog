## Understanding version control and mastering git - Tag, log, Stash, and more..!

After a short one-week break, I am back with more on git commands. In the previous blogs in this series, we learned about version control and some basic git commands. We also learned about branching and merging (two very important concepts in git). 

You can follow the complete series (or any of the previous blogs in this series) by clicking [here](https://blog.nandankumar.info/series/the-git-pro-series).

In this blog, I will cover more on git commands like Tag, Log, Stash, etc, which come in handy in day-to-day development. Let's get started.

### git tag: Identify a significant commit 
This Git tag command can be used to mark a significant changeset, such as a release.

- Create a new tag
```
git tag <tagname> 
git tag 1.0.0
``` 
- Tag a specific commit
```
git tag <tagname> <commitID> 
git tag 1.0.0 a3d3dwe323de3r2e
``` 
- List out all the tags
```
git tag
``` 
- Push all tags to the remote repository
```
git push --tags origin
``` 
- Delete a tag
```
git tag -d <tagname>
``` 
- Checking Out Tags
```
git checkout <tagname>
``` 

### git log: List a commit history
This Git log command can be used to see the logs of commits like an overview of all the changes made in a specific branch.

- list the version history for the current branch.
```
git log
``` 
- list the version history of a specific file
```
 git log –-follow <file name>
``` 
- shows the metadata and content changes of the specified commit
```
 git show <commitID>
``` 

### git reset: For when things may go wrong
IF sometimes a commit or a file add goes wrong and you want to undo the changes, the reset command comes to the rescue

- This command unstages the file, but it preserves the file contents.
```
 git reset <file Name>
``` 
- This command undoes all the commits after the specified commit and preserves the changes locally.
```
 git reset <commitID>
``` 
- This command discards all history and goes back to the specified commit.
```
 git reset –-hard <commitID>
``` 
- If you mess up, you can replace the changes in your working tree with the last content in the head: Changes already added to the index, as well as new files, will be kept.
```
git checkout -- <filename>
``` 
- To drop all your local changes and commits, fetch the latest history from the server and point your local master branch at it.
```
git fetch origin
git reset --hard origin/master
``` 

### git stash: For when you want to get a quick tour of another branch.
There will be instances when you are working on a branch and you have to switch to another branch due to some work. 

In such cases, you have to commit your existing changes. But that is not always desirable; you would ideally want to keep your commit history clean and would not want to commit a half-baked work. In such cases, you can stash your work by using the git stash command.

- This command temporarily stores all the modified tracked files.
```
git stash
``` 
- This command temporarily stores all the modified tracked files with a message
```
git stash save "<stash message>"
``` 
- This command lists out all the stashed changesets
```
git stash list
``` 
- This command restores the most recently stashed files.
```
git stash pop
``` 
- This command discards the most recently stashed changeset.
```
git stash drop
``` 
**Pro Tip:** You can use git stash to pass your code from one branch to another branch in case of conflicts. 

That's all for now! We will cover conflicts in the next blog. I know it's the most painful task of all. And not just conflicts, we will also cover more on git and its commands. We will dig deeper and learn how to ignore certain files in a repository and so on.

If you have any questions on git, please feel free to shoot out a mail to *nandan.1345@gmail.com* and I will try and get back to you.

Stay tuned & follow me on my social media channels. Do make sure to subscribe to my newsletter to get regular updates on my upcoming posts.