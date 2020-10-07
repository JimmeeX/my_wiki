---
description: >-
  Version Control for coding. Here I will throw in commands I commonly use in my
  projects.
---

# Git & Github

## 1. Starting a Project

### Creating a New Project

1. Create a new directory and navigate to it

```bash
mkdir my_project && cd my_project
```

1. Initialise Git versioning for the project \(this will create a _.git_ directory\)

```text
git init
```

1. Map the project to an existing remote Github repository

```text
git remote add origin <git@github.com:<Github-Username>/<Github-Repository>.git>
```

### Making Changes to an Existing Project as a Collaborator

1. Download a copy of the repository locally on your computer. There are 3 main ways to do this:

   1.1. Via HTTPS \(requires Github login/password\)

   ```bash
    git clone https://github.com/<Github-Username>/<Github-Repository>.git
   ```

   1.2. Via SSH \(requires ssh key\)

   ```bash
    git clone git@github.com:<Github-Username>/<Github-Repository>.git
   ```

   1.3. Via Github CLI

   ```bash
    gh repo clone <Github-Username>/<Github-Repository>
   ```

## 2. Creating Local Changes

1. Shows list of changed files

```text
git status
```

1. Shows differences in changed files. Note adding `--staged` shows differences in staged \(after git add\) files

```text
git diff
git diff --staged
```

1. Shows the commit history

```text
git log
```

1. Stage \(add\) files to be committed. `.` will add both tracked and untracked files, `-u` will add only tracked files. [Source](https://stackoverflow.com/questions/572549/difference-between-git-add-a-and-git-add)

```text
git add .
git add -u
```

1. Commit your added files

```text
git commit -m <your message>
```

If you made a mistake, you can use `git reset` to unstage changes.

```text
git reset
```

Adding a filepath argument will only unstage that particular file

```text
git reset <filepath>
```

If you want to completely discard all changes and reset to the last commit you can either

```text
git reset --hard origin <branch-name>
```

```text
git checkout .
```

## 3. Publishing your Local Changes

After committing changes from section 2, your changes will only be reflected in your local computer. If you want to push those changes to the online public Github repository so your team can use your changes, you have to run

```text
git push origin <branch-name>
```

## 4. Updating the Source Code

If a team member has pushed changes and you want to update your code, then you can choose to:

1. Download the updated changes \(without modifying your current local code\)

   ```text
   git fetch
   ```

2. Download the updated changes and updates your current local branch code with the new \ code

```text
git pull origin <remote-branch-name>
```

If you made current local changes and still want to pull in the new code, you can either choose to commit the changes \(Section 2\), or stash them. Stashing will keep a copy of your code and reset your code to the last local commit \(so you can pull in the new code without conflicts\)

```text
git stash
```

If you want to retrieve the stashed code, you can

```text
git stash apply <stash-ref>
```

To find what exists in the stash, you can run

```text
git stash list
```

To empty the stash, you can run

```text
git stash clear
```

## 5. Branching

Work in branches to develop a feature, then merge with master via a pull request

To list all local branches:

```text
git branch
```

To delete \(force\) a branch, add the -D flag

```text
git branch -D <branch-to-delete>
```

To create and navigate to a new local branch

```text
git checkout -b <new-branch-name>
```

## 6. Other Useful Commands

If you have updated .gitignore to ignore already tracked files, you can type the following to stop tracking the file.

```text
git rm -r --cached .
```

## 7. Setting up Git/Github on a New Computer

1. Install Git
2. Configure Git

You can view your current configuration by

```text
git config --list --show-origin
```

You can update your email and name \(for your commits\) by:

```text
git config --global user.email "<your-email@email.com>"
git config --global user.name "your name"
```

1. [Add an SSH Key](https://docs.github.com/articles/generating-an-ssh-key/) for more convenient authentication.
2. [Generate a GPG Key](https://docs.github.com/articles/generating-a-gpg-key/) for encrypted and signed commits.

```text
git config --global user.signingkey "<your-GPG-key>"
git config --global commit.gpgsign true
```

