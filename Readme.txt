################################################################################
# JAZMVC                                                                       #
# Version 1.0.0                                                                #
# June 2014                                                                    #
################################################################################

JAZMVC is a A lightweight, directory based Model View Controller library for PHP 
with MySQL database connection and HTML builder methods.

It is driven by url path variables, so if your url is

 * http://yoursite.com/foo/bar

The 'foo' controller will be used, and the 'bar' method of the 'foo' controller
will be called.  The default directory structure is as follows, but this can be
modified via the config file.

*** In the site's root directory ***

.htaccess - Apache mod rewrite instructions to make MVC work

index.php - this file 'drives' everything.  Initializing the JAZMVC class, resolving views, etc.

lib - the root directory of library files

 -> JAZMVC.php - the class that contains library methods to 'drive' the MVC
 
 -> config.inc.php - the configuration file for JAZMVC
 
 -> db_mysql_v2.inc.php - MySQL database connection library (optional)
 
 -> Controller - directroy for controller classes
   -> Controller.php - BaseController class that other controllers inherit from
   -> Main.Controller.php - default controller (no path vars)
   -> other controllers of the format Foo.Controller.php
 
 -> Model - directory for model classes
   -> Model.php - BaseModel class that other models inherit from
   -> other models of the format Object.Model.php
 
 -> View - directory for view files
   -> View.php - View class that encapsulates view definition data
   -> Definitions.php - View definitions
   -> other view directories and files
   
 -> Service - directory for service classes
   -> Security.php - Special file for code that runs before the MVC does, 
                     such as security checks.
   -> Other service classes