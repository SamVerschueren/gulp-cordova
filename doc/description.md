# Set project description

The `config.xml` file consists of all the information regarding the cordova project. The description of the cordova project is also
defined in here.

This small and easy-to-use [`plugin`](https://github.com/SamVerschueren/gulp-cordova-description) sets the description in the `config.xml` file.

## Usage

```JavaScript
var gulp = require('gulp'),
    create = require('gulp-create'),
    description = require('gulp-cordova-description');

gulp.task('create', function() {
    return gulp.src('dist')
        .pipe(create())
        .pipe(description('This is the description of my project'));
});
```

This will set the description in the `config.xml` file.

```xml
<description>This is the description of my project</description>
```

## Plugin I/O

The plugin expects a cordova project folder as input file and passes the same cordova project folder as output file to the next
plugin. This makes it perfectly valid to define the tasks like this.

```JavaScript
var gulp = require('gulp'),
    create = require('gulp-create'),
    description = require('gulp-cordova-description');

gulp.task('create', function() {
    return gulp.src('dist')
        .pipe(create());
});

gulp.task('description', ['create'], function() {
    return gulp.src('.cordova')
        .pipe(description('This is the description of my project'));
});
```

When you run the `description` task, it will first run the `create` task and uses the created cordova project as input for the
description plugin.
