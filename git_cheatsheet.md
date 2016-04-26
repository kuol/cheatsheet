## Basic staging:
- Stage modified and deleted files ( __u__: update, comparing to files that are already staged.)
```
git add -u
```
- Stage modified and new files (__.__: current directory, add everything in current directory.)
```
git add .
```
- Stage all modified, deleted and new files
```
git add -A
```


## Basic control
- Dicard unstaged changes.

  - Discard a certain unstaged file
  ```
  git checkout path/to/myfile
  ```
  - Discard all unstaged files in current directory
  ```
  git checkout -- .
  ```

## Set up Upstream Repo and merge

- List currrent configured remote repository
```
git remote -v
origin  https://github.com/YOUR_USERNAME/YOUR_FORK.git (fetch)
origin  https://github.com/YOUR_USERNAME/YOUR_FORK.git (push)
```
- Specify a new remote upstream repository
```
git remote add upstream https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git
```

- Fetch and merge with upstream `git fetch upstream; git merge upstream/master` is equivalent to `git pull upstream/master`
```
git fetch upstream
git checkout master
git merge upstream/master
```

`git fetch` is the command that says "bring my local copy of the remote repository up to date."


`## Merge or Rebase
- `git merge branch_name`: takes new commits from the branch `branch_name` and adds them to the current branch.
- `git rebase branch_name`: takes new commits from the branch `branch_name` and put the current branch on top of  

## Resolve merge conflicts
- Use kdidff3 as merge.tool
```
git mergetool -t kdidff3
```

## Git Branching
- Create a new branch based on current branch and switch to it.
```
git checkout -b new_branch
```

- Push your local `new_branch` to remote
```
git push -u origin feature_branch_name
```

- Push all your local branches to the remote
```
git push -u origin feature_branch_name
```


## Git: Basic Design Philosophy:
Git: not a __client/server__ model that assumes the server is always available.  
Instead, git is a __distributed__ model, in which the client and the server don't need to be only at the same time. Git can figure out the changes needed even when the remote repository is not reachable. Later when you need to send the changes to someone else, git can transfer them as a set of changes from a point in time known to the remote repository.

There are often at least 3 copies of a project on you computer.
- Your own repository with your own commit history.
- Your working copy where you are editing and building
- Your local "cached" copy of a remote repository.
