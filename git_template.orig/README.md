# Git Template

## Configuration

1. Copy the git_template.orig directory to your home folder, and rename it to `.git_template`
2. Run the following command: `git config --global init.templatedir '~/.git_template'`
    
## Hooks

### Post-Checkout

This git template will automatically run `init-git-utils`, `git-set-current-feature`, and `git-show-current-feature` upon checkout (branch change)
