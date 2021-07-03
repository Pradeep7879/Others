# Others
LESS and SCSS compile

---------------------------------------------------------------------------**Stylesheets**--------------------------------------------------------------------------

If you are using Less as CSS preprocessor. As Drupal 8 doesn’t have a nice less or scss compiler build in, or a nice module for this (correct me if there is a new module out there), we need to compile the files locally.
I can recommend the plugin **Easy Compile** for **Visual Studio Code**, with the following settings:

**Add below code** in **composer.json** file which is provided by **Easy Compile** by **visual studio code**:-

---------------------------------------------------
"easycompile.compile": {
   "minifyCssOnSave": false,
   "sass": true,
   "less": true,
 },
 "easycompile.sass": {
   "compress": true,
   "sourceMap": true,
   "autoprefixer": "> 1%, not ie 6-9",
   "groupmedia": true,
   "out": false,
 },
 "easycompile.less": {
   "compress": true,
   "sourceMap": true,
   "autoprefixer": "> 1%, not ie 6-9",
   "relativeUrls": true,
   "out": false,
 },
 --------------------------------------------------
 
 This make easy to compile SASS and LESS no need to npm and other module or tool.
 on visual studio code you save the code it automatically compile.
 
------------------------------------------------------------------------------------------------------------------------------------------------------------------

--------------------------**Javascript**---------------------

context in drupal.behaviour.mymoduleBehaviour
The context is the piece of the DOM that has been rendered before Drupal.behaviors are invoked.


-----------------------------------------------------------------------------------------------------------------------------------------------------------------

**Error with Kint of max-level, when you kint the variable.**

Add this to the end of your settings.php or settings.local.php.
If you're putting it in settings.local.php also make sure that settings.local.php is included from within your settings.php.
Make sure to rebuild your cache after that (drush cr).

// Include Kint class.
include_once(DRUPAL_ROOT . '/modules/contrib/devel/kint/kint/Kint.class.php');

// If debugging is very slow or leads to WSOD reduce the number
// of levels of information shown by Kint.
// Change Kint maxLevels setting:
if (class_exists('Kint')){
  // Set the maxlevels to prevent out-of-memory. Currently there doesn't seem to be a cleaner way to set this:
  Kint::$maxLevels = 4;
}
