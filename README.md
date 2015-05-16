# gulp-cordova documentation

`gulp-cordova` is not a single library that takes care of everything, it is a bundle of multiple libraries
that each leverage a different task in the chain of creating cordova projects.

Like many others, these libraries are build with ```code over configuration``` kept in mind.

## Important

This entire project is still in beta. I'm working hard to deliver more plugins and to make the existing plugins
bugfree. If something isn't working, please create a new issue in the appropriate plugin project. I will
accept pull requests as well.

## Table of contents

- [Create a cordova project](doc/create.md)
- [Add a plugin](doc/plugin.md)
- [Set preferences](doc/preferences.md)
- [Add an icon](doc/icon.md)
- [Build a project](doc/build)
    - [Android](doc/build/android.md)

## Plugins

These plugins are currently available.

1. [gulp-cordova-create](https://github.com/SamVerschueren/gulp-cordova-create)
    - Create a cordova project.
2. [gulp-cordova-plugin](https://github.com/SamVerschueren/gulp-cordova-plugin)
    - Add a plugin to your cordova project.
3. [gulp-cordova-preference](https://github.com/SamVerschueren/gulp-cordova-preference)
    - Set the preferences of your cordova project.
4. [gulp-cordova-icon](https://github.com/SamVerschueren/gulp-cordova-icon)
    - Generates all the icons for your Cordova build automatically.
5. [gulp-cordova-build-android](https://github.com/SamVerschueren/gulp-cordova-build-android)
    - Build the cordova project for the Android platform.
6. [gulp-cordova-build-bb10](https://github.com/SamVerschueren/gulp-cordova-build-bb10)
    - Build the cordova project for the BlackBerry 10 platform.

*More plugins will follow in the near future.*

## Author

- Sam Verschueren [<sam.verschueren@gmail.com>]
