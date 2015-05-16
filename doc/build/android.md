# Android

```JavaScript
var gulp = require('gulp'),
    create = require('gulp-create'),
    plugin = require('gulp-cordova-plugin'),
    android = require('gulp-cordova-android');

gulp.task('create', function() {
    return gulp.src('dist')
        .pipe(create())
        .pipe(plugin('org.apache.cordova.file'))
        .pipe(plugin('org.apache.cordova.inappbrowser'))
        .pipe(icon('res/icon.png'))
        .pipe(android())
        .pipe(gulp.dest('builds'));
});
```

This will build the cordova project for android and stores the debug apk in the `builds` directory. It's also possible to sign the
apk by adding some options to the plugin. Have a look at [gulp-cordova-build-android](https://github.com/SamVerschueren/gulp-cordova-build-android)
for more information.

The plugin expects a cordova project as source. So the following tasks will work perfectly.

```JavaScript
var gulp = require('gulp'),
    create = require('gulp-create'),
    plugin = require('gulp-cordova-plugin'),
    android = require('gulp-cordova-android');

gulp.task('create', function() {
    return gulp.src('dist')
        .pipe(create());
});

gulp.task('plugin', ['create'], function() {
    return gulp.src('.cordova')
        .pipe(plugin('org.apache.cordova.file'))
        .pipe(plugin('org.apache.cordova.inappbrowser'));
});

gulp.task('icon', ['plugin'], function() {
    return gulp.src('.cordova')
        .pipe(icon('res/icon.png'));
});

gulp.task('android', ['icon'], function() {
    return gulp.src('.cordova')
        .pipe(android())
        .pipe(gulp.dest('builds'));
});

gulp.task('build', ['android']);
```

If you run the `android` task, it will first run the `icon` task, which will run the `plugin` task which on his turn will first run the
`create` task.
