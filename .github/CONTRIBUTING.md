# How to contribute

## Branching strategy

The following branches are the primary branches:

- main
- develop
- hotfix/\*\*
- \*\* (e.g., feature/**)

The relationships between branches are as follows:

```mermaid
%%{init: { 'gitGraph': {'mainBranchOrder': 10}} }%%
gitGraph
commit id: "init"

branch develop order: 20
checkout develop
commit id: "dev-init"

branch feat/new-ui order: 30
checkout feat/new-ui
commit id: "work-1"
commit id: "work-2"
checkout develop
merge feat/new-ui id: "merge-feat"

branch fix/localization order: 40
checkout fix/localization
commit id: "fix-1"
checkout develop
merge fix/localization id: "merge-loc"

checkout main
merge develop id: "release-v1.0.0" tag: "v1.0.0"

checkout develop
merge main id: "sync-v1.0.0"

branch feat/new-table order: 50
checkout feat/new-table

checkout main
branch hotfix/crash-fix order: 0
checkout hotfix/crash-fix
commit id: "fix-critical"
checkout main
merge hotfix/crash-fix id: "merge-hotfix" tag: "v1.0.1"

checkout develop
merge main id: "sync-v1.0.1"

checkout feat/new-table
commit id: "work-3"
commit id: "work-4"
merge develop id: "Update branch"
checkout develop
merge feat/new-table id: "merge-table"

checkout main
merge develop id: "release-v1.1.0" tag: "v1.1.0"
```

### main

This is the release version.  
All releases are created from this branch. You cannot commit directly to this branch. Also, you cannot merge branches other than the develop branch or hotfix/\*\* branches into it.

### develop

This is the Canary version.  
All implementations are merged into this branch. There is a possibility that bugs still exist. However, since we perform integration tests before merging, bugs should be rare.

### hotfix/\*\*

This is a working branch used when a critical bug is found after a release.  
It allows you to skip the `develop` branch and merge directly into `main`. Please create this branch from the `main` branch and create a Pull Request directly to the `main` branch.

### \*\* (eg. feature/\*\*)

This is a standard working branch for adding features, fixing bugs or other tasks.  
Please create this branch from the `develop` branch and create a Pull Request to the `develop` branch.

Before creating a Pull Request, please merge the latest changes from `develop` and ensure all tests pass.  
Do not implement multiple features in a single branch. Please divide the work by feature as finely as possible.  
Small code units make code reviews easier and help the reviewer!
