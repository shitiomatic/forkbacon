# ForkBacon

[![build](https://github.com/shitiomatic/forkbacon/workflows/build/badge.svg?branch=master)](https://github.com/shitiomatic/forkbacon/actions?query=workflow%3Abuild)

Keeps your repository minimally modified forks in sync.

## Action

```yaml
...
jobs:
  forkbacon:
    runs-on: ubuntu-latest
    steps:
    - name: forkbacon
    - uses: actions/checkout@v2
    - uses: shitiomatic/forkbacon@master # Prefer using tagged version
      with:
        upstream_url: "URL for upstream repo. This must be HTTP" # Required! Upstream https clone URL
        upstream_branch: "master"   # Upstream Branch to use
        branch: "master"   # Local Branch
        method: "rebase"   # Method to use. Can be `merge`, `merge-ff-only` or `rebase`.
        args: "--no-push"  # Additional Arguments to pass to the container
```

## Help

```console
Usage: docker run -it shitiomatic/forkbacon:latest   [options]

Keeps minimally modified forks in sync.
Please do not use this for forks with extensive
modifications as it might lead to lot of conflicts.
-----------------------------------------------------------
[-m --method]           [Method to use. (Defaults to merge-ff)]
[-b --branch]           [Branch to merge/rebase]
[-x --upstream-branch]  [Upstream Branch to merge/rebase (Defaults to master)]
[-u --upstream-url]     [Upstream URL to set (Required)]
[--no-push]             [Skip Git Push]
[-h --help]             [Display this help message]

Version: master
SHA    : 81ef4e67b8beef4ff1ef285c3e5f80b803b3bcb3

This is best used as github action.
For info on how to do it see https://github.com/shitiomatic/forkbacon

```
