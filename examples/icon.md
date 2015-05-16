# Add an icon

It's only possible to use `png` images as icon. If you use any other type of image, it will throw an error.

```JavaScript
var gulp = require('gulp'),
    create = require('gulp-create'),
    plugin = require('gulp-cordova-plugin'),
    icon = require('gulp-cordova-icon');

gulp.task('create', function() {
    return gulp.src('dist')
        .pipe(create())
        .pipe(plugin('org.apache.cordova.file'))
        .pipe(plugin('org.apache.cordova.inappbrowser'))
        .pipe(icon('res/icon.png'));
});
```

This will not do much on itself. What happens is that this plugin will install a hook script that will generate the correct
icons right before the requested platform is built.

The plugin expects a cordova project as input.

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

gulp.task('icon', ['plugin'], function() {
    return gulp.src('.cordova')
        .pipe(icon('res/icon.png'));
});

gulp.task('build', ['icon']);
```

When running the `build` task, it will execute the `icon` task wich will first execute the `plugin` task which on his turn will
first execute the `create` task.