Installer module
================

A PW module to install other PW modules.


Rationale
---------

Whilst PW already supports the 'installs' parameter for modules each of the modules it installs must also be visible
in the GUI. This means that with a subdirectory with a set of modules (such as Apeisa's Shopping Cart) package all of
the modules are initially visible in the modules GUI and the user then either has to install them one-by-one or
correctly pick the 'master' module which has the installs list.

I like my packages to have just a single module visible in the UI (this module here) and that this module will
install its UI-invisible siblings when it is installed. The Installer should also delete itself from the filesystem
and UI if it is successful.

This method means the user is presented with a simple choice when installing a package, rather than a complex one.


Usage
-----

1. **Mandatory:** Rename all the modules you want this module to install from .module to .module.php files and place
them all in a common directory along with a copy of this module file.
2. *Optional but recommended:* If your project delivers, say, an SMS sending package of modules then...

- rename 'Installer.module' to 'SmsInstaller.module'
- edit the file and change the class from 'Installer' to 'SmsInstaller'
- update the 'title' and 'description' fields in the getModuleInfo() method

3. **Madatory:** Zip up or otherwise deliver the entire directory to your users.

Once a user places the directory in their site/modules folder and gets PW to check for new modules, the user will
see only  the 'Installer' module. When they install this module all the other modules will get installed and the
'Installer' will be gone.


Copyright
---------

Copyright 2014 Stephen Dickinson, QBox.
