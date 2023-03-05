---
title: "How to use gitignore, git hooks for better code management..!!"
seoTitle: "How to use gitignore, git hooks for better code management..!!"
seoDescription: "How to use gitignore, git hooks for better code management..!! Understanding version control and mastering git Series. By Nandan Kumar"
datePublished: Sun Mar 05 2023 15:49:05 GMT+0000 (Coordinated Universal Time)
cuid: clevkjcvw000008mi9gvkacqn
slug: how-to-use-gitignore-git-hooks-for-better-code-management
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1678031198177/ad42397a-1584-4345-a153-e05f139174d7.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1678031270468/42ebe0d7-7ad3-468e-ae2d-374df81ea928.png
tags: code, github, technology, version-control, git

---

Hey Everyone, I know it's been a long time since I have written something in the [git pro series](https://blog.nandan.dev/series/the-git-pro-series) and You all must be waiting for it. So here I am with another blog post in the git series.

In this blog post, I will be taking you through the quirks of gitigore and will talk about how what git hooks are and how to write a basic hook. You can use these two git features to manage your codebase and write cleaner code. So Let's get going...

As I have mentioned this in my previous blog [post](https://blog.nandan.dev/understanding-version-control-and-mastering-git-resolving-merge-conflicts-cherry-picking), managing code in a collaborative environment can be a challenging task, particularly when it comes to version control.

Git is one of the most popular tools for managing code, and it offers many features that can help make code management easier. In this blog, we'll discuss how to use gitignore and git hooks for better code management.

## What is gitignore?

When working on a project, there are often files and directories that you don't want to track with Git. These might include log files, build artifacts or configuration files that contain sensitive information. Gitignore is a feature of Git that allows you to specify patterns of files and directories that should be ignored by Git.

To use gitignore, create a file called .gitignore in the root directory of your Git repository. In this file, you can list patterns of files and directories that Git should ignore. For example, if you want to ignore all log files, you can add the following line to your .gitignore file:

```bash
*.log
```

This will tell Git to ignore all files with the extension .log. You can also use wildcards to ignore entire directories, like this:

```bash
logs/
```

This will tell Git to ignore the entire logs directory and all of its contents.

Using gitignore is important because it keeps your Git repository clean and organized. When you commit changes to your repository, you only want to include the files that are relevant to your project. Ignoring unnecessary files and directories can help prevent your repository from becoming cluttered and difficult to manage.

## Gitignore patterns

Gitignore patterns are a way of telling Git which files or directories to ignore. A pattern is simply a string that Git uses to match file and directory names. Here are some common Gitignore patterns:

* `*.log`: Ignore all files with the extension .log.
    
* `logs/`: Ignore the entire logs directory and all of its contents.
    
* [`config.py`](http://config.py): Ignore the file [config.py](http://config.py).
    
* `/build/`: Ignore the build directory only if it is in the root directory of the repository.
    
* `**/build/`: Ignore the build directory and all of its contents, no matter where it is in the repository.
    

The double asterisk (`**`) is a special pattern that matches any number of subdirectories. Using `**` in a pattern can be useful if you want to ignore a particular file or directory no matter where it is in the repository.

You can also use negation patterns to specify files or directories that should not be ignored. Negation patterns start with an exclamation mark (`!`). For example, if you want to ignore all files in a directory except for one, you can use a pattern like this:

```bash
mydir/*
!mydir/file.txt
```

This tells Git to ignore all files in the `mydir` directory except for `file.txt`.

## What are git hooks?

Git hooks are scripts that Git runs before or after certain Git events, such as committing or pushing changes. Git hooks are stored in the .git/hooks directory of your Git repository, and they can be used to automate tasks or enforce rules for your team's workflow.

There are two types of Git hooks: client-side hooks and server-side hooks. Client-side hooks are run on the local machine where changes are being made, while server-side hooks are run on the remote Git server.

Some common uses of Git hooks include:

* Enforcing code quality standards
    
* Running tests automatically before committing changes
    
* Preventing commits that don't meet certain criteria (such as a commit message that doesn't follow a specific format)
    

## Git hook types

Git has a number of hooks that can be used to automate tasks or enforce rules for your team's workflow. Here are some of the most commonly used Git hooks:

### Pre-commit hook

The pre-commit hook is run before a commit is made, and it can be used to perform checks or tests on the changes being committed. This hook is useful for enforcing coding standards, running linters or static analysis tools, and preventing commits that don't meet certain criteria.

For example, you can use a pre-commit hook to ensure that all of the code being committed passes a linting check. This can help maintain consistent code quality and prevent bugs caused by common coding errors.

### Post-commit hook

The post-commit hook is run after a commit has been made, and it can be used to perform tasks or updates that need to happen after the commit has been made. This hook is useful for performing tasks such as updating a database, sending notifications, or triggering a build process.

For example, you can use a post-commit hook to trigger a build process that automatically deploys your changes to a test environment.

### Pre-push hook

The pre-push hook is run before changes are pushed to a remote repository, and it can be used to perform checks or tests on the changes being pushed. This hook is useful for preventing bad code from being pushed to a remote repository and ensuring that all changes meet certain criteria.

For example, you can use a pre-push hook to ensure that all of the code being pushed has passed a test suite. This can help ensure that your codebase remains stable and consistent.

### Post-receive hook

The post-receive hook is run after changes have been pushed to a remote repository, and it can be used to perform tasks or updates that need to happen after the changes have been received. This hook is useful for performing tasks such as updating a database, sending notifications, or triggering a build process.

For example, you can use a post-receive hook to trigger a build process that automatically deploys your changes to a production environment.

### Prepare-commit-msg hook

The prepare-commit-msg hook is run after a commit message has been entered, but before the commit is made. This hook can be used to modify the commit message or add additional information to it.

For example, you can use a prepare-commit-msg hook to automatically add the branch name or issue number to the commit message. This can help keep your commit messages consistent and organized.

### Pre-rebase hook

The pre-rebase hook is run before a rebase operation is performed, and it can be used to perform checks or tests on the changes being rebased. This hook is useful for preventing bad code from being rebased and ensuring that all changes meet certain criteria.

For example, you can use a pre-rebase hook to ensure that all of the code being rebased has passed a test suite. This can help ensure that your codebase remains stable and consistent.

### Post-merge hook

The post-merge hook is run after a merge operation has been performed, and it can be used to perform tasks or updates that need to happen after the merge has been completed. This hook is useful for performing tasks such as updating a database, sending notifications, or triggering a build process.

For example, you can use a post-merge hook to trigger a build process that automatically deploys your changes to a test environment.

## How to use git hooks

To use Git hooks, you first need to create a script that Git will run. The script should be named after the Git hook you want to use (for example, pre-commit or post-commit). The script should be saved in the .git/hooks directory of your Git repository, and it should be executable.

Here's an example of a pre-commit hook that runs a script to check the formatting of all Python files in your repository:

```bash
#!/bin/bash

echo "Checking Python formatting..."

if ! black --check .
then
    echo "Python files are not formatted correctly!"
    exit 1
fi
```

To make this script executable, you need to run the following command:

```bash
chmod +x .git/hooks/pre-commit
```

This will allow Git to run the script when the pre-commit hook is triggered.

Once you've created your Git hook script, you need to configure Git to use it. You can do this by adding a line to the appropriate Git configuration file. For example, if you want to use a pre-commit hook, you would add the following line to the .git/config file:

```bash
[core]
    hooksPath = .git/hooks
```

This tells Git to use the hooks in the .git/hooks directory of your Git repository.

Git hooks are one of the most important git tools as it can enable you to automate a lot of things in your project i.e. running a code lint or running all the tests before a commit happens. You can even run both lint and test if you want to.

This can help you assure that no bad commits get into the code repository and you can have lesser bugs in the live environment.

That's all folks for now.

Feel free to comment on how you like my blog or shoot me a mail at [**connect@nandan.dev**](mailto:connect@nandan.dev) If you have any queries and I will try to answer.

You can also visit my website to read some of the articles at [**https://nandan.dev**](https://nandan.dev)

Stay tuned & connect with me on my social media channels. Make sure to subscribe to my newsletter to get regular updates on my upcoming posts.

[**Twitter**](https://twitter.com/_sirius93_) | [**Instagram**](https://www.instagram.com/_sirius93_) | [**Github**](https://github.com/sirius93) | [**Website**](https://nandan.dev/)