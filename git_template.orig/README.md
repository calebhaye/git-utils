# Git Template

## Configuration

1. Copy the git_template.orig directory to your home folder, and rename it to `.git_template`
2. Run the following command: `git config --global init.templatedir '~/.git_template'`
    
## Hooks

### Post-Checkout

This hook contained within the git template will automatically set the value of the `$CF` environment variable to equal the name of the current branch.
