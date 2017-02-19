# Create a cordova project

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
    create = require('gulp-cordova-create');

gulp.task('create', function() {
    return gulp.src('dist')
        .pipe(create({dir: 'myproject', id: 'com.myproject.hello', name: 'MyProject'}));
});
```

This will create a `myproject` directory with a cordova project with the id `com.myproject.hello` and with the name `MyProject`. The contents of the `dist` folder will be copied to the `www` folder of the cordova project.
