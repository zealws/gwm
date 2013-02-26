Git Workspace Manager
=====================

`gwm` is a tool for managing multiple git repositories. It allows you to run git and shell commands in groups of repositories, rather than running a command separately in each repository.

Usage
-----

    » gwm
    Usage:
        gwm command
        gwm options command
    
        options:
            -s
                Execute a shell command, rather than a git command.
            -w DIR
                Set the workspace location.
            -h, --help
                Print this help message and exit.
            --
                Signifies the end of options. Any arguments after this point are
                treated as part of the command.
    
        Set the WORKSPACE variable to change the default workspace location.
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
        # Untracked files:
        #   (use "git add <file>..." to include in what will be committed)
        #
        #	my file
        nothing added to commit but untracked files present (use "git add" to track)

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
        
            Updated gwm to sed stderr as well as stdout, and filter git repos correctly. Updated README with general description.

    » gwm checkout -b new_branch
    DbMigrations
        Switched to a new branch 'new_branch'
    gwm
        Switched to a new branch 'new_branch'

    » gwm checkout master
    DbMigrations
        Switched to branch 'master'
    gwm
        Switched to branch 'master'

    » gwm branch -d new_branch
    DbMigrations
        Deleted branch new_branch (was 034acf9).
    gwm
        Deleted branch new_branch (was e40fc7f).

### Shell Commands:

    » gwm -s pwd
    DbMigrations
        /Users/freud/workspace/DbMigrations
    gwm
        /Users/freud/workspace/gwm

    » gwm -s ls
    DbMigrations
        README.md
        dbmigrations
        setup.py
    gwm
        README.md
        gwm
        my file

