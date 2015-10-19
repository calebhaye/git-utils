# Git Utils

Simple bash scripts to make life with git a bit more enjoyable.

## Overview

This repository contains Bash scripts which are intended to make life as a software developer more enjoyable.  

### Usage

1. Clone this repo to your home directory
2. Update your `.bashrc` file with the following:

#### .bashrc 

    alias init-git-utils='[[ -s "$HOME/git-utils/bin" ]] && source "$HOME/git-utils/bin/"*' # Load the g
    alias current-feature="init-git-utils && git-set-current-feature && git-show-current-feature"
    alias cf="current-feature"
    alias gpcf="current-feature && git push origin $CF"

    trap '
      if [ "x$(git rev-parse --is-inside-work-tree 2>/dev/null)" = "xtrue" ]; then
        export CF=`current-feature`
      fi
    ' DEBUG
    
#### $CF Environment Variable

Assuming you followed the aforementioned instructions, the `$CF` environment variable will always equal the name of the current branch you are on. :+1:


## Contributing

Any feedback is welcomed.  Fork/commit/pull-request ... yadda yadda :)