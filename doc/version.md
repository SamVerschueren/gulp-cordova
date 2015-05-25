# Set project version

Every application consists of a version number. For cordova application, the version number is configured in the `config.xml` file. 
This small and easy-to-use plugin will set the version number in the `config.xml` file.

## Usage

```JavaScript
var gulp = require('gulp'),
    create = require('gulp-create'),
    version = require('gulp-cordova-version');

gulp.task('create', function() {
    return gulp.src('dist')
        .pipe(create())
        .pipe(version('2.3.15'));
});
```

The start of the `config.xml` file will then look like this.

```xml
<widget id="io.cordova.hellocordova" version="2.3.15" xmlns="http://www.w3.org/ns/widgets" xmlns:cdv="http://cordova.apache.org/ns/1.0">
```

Because the `package.json` file also has a version number, it's a nice idea to use that version number as your application version as well. If you
bump your `package.json` version, it will automatically reflect that to the version of the build.

```JavaScript
var gulp = require('gulp'),
    create = require('gulp-create'),
    version = require('gulp-cordova-version'),
    pkg = require('./package.json');

gulp.task('create', function() {
    return gulp.src('dist')
        .pipe(create())
        .pipe(version(pkg.version));
});
```

## Plugin I/O

The plugin expects a cordova project folder as input file and passes the same cordova project folder as output file to the next
plugin. This makes it perfectly valid to define the tasks like this.

```JavaScript
var gulp = require('gulp'),
    create = require('gulp-create'),
    version = require('gulp-cordova-version');

gulp.task('create', function() {
    return gulp.src('dist')
        .pipe(create());
});

gulp.task('version', ['create'], function() {
    return gulp.src('.cordova')
        .pipe(version('2.3.15'));
});
```

When you run the `version` task, it will first run the `create` task and uses the created cordova project as input for the
description plugin.