# Add a plugin

```JavaScript
var gulp = require('gulp'),
    create = require('gulp-create'),
    plugin = require('gulp-cordova-plugin');

gulp.task('create', function() {
    return gulp.src('dist')
        .pipe(create())
        .pipe(plugin('org.apache.cordova.file'))
        .pipe(plugin('org.apache.cordova.inappbrowser'));
});
```

This will add two plugins to the cordova project.

The [`gulp-cordova-plugin`](https://github.com/SamVerschueren/gulp-cordova-plugin) plugin expects a cordova project as source. So it's perfectly valid to have the following tasks.

```JavaScript
var gulp = require('gulp'),
    create = require('gulp-create'),
    plugin = require('gulp-cordova-plugin');

gulp.task('create', function() {
    return gulp.src('dist')
        .pipe(create());
});

gulp.task('plugin', ['create'], function() {
    return gulp.src('.cordova')
        .pipe(plugin('org.apache.cordova.file'))
        .pipe(plugin('org.apache.cordova.inappbrowser'));
});
```

When running the `plugin` task, it will first create the cordova project by using the `dist` directory as source of the application. When the project is created, it will take the `.cordova` folder and adds the two plugins to the project.
