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

- Fetch and merge with upstream
```
git fetch upstream
git checkout master
git merge upstream/master
```

## Merge or Rebase
- `git merge branch_name`: takes new commits from the branch `branch_name` and adds them to the current branch.
- `git rebase branch_name`: takes new commits from the branch `branch_name` and put the current branch on top of  

## Resolve merge conflicts
- Use kdidff3 as merge.tool
```
git mergetool -t kdidff3
```
