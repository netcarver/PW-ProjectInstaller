Multi Module Installer
======================

A PW module to neatly install a __set__ of PW modules whilst keeping the UI uncluttered.


Rationale
---------

Whilst PW already supports the 'installs' parameter for modules, each of the modules it installs will also be visible
in the UI. This means that a subdirectory with a set of modules to be installed (such as Apeisa's Shopping Cart) all of
the modules are initially visible in the modules UI and the user then either has to install them one-by-one or
correctly pick the 'master' module which contains the installs list.

I like my packages to have just a single module visible in the UI (that's this module here) and this module will
install its UI-invisible siblings when it is installed. The Installer then also deletes itself from the filesystem
and UI if it is successful.

In effect, this method means the user is presented with a simple choice when installing a package, rather than a complex one.


Usage
-----

1. **Mandatory:** Rename all the modules you want this module to install from .module to .module.php files and place
them all in a common directory along with a copy of this module file.
2. *Optional but recommended:* If your project delivers, say, an SMS sending package of modules then...
Firstly; rename 'Installer.module' to 'SmsInstaller.module'. Secondly; edit the file and change the class from
'Installer' to 'SmsInstaller'. Lastly; update the 'title' and 'description' fields in the getModuleInfo() method.
3. **Madatory:** Zip up or otherwise deliver the entire directory to your users.

Once a user places the directory in their site/modules folder and gets PW to check for new modules, the user will only
see the renamed 'Installer' module. When they install it all the other modules will get installed and the 'Installer'
will be gone.


Copyright
---------

Copyright 2014 Stephen Dickinson, QBox.


License
-------

This module is released under the GPLv2 License. See the LICENSE file for more details.
