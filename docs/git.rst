
GIT - distributed version-control system
========================================

Config
------

Get
...

.. code :: bash

    git config --get remote.origin.url

Set
...

.. code :: bash

    git remote set-url origin https://github.com/USERNAME/REPOSITORY.git


Caching
-----------------------------------

Caching your GitHub password in Git
...................................
.. code :: bash

    git config --global credential.helper cache


Remove
------

Remove Directory
................

.. code :: bash

    git rm --cached mylogfile.log

Remove file
...........
.. code :: bash

    git rm --cached -r mydirectory

Remove branch
.............
.. code :: bash

    git branch -d branch_name
    git branch -D branch_name

Delete a remote GIT branch
..........................
.. code :: bash
    
    git push <remote_name> --delete <branch_name>

Reset
-----

Delete the most recent commit
............................
.. code :: bash
    
    git reset --hard HEAD~1

Delete the most recent commit, without destroying the work you've done
.................................
.. code :: bash
    
    git reset --soft HEAD~1
