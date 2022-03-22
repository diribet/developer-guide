# Git Developer Guide

All code that we produce should be put into the Git repository except for some one-time scripts.

Developers should commit their work regularly, not leaving uncommitted changes in working copy until the next day.

The Git history serves as useful documentation of the code changes. Be aware of that and write useful commit messages.

## Git setup

On a Windows machine, you should use `core.autocrlf = true`

`user.email` should be set up to @diribet.cz address.

## Repository names

Repository names should contain only letters and `-` sign.

## Main branch

Old repositories are created with a `master` main branch. 
New repositories are created with a `main` main branch.
We mean any of them when we talk about the main branch.

The main branch must not be force-pushed (it should be protected on GitHub).

## Feature branches

Development of new features is done on feature branches.

Feature branch name should contain a short description of the feature or Jira ticket number or both.

When the feature is finished, a pull request should be created.

After an optional code review, it is merged to main branch. If the history of the feature branch is not 
clean (contains some work-in-progress commits or main branch merge commits), squash-merge should be 
used to merge into the main branch.

### Long-running feature branches

When the development of the feature takes a long time, it is desirable to merge the main branch into the 
feature branch regularly. History is then cleaned by the final squash-merge.

### Rebase of a feature branch

It is possible to rebase and force-push feature branch, if you are sure that other developers didn't check it out.

## Commits

### Commit messages

Commit messages should be written in English.

Messages should contain a short description of the feature or bugfix.

If there is a Jira ticket describing this feature, you should append the ticket number to the message. 

E.g.
```
git commit -m "implementation of super-cool evaluation algorithm - CHY-42"
```
