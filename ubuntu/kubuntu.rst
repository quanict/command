Install the KDE Plasma Desktop on Ubuntu 18.04 LTS
==================================================

Step1: Install Tasksel; a prerequisite for installing Kubuntu
-------------------------------------------------------------
..code :: bash

    sudo apt install tasksel


Step 2: Install Kubuntu Desktop
-------------------------------
..code :: bash

    sudo tasksel install kubuntu-desktop

Package Configuration manager
.............................
..code :: bash

    sudo dpkg-reconfigure sddm