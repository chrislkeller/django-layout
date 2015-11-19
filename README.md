Django Project Template
=======================

This Django Project Template provides some defaults for new KPCC Django projects. It is based on [django-layout](https://github.com/lincolnloop/django-layout).

To use this template, run the following command:

    django-admin.py startproject --template=https://github.com/chrislkeller/django-layout/zipball/master --extension=py,rst,gitignore,example {{ project_name }}

Quickstart
==========

**To bootstrap the project**:

* This assumes you have Django 1.8 and Fabric installed outside of your virtualenv(s).

* Rename ```config.yml.template``` to ```config.yml``` and ```development.yml.template``` to ```development.yml```

* Open ```development.yml``` and add the name of your project as the database name on line 17.

        database:
          host: "127.0.0.1"
          port: 3306
          database: "project_name"
          username: "root"
          password: ""

* Run ```fab bootstrap```
    * This attempts to scaffold the project by:
        * Creating virtualenv
        * Activating the virtualenv
        * Installing requirements
        * Creating the database
        * Applyin initial Django migrations
        * Creating the Django superuser
        * Running the Django development server

**Available Fabric Commands**:

* ```fab run```
    * Launches the Django development server

* ```fab make```
    * Creates Django database migrations

* ```fab migrate```
    * Applies Django database migrations

* ```fab requirements```
    * Installs Python packages from requirements.txt file

* ```fab create_db```
    * Creates a database based on DATABASE variables in ```settings_development.py``` file

* ```fab bootstrap```
    * Attempts to scaffold the project by:
        * Create virtualenv
        * Activates the virtualenv
        * Installs requirements
        * Creates the database
        * Applies initial Django migrations
        * Creates the Django superuser
        * Runs the Django development server

* ```fab build```
    * Activates the django-bakery script to build the views specified in ```settings_development.py```

* ```fab buildserver```
    * Activates the django-bakery development server

* ```fab commit```
    * Commits and pushes to the version control repo

**Documentation**:

* Developer documentation is available in Sphinx format in the docs directory.
* Initial installation instructions (including how to build the documentation as
HTML) can be found in docs/install.rst.
