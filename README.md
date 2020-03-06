# Fork Bacon

Keeps your repository minimally modified forks in sync.

## Action

```yaml
name: fork
jobs:
  fork:
    - name: fork-bacon
      uses: shitiomatic/forkbacon@0.1.1
      with:
        upstream_url: "URL for upstream repo. This must be HTTP" # Required! Upstream https clone URL
        upstream_branch: "master"   # Upstream Branch to use
        branch: "master"   # Local Branch
        method: "rebase"   # Merge Method
        args: "--no-push"  # Additional Arguments to pass to the container
        key: ${{ secrets.GITHUB_SSHKEY }} # Deploy Key with write access
```