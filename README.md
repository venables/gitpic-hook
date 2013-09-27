gitpic-hook
===========

A git post-commit hook for uploading photos to [gitpic](http://www.gitpic.io)

What is gitpic.io?
==================

[gitpic.io](http://www.gitpic.io) is a fun, free website where you can watch code happen.
Every developer who installs this post-commit hook will upload photos directly to [gitpic.io](http://www.gitpic.io) after every commit.

How to install:
===============

1. Clone this repository.

        git clone https://github.com/venables/gitpic-hook.git

2. Copy your gitpic API key to your local machine.  You can get your API key by signing in to http://www.gitpic.io.

        touch ~/.gitpic-api-key
        echo "API_KEY_FROM_GITPIC" > ~/.gitpic-api-key

3. Install imagesnap

        brew install imagesnap

4. Follow [these instructions](https://coderwall.com/p/jp7d5q) on how to make a global git post-commit hook:

    > 1. Enable git templates:

    >         git config --global init.templatedir '~/.git-templates'

    >   This tells git to copy everything in `~/.git-templates` to your per-project `.git/` directory when you run `git init`

    > 2. Create a directory to hold the global hooks:

    >         mkdir -p ~/.git-templates/hooks

    > 3. Write your hooks in `~/.git-templates/hooks`.

    >   For gitpic, do the following:

    >         touch ~/.git-templates/hooks/post-commit
    >         echo "#!/bin/sh" >> ~/.git-templates/hooks/post-commit
    >         echo "CLONED_REPOSITORY_PATH/gitpic" >> ~/.git-templates/hooks/post-commit

    >   **NOTE:** You must change CLONED_REPOSITORY_PATH to where you cloned this repository

    > 4. Make sure the hook is executable.

    >         chmod a+x ~/.git-templates/hooks/post-commit

    > 5. Re-initialize git in each existing repo you'd like to use this in:

    >         git init

    >   **NOTE:** if you already have a hook defined in your local git repo, this will not overwrite it. You'll have to remove that file and run `git init` again
