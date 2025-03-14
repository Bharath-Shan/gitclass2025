# Git Exercises and Commands

## Part 1: Repositories

### 1.1 Tasks

1. setup your git user name and email address:
   `git config --global user.name "John Doe"` and
   `git config --global user.email johndoe@example.com` (and optionally the
   preferred text editor of git `git config --global core.editor vim`)
2. put the 3 text [files](example) into a new folder
3. initialize the git repository using `git init <directory>`. Want a better
   terminal experience? Try [Oh My Zsh](https://ohmyz.sh) or
   [Oh My Bash](https://ohmybash.nntoan.com)!
4. use `git status` in order to see what you have currently in your git
   repository
5. add the 3 text files using `git add <filenames>`
6. check the status of your repository with `git status`. Try to understand
   the status output.
7. use `git rm --cached <file names>` as indicated in the status output
   (or `git reset <file names>`) unstage the changes
8. stage the changes again, using `git add <file names>`
9. use `git commit` to save the files into a commit. A text editor will open
   and you need to write a short commit message (e.g. "Initial commit"). Save
   the text file and exit the editor when you are done to finish the commit.
10. now make some changes to the files. (e.g. delete some content)
11. try out the command `git diff`. What do you see?
12. Stage and commit again
13. use `git log` to get the name of the first commit
14. go back to the first version using `git checkout <commit name>`
15. check that you are seeing the first commit; check your current position in
    the commit history through `git log --all`
16. go back to the latest commit using `git checkout main` (or
    `git checkout master`, depending on the name of  your default branch).
17. (for the adventurous: use `git reset --hard <commit name>` to return the
    `HEAD` to the first commit. Why should this be avoided if possible?)
18. use `git rm` to remove the 3 text files
19. choose a recipe from [Foodista](http://www.foodista.com) or write your own!
    Copy the recipe into a new text file; add and commit it to the repository.
20. make some changes to the recipe (personalize it!); commit the changed text;
    this commit will be the base for the following classes.

### 1.2 You should have learned

* how to create the local repository (init)
* how to update the local repository (staging, committing, reset)
* how to inspect the local repository (log, diff, show)

### 1.3 Commands

```git
git config
git init
git add
git commit
git status
git log
git checkout
git reset
git diff
```

## Part 2: Branches and Merging

### 2.1 Tasks

1. extract the archive [recipe.tgz](recipe.tgz)
   (or [recipe.zip](recipe.zip)) into your repository
2. look at `index.html` with your web browser (note: you may need to enable
   local file access for your browser. Instructions
   [here](local_file_access.md))
3. commit all files
4. make a new branch using `git branch <branch name>`. Checkout if the branch
   exists with `git branch` and then `git checkout <branch name>` to move to it.
5. use `git mv` to put your recipe file into the corresponding subfolder
   as `recipes/recipe.md`. This will overwrite the default recipe.
6. look again at `index.html` with your browser and see if your recipe shows up.
7. commit all the changes
8. *Markdown-ize* your recipe (if you don't know what's Markdown and/or how to
   use it, please visit [this page](markdown_for_GitChefs.md));
9. use `git mv recipes/recipe.md recipes/<your_recipe>.md` to give a more
   appropriate name of your choice.
10. edit `index.html` to change the name of the recipe file.
11. commit these changes
12. do further edits to `<your_recipe>.md`, add one ore more images
13. commit the final version
14. switch back to the `main` (or `master`) branch; create a `README.md` file;
    make a few more commits
15. use ["Git Graph"](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph)
    with Visual Studio Code or `git log --all --graph --decorate` in the
    terminal to visualize the git graph structure. Other possible GUI are
    [gitk](https://git-scm.com/docs/gitk), [GitUp](http://gitup.co) on Mac, or
    [ungit](https://github.com/FredrikNoren/ungit) on all platforms
    (other clients are listed [here](https://git-scm.com/download/gui/linux))
16. merge the branch into the `main` (or `master`) branch

### 2.2 You should have learned

* what a branch is
* how to open a new branch
* how to merge one branch into another

### 2.3 Commands

```git
git branch
git checkout <branch name>
git merge
"Git Graph" (or another gui)
```

## Part 3: Remotes

### 3.1 Tasks

1. create a GitHub account
2. create an ssh key using `ssh-keygen` and upload the key to GitHub
3. create a new repository on GitHub
   use `git add remote` to add the remote repository to your repository (follow
   the GitHub help when you create the repository)
4. use `git push` to push your commits to the remote (you get help with
   `git push --help`)
5. edit the file `README.md` using the GitHub online interface
6. use `git pull` to download and merge the new version into the local repository
7. modify again the file `README.md` using the GitHub online interface
8. use `git fetch` to download remote commits
9. type `git status`. What are you seeing? Try to understand that `git pull` is
   a combination of `git fetch` and `git merge` (or `git rebase`)
10. make a local commit and a remote commit using the GitHub interface, so that
    the local and remote repository diverge. Try `git push` and see what happens
11. do again `git fetch` followed by `git merge`: look at the Git Graph
12. redo step "10" (local and remote commit), but now do `git fetch` followed by
    `git rebase`: what is the difference between `merge` and `rebase`?
13. go one folder down from your repository
14. use `git clone --bare` to make a local clone of the repository. What is
   a bare repository?
15. add the second local repository as remote `local`. Open the file
   `.git/config` to see and change the remotes.
16. make a change, commit, and use `git push local main` (or
    `git push local master`) to update the `local` repository

### 3.2 You should have learned

* how to add a remote repository
* how to synchronize (`pull`, `fetch`, `push`, `merge`, `rebase`) with the
  remote repository

### 3.3 Commands

```git
git remote
git push
git clone
git pull
git fetch
git rebase
```

## Part 4: Github and Online Interfaces

### 4.1 Tasks

1. make a fork of the main repository
  [github.com/git-impatient/cookbook](https://github.com/git-impatient/cookbook)
2. clone the fork on your personal computer
3. make a new branch with a name of your choice
4. checkout the new branch.
5. integrate your recipe into the cookbook and commit to the new branch
6. push the modified cookbook branch to your GitHub repository fork
7. add the main repository as a remote with name `upstream` to the local
  repository. Checkout the file `.git/config` after you have done it. What
  is the difference between `origin` and `upstream`?
8. open a pull request using the GitHub web interface to include your changes
  in the main repository
9. reply to the comments of the repository managers and fix conflicts on
  your local computer by committing and pushing new versions to your GitHub
  fork's branch.

### 4.2 Advanced

1. Try to push from the local `main` (or `master`) to a different remote branch
   with `git push origin main:new_branch` (or
   `git push origin master:new_branch`).

### 4.3 You should have learned

* how to use git to interact with a repository hosted on GitHub
* how to work on foreign repositories using forks and pull requests

### 4.4 Commands

```git
git blame
```
