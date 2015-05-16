# Set preferences

Via the `config.xml` file, a developer can adjust the behaviour of an application on each platform. For `android` for example , you
can find the preferences [here](http://cordova.apache.org/docs/en/5.0.0/guide_platforms_android_config.md.html#Android%20Configuration).

It's also possible to set or overwrite preferences in the config file with the [`gulp-cordova-preference`](https://github.com/SamVerschueren/gulp-cordova-preference)
plugin.

## Usage

The plugin can be used in two ways. The first way is via a key-value pair, the second way is via an object.

### Key-value pair method

With this method, the plugin expects two parameters. The first parameter is the key or the name of the preference, the second
parameter is the value of the preference. You can chain multiple calls to the plugin after eachother.

```JavaScript
var gulp = require('gulp'),
    create = require('gulp-create'),
    pref = require('gulp-cordova-preference');

gulp.task('create', function() {
    return gulp.src('dist')
        .pipe(create())
        .pipe(pref('KeepRunning', false))
        .pipe(pref('LogLevel', 'VERBOSE'));
});
```

This will add the following tags to the `config.xml` file.

```xml
<preference name="KeepRunning" value="false" />
<preference name="LogLevel" value="VERBOSE" />
```

### Object method

If you have a lot of preferences to set, it might be better to use the object method. This method only provides one object
to the plugin where the key of each property is the name of the preference and the value is the value of the preference.

The same example can also be written like this.

```JavaScript
var gulp = require('gulp'),
    create = require('gulp-create'),
    pref = require('gulp-cordova-preference');

gulp.task('create', function() {
    return gulp.src('dist')
        .pipe(create())
        .pipe(pref({
			KeepRunning: false,
			LogLevel: 'VERBOSE'
		}));
});
```

A good thing to notice is that every time the `gulp-cordova-preference` plugin is called, the `config.xml` file is parsed. Because
of this, the object method is a great advantage over the key-value pair method because with the object method, the config file will
only be parsed once.

The benefit of using this approach is that every time the plugin is called, the `config.xml` file will be parsed.

## Plugin I/O

The plugin expects a cordova project folder as input file and passes the same cordova project folder as output file to the next
plugin. This makes it perfectly valid to define the tasks like this.

```JavaScript
var gulp = require('gulp'),
    create = require('gulp-create'),
    pref = require('gulp-cordova-preference');

gulp.task('create', function() {
    return gulp.src('dist')
        .pipe(create());
});

gulp.task('preference', ['create'], function() {
    return gulp.src('.cordova')
        .pipe(pref({
			KeepRunning: false,
			LogLevel: 'VERBOSE'
		}));
});
```

When you run the `preference` task, it will first run the `create` task and uses the created cordova project as input for the
preference plugin.
