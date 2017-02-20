# Set author

The `config.xml` contains the information regarding the author. This information consists of the author's name, email address and
website.

This small and easy-to-use [`plugin`](https://github.com/SamVerschueren/gulp-cordova-author) sets the author in the `config.xml` file.

## Usage

```JavaScript
var gulp = require('gulp'),
    create = require('gulp-create'),
    author = require('gulp-cordova-author');

gulp.task('create', function() {
    return gulp.src('dist')
        .pipe(create())
        .pipe(author('Sam Verschueren'));
});
```

This will only set the name of the author.

```xml
<author>Sam Verschueren</author>
```

You can set the email and the author's website as well.

```JavaScript
var gulp = require('gulp'),
    create = require('gulp-create'),
    author = require('gulp-cordova-author');

gulp.task('create', function() {
    return gulp.src('dist')
        .pipe(create())
        .pipe(author('Sam Verschueren', 'sam.verschueren@gmail.com', 'https://github.com/samverschueren'));
});
```

This will result in the following `xml` tag.

```xml
<author email="sam.verschueren@gmail.com" href="https://github.com/samverschueren">
	Sam Verschueren
</author>
```

## Plugin I/O

The plugin expects a cordova project folder as input file and passes the same cordova project folder as output file to the next
plugin. This makes it perfectly valid to define the tasks like this.

```JavaScript
var gulp = require('gulp'),
    create = require('gulp-create'),
    author = require('gulp-cordova-author');

gulp.task('create', function() {
    return gulp.src('dist')
        .pipe(create());
});

gulp.task('author', ['create'], function() {
    return gulp.src('.cordova')
        .pipe(author('Sam Verschueren', 'sam.verschueren@gmail.com', 'https://github.com/samverschueren'));
});
```

When you run the `author` task, it will first run the `create` task and uses the created cordova project as input for the
author plugin.
