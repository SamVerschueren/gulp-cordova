# gulp-cordova

`gulp-cordova` is not a single library that takes care of everything, it is a bundle of multiple libraries
that each leverage a different task in the chain of creating cordova projects.

Like many others, these libraries are build with ```code over configuration``` kept in mind.

## Examples

The first example creates a cordova project, adds two plugins and copies the contents of the ```dist``` directory
to the ```www``` directory of the cordova project. In the end, it builds the project for the Android platform.

```JavaScript
var gulp = require('gulp'),
    create = require('gulp-cordova-create'),
    plugin = require('gulp-cordova-plugin'),
    android = require('gulp-cordova-build-android');

gulp.task('build', function() {
    return gulp.src('dist')
        .pipe(create())
        .pipe(plugin('org.apache.cordova.file'))
        .pipe(plugin('org.apache.cordova.inappbrowser'))
        .pipe(android());
});
```

The cordova project is by default created in the ```.cordova``` directory.

## Plugins

1. [gulp-cordova-create](https://github.com/SamVerschueren/gulp-cordova-create)
    - Create a cordova project
2. [gulp-cordova-plugin](https://github.com/SamVerschueren/gulp-cordova-plugin)
    - Add a plugin to your cordova project
3. [gulp-cordova-build-android](https://github.com/SamVerschueren/gulp-cordova-build-android)
    - Build the cordova project for the Android platform.
4. [gulp-cordova-build-ios](https://github.com/SamVerschueren/gulp-cordova-build-ios)
    - Build the cordova project for the iOS platform.
5. [gulp-cordova-build-bb10](https://github.com/SamVerschueren/gulp-cordova-build-bb10)
    - Build the cordova project for the BlackBerry 10 platform.

These plugins will become available in the near future

1. gulp-cordova-build-wp8
    - Build the cordova project for the Windows Phone platform
2. gulp-cordova-build
    - General builder that can be used for any platform

## Author

Sam Verschueren [<sam.verschueren@gmail.com>]
