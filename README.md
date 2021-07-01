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
