
# Git

## Unstage file from being committed

```
git checkout -- <file>
```

## Remove all your changes since last commit

```
git reset --hard
```

## Branching

```
git checkout -b <name>
```

## Rebasing

```
git fetch origin
git rebase origin/master
```

## Merging

```
export myBranch='feature-1'
export upstreamBranch='master'
```

With merge commit:


```
git checkout $upstreamBranch
git merge --no-ff $myBranch
```

Without merge commit:

```
git checkout $upstreamBranch
git merge --ff-only $myBranch
```
