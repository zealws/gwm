Git Workspace Manager
=====================

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
        commit a4eb8581951cc629086f32a463926a6b32f6f574
        Author: zeal <zealjagannatha@gmail.com>
        Date:   Thu Feb 21 21:12:04 2013 -0800
        
            Updated build.xml pt2
    gwm
        commit a53840985ae5b766124dd904cc30d6e5b440f231
        Author: zeal <zeal@skybox.com>
        Date:   Sun Feb 24 03:42:34 2013 -0800
        
            Added simple readme and script.

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
