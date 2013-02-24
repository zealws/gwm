Git Workspace Manager
=====================

`gwm` is a tool for managing multiple git repositories. It allows you to run git and shell commands in groups of repositories, rather than running a command separately in each repository.

Usage
-----

    Usage:
        gwm git-command
            Run a git command on all git repositories in the workspace.
        gwm ! shell-command
            Run a shell command on all git repositories in the workspace.
    
        Set the WORKSPACE variable to change the workspace location.

Setup
-----

Simply set the WORKSPACE environment variable to point to your workspace.

    » echo $WORKSPACE
    /Users/freud/workspace

Examples
--------

### Git Commands:

    » gwm status
    DbMigrations
        # On branch master
        nothing to commit (working directory clean)
    gwm
        # On branch master
        nothing to commit (working directory clean)

    » gwm log -1
    DbMigrations
        commit 034acf91e5c0677e57f479429de86af91d98d22a
        Author: zeal <zealjagannatha@gmail.com>
        Date:   Sun Feb 24 04:10:00 2013 -0800
        
            Removed build.xml
    gwm
        commit e40fc7f23bda2d207b6f7899d02d0c61732dfbfa
        Author: zfjagann <zealjagannatha@gmail.com>
        Date:   Sun Feb 24 04:25:10 2013 -0800
        
            Updated gwm to sed stderr as well as stdout, and filter git repos correctly...

    » gwm checkout -b new_branch
    DbMigrations
        Switched to a new branch 'new_branch'
    gwm
        Switched to a new branch 'new_branch'

    » gwm branch -d new_branch
    DbMigrations
        Deleted branch new_branch (was a4eb858).
    gwm
        Deleted branch new_branch (was a538409).

### Shell Commands:

    » gwm ! pwd
    DbMigrations
        /Users/freud/workspace/DbMigrations
    gwm
        /Users/freud/workspace/gwm

    » gwm ! ls 
    DbMigrations
        README.md
        build.xml
        dbmigrations
        setup.py
    gwm
        README.md
        gwm
