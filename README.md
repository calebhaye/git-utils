# Git Utils

Simple bash scripts to make life with git a bit more enjoyable.

## Overview

This repository contains Bash scripts which are intended to make life as a software developer more enjoyable.  

### Usage

1. Add the `git-utils/bin` to your `$PATH`
2. Append the following to your `.bashrc` file:

#### .bashrc 

    alias init-git-utils='[[ -s "$HOME/git-utils/bin" ]] && source "$HOME/git-utils/bin/"*' # Load the g
    alias current-feature="init-git-utils && git-set-current-feature && git-show-current-feature"
    alias cf="current-feature"
    alias gpcf="current-feature && git push origin $CF"

    trap '
      if [ "x$(git rev-parse --is-inside-work-tree 2>/dev/null)" = "xtrue" ]; then
        CURRENT_FEATURE=$(git symbolic-ref -q HEAD)
        CURRENT_FEATURE=${CURRENT_FEATURE##refs/heads/}
        CURRENT_FEATURE=${CURRENT_FEATURE:-HEAD}

        export CF=$CURRENT_FEATURE
        echo "CURRENT FEATURE: $CF"
      fi
    ' DEBUG
    
#### $CF Environment Variable

Assuming you followed the aforementioned instructions, the `$CF` environment variable will always equal the name of the current branch you are on. :+1:


#### Available Commands

**init-git-utils** 
Sources the bash aliases

**git-set-current-feature** 
Sets the $CF variable to the current git branch

**git-show-current-feature** 
Displays the current feature branch (i.e. the current value of $CF)

## Contributing

Any feedback is welcomed.  Fork/commit/pull-request ... yadda yadda :)

Special thanks to @mcary for helping with the `trap` bit :+1:
