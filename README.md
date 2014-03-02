RedKite CMS Sandbox
===================
Welcome to RedKite CMS Sandbox - a fully-functional Symfony2 application powered by 
RedKite CMS. You can use this application as skeleton for your new project or to test 
the CMS itself.

This document contains information on how to download and to start using RedKite CMS.

[![Build Status](https://secure.travis-ci.org/redkite-labs/RedKiteCmsSandbox.png)](http://travis-ci.org/redkite-labs/RedKiteCmsSandbox)

Before starting
---------------
This repository houses the RedKite CMS Sandbox and requires to install vendor libraries 
and then the CMS itself and it is the right place to start if you would like to contribute 
to RedKite CMS project.

If you just want to try something ready, have a look to the [Get & Go Sandbox](http://redkite-labs.com/download-get-and-go-redkite-cms-sandbox),
ideal to have a quick try the application and perfect to be used by a single developer, or
to the [RedKite CMS Sandbox](http://redkite-labs.com/download-redkite-cms-sandbox) which has the
required vendor libraries installed. Follow the links to have more details about those products.


Install RedKite CMS Sandbox
---------------------------
The quick way to install RedKite CMS Sandbox is to use composer, so get it running
the following command:

    curl -s http://getcomposer.org/installer | php

then run the following command to get the latest RC:

    php composer.phar create-project redkite-labs/redkite-cms-sandbox -s stable RedKiteCmsSandbox 1.1.1 --no-dev

or run this one to get the develop branch:

    php composer.phar create-project redkite-labs/redkite-cms-sandbox -s dev RedKiteCmsSandbox

Alternatively you can download the latest release from releases page:

    https://github.com/redkite-labs/RedKiteCmsSandbox/releases

then move to the root folder and grab composer as explained at the beginning of this paragraph 
and run this command to install the required vendor libraries:

    php composer.phar install


RedKite CMS setup
-----------------
RedKite CMS requires several steps to be accomplished to properly setup the CMS itself. Luckily
the **RedKiteCmsInstallerBundle** will do all the job for you. 

This bundle provides a web installer interface or an interactive symdony2 command to install 
RedKite CMS.

Permissions
-----------
Before starting you must be sure that following folders and files are writable:

    app/cache
    app/logs
    app/config
    web
    app/AppKernel.php
    app/config/config.yml
    app/config/routing.yml
    app/config/parameters.yml
 
because RedKite CMS installer will update them for you. If you prefer to setup RedKite CMS manually just
follow this guide: http://redkite-labs.com/how-to-install-redkite-cms.

The best way to set up you permissions is using ACL:

    sudo setfacl -R -m u:www-data:rwx -m u:[USERNAME]:rwx *
    sudo setfacl -dR -m u:www-data:rwx -m u:[USERNAME]:rwx *

To get more details, please refer to the [symfony2 setup and configuration tutorial](http://symfony.com/doc/current/book/installation.html#configuration-and-setup)


Installing from the console
---------------------------
Installing RedKite CMS from the console is really easy:

    app/console redkitecms:configure

This will run the interactive command and provide the required information. If everything goes well,
you will be prompted that the configuration has been written and you ready to start the install. Run
the following command from the console:
    
    app/console redkitecms:install --env=rkcms

When the setup ends, point your browser at

    http://localhost/rkcms.php/backend/login

to start using RedKite CMS.


Installing using the web interface
----------------------------------
To install RedKite CMS using the web interface, just point your browser at:

    http://localhost/app_dev.php/install

Provide the required information and you are done! 


Using another database intead of mysql, postgres, sqlite
--------------------------------------------------------

Please refer [this document](http://redkitelabs/rkcms_dev.php/backend/en/download-redkite-cms-sandbox#use-another-database-instead-of-mysql-postgres-or-sqlite) to use a database different than mysql, postgres or sqlite.

Sign in
-------
RedKite CMS is secured by default and a new user is created when the application is 
installed:

    username: admin
    password: admin

enter the credentials above to sign in.


Documentation
-------------
Although RedKite CMS is designed to be as simple and intuitive as possible, you probably 
would like to go deeper, reading some documentation:

- [The book](http://redkite-labs.com/getting-started-with-redkite-cms)
- [The cookbook](http://redkite-labs.com/redkite-cms-practical-manual-part-1)
- [Developers guide](http://redkite-labs.com/getting-started-contributing-to-redkite-cms)

RedKite CMS [documentation repository](https://github.com/redkite-labs/redkitecms-docs)
lives at github.


Support
-------
If you require support you can ask for help at [RedKite CSM users forum](https://groups.google.com/forum/?hl=it#!forum/redkitecms-users).

If you want to collaborate, just introduce yourself at [RedKite CSM developers forum](https://groups.google.com/forum/?hl=it#!forum/redkitecms-dev).


Stay in touch
-------------
RedKite CMS is present on major social networks:

Follow [@redkite-cms on Twitter](https://twitter.com/redkitecms) for the latest news

Like RedKite CMS at [Facebook](https://www.facebook.com/redkitecms)

Connect with RedKite CMS at [Google+](https://plus.google.com/103994964006724386514)


Notes for windows users
-----------------------
RedKite CMS has been written on a linux system machine, so you might encounter some small issues when
you work on a windows machine:

- assetic:dump command might return an error
- Skin problems

None of those problems breaks the usability of RedKite CMS. If you are a windows user and you want
to fix them on your own, fork the repository, do the fixes then ask for a pull request: it would be really
appreciated! :)

Enjoy!
