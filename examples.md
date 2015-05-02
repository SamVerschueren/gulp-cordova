# Examples

- [Create a cordova project](#create-a-cordova-project)
- [Add a plugin](#add-a-plugin)
- [Build a project](#build-a-project)
    - [Android](#android)

## Create a cordova project

```JavaScript
var gulp = require('gulp'),
    create = require('gulp-cordova-create');

gulp.task('create', function() {
    return gulp.src('dist')
        .pipe(create());
});
```

By default, the [`gulp-cordova-create`](https://github.com/SamVerschueren/gulp-cordova-create) plugin will create a `.cordova` directory with your cordova project. You can change this by passing some options to the plugin.

```JavaScript
var gulp = require('gulp'),
    create = require('gulp-create');

gulp.task('create', function() {
    return gulp.src('dist')
        .pipe(create({directory: 'myproject', id: 'com.myproject.hello', name: 'MyProject'}));
});
```

This will create a `myproject` directory with a cordova project with the id `com.myproject.hello` and with the name `MyProject`. The contents of the `dist` folder will be copied to the `www` folder of the cordova project.

## Add a plugin

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

## Build a project

### Android

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
        .pipe(android())
        .pipe(gulp.dest('builds'));
});
```

This will build the cordova project for android and stores the debug apk in the `builds` directory. It's also possible to sign the
apk by padding some options to the plugin. Have a look at [gulp-cordova-build-android](https://github.com/SamVerschueren/gulp-cordova-build-android)
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

gulp.task('android', ['plugin'], function() {
    return gulp.src('.cordova')
        .pipe(android())
        .pipe(gulp.dest('builds'));
});
```

If you run the `android` task, it will first run the `plugin` task which on his turn will first run the
`create` task.