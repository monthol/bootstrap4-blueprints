# bootstrap4-blueprints
Migrating the dinosaur js to Bootstrap framework


#### Initiate npm for the project
make entry point to ```Gulpfile.js``` and test command to ```gulp test```.
```
>> npm init
```
This will create package.json

#### Installing Gulp
```
>> npm install --save-dev gulp
```
#### Create Gulpfile.js with default task.
```
var gulp = require('gulp'); 
 
gulp.task('default', function() { 
  // place default task here 
});
```
Here I couldn't test with ```gulp```, [SO](https://stackoverflow.com/questions/22224831/after-installation-of-gulp-no-command-gulp-found) said ```gulp-cli``` is required. Instead gulp can be invoked by placing ```scripts``` in ```package.json``` file and run ```>> npm run gulp```
```
{
    "name": "your-app",
    "version": "0.0.1",
    "scripts": {
        "gulp": "gulp",
        "minify": "gulp minify"
    }
}
```
#### install ```rimraf``` for cleaning tasks and ```gulp-environment```
```
>>npm install rimraf --save-dev”
>>npm install --save-dev gulp-environments
```
#### Install Bootstrap with Bower
```
>>bower init
>>bower install bootstrap#4 --save-dev
```
Here comes the error since XCode was uninstalled.
```
Additional error details:
xcrun: error: active developer path ("/Applications/Xcode.app/Contents/Developer") does not exist
Use `sudo xcode-select --switch path/to/Xcode.app` to specify the Xcode that you wish to use for command line developer tools, or use `xcode-select --install` to install the standalone command line developer tools.
See `man xcode-select` for more details.
```
The work around is to install only the command line tool
```
>> xcode-select --install
```
Now see the current active developer path
```
>> xcode-select p
```
Switch active developer path to the new command line tools, from [here](https://stackoverflow.com/questions/11456918/change-xcrun-developer-path)
```
>> sudo xcode-select --switch /Library/Developer/CommandLineTools
```

