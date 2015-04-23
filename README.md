# gulp-cordova

```gulp-cordova``` is not a single library that takes care of everything, it is a bundle of multiple libraries
that each leverage a different task in the chain of creating cordova projects.

Like many others, these libraries are build with ```code over configuration``` kept in mind.

## Examples

The first example creates a cordova project, adds two plugins and copies the contents of the ```dist``` directory
to the ```www``` directory of the cordova project.

```JavaScript
var gulp = require('gulp'),
    create = require('gulp-cordova-create'),
    plugin = require('gulp-cordova-plugin');

gulp.task('build', function() {
    return gulp.src('dist')
        .pipe(create())
        .pipe(plugin('org.apache.cordova.file'))
        .pipe(plugin('org.apache.cordova.inappbrowser'));
});
```

## Plugins

1. [gulp-cordova-create](https://github.com/SamVerschueren/gulp-cordova-create)
    - Create a cordova project
2. [gulp-cordova-plugin](https://github.com/SamVerschueren/gulp-cordova-plugin)
    - Add a plugin to your cordova project

## Author

Sam Verschueren [<sam.verschueren@gmail.com>]
