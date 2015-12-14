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
- [Set version](doc/version.md)
- [Set project description](doc/description.md)
- [Set author](doc/author.md)
- [Add an icon](doc/icon.md)
- [Add a splashscreen](doc/splashscreen.md)
- [Build a project](doc/build)
    - [Android](doc/build/android.md)
    - [BlackBerry 10](doc/build/blackberry10.md)

## Plugins

These plugins are currently available.

*More plugins will follow in the near future.*

## General

1. [gulp-cordova-create](https://github.com/SamVerschueren/gulp-cordova-create)
    - Create a cordova project.

## Configuration

These plugins can be used to change the configuration of the cordova project.

1. [gulp-cordova-plugin](https://github.com/SamVerschueren/gulp-cordova-plugin) 
    - Add a plugin to your cordova project.  
    [![Build Status](https://travis-ci.org/SamVerschueren/gulp-cordova-plugin.svg?branch=master)](https://travis-ci.org/SamVerschueren/gulp-cordova-plugin)
    [![Coverage Status](https://coveralls.io/repos/SamVerschueren/gulp-cordova-plugin/badge.svg?branch=master)](https://coveralls.io/r/SamVerschueren/gulp-cordova-plugin?branch=master)
2. [gulp-cordova-plugin-remove](https://github.com/SamVerschueren/gulp-cordova-plugin-remove)
    - Removes a plugin from the cordova project.  
    [![Build Status](https://travis-ci.org/SamVerschueren/gulp-cordova-plugin-remove.svg?branch=master)](https://travis-ci.org/SamVerschueren/gulp-cordova-plugin-remove)
    [![Coverage Status](https://coveralls.io/repos/SamVerschueren/gulp-cordova-plugin-remove/badge.svg?branch=master&service=github)](https://coveralls.io/github/SamVerschueren/gulp-cordova-plugin-remove?branch=master)
3. [gulp-cordova-preference](https://github.com/SamVerschueren/gulp-cordova-preference)
    - Set the preferences of your cordova project.  
    [![Build Status](https://travis-ci.org/SamVerschueren/gulp-cordova-preference.svg?branch=master)](https://travis-ci.org/SamVerschueren/gulp-cordova-preference)
4. [gulp-cordova-access](https://github.com/SamVerschueren/gulp-cordova-access)
    - Sets the access origins of the cordova project.  
    [![Build Status](https://travis-ci.org/SamVerschueren/gulp-cordova-access.svg?branch=master)](https://travis-ci.org/SamVerschueren/gulp-cordova-access)
    [![Coverage Status](https://coveralls.io/repos/SamVerschueren/gulp-cordova-access/badge.svg?branch=master&service=github)](https://coveralls.io/github/SamVerschueren/gulp-cordova-access?branch=master)
5. [gulp-cordova-version](https://github.com/SamVerschueren/gulp-cordova-version)
    - Sets the version of the cordova project in the `config.xml` file.  
    [![Build Status](https://travis-ci.org/SamVerschueren/gulp-cordova-version.svg?branch=master)](https://travis-ci.org/SamVerschueren/gulp-cordova-version)
    [![Coverage Status](https://coveralls.io/repos/SamVerschueren/gulp-cordova-version/badge.svg?branch=master&service=github)](https://coveralls.io/github/SamVerschueren/gulp-cordova-version?branch=master)
6. [gulp-cordova-description](https://github.com/SamVerschueren/gulp-cordova-description)
    - Sets the description of the cordova project in the `config.xml` file.  
    [![Build Status](https://travis-ci.org/SamVerschueren/gulp-cordova-description.svg?branch=master)](https://travis-ci.org/SamVerschueren/gulp-cordova-description)
    [![Coverage Status](https://coveralls.io/repos/SamVerschueren/gulp-cordova-description/badge.svg?branch=master)](https://coveralls.io/r/SamVerschueren/gulp-cordova-description?branch=master)
7. [gulp-cordova-author](https://github.com/SamVerschueren/gulp-cordova-author)
    - Sets the author of the cordova project in the `config.xml` file.  
    [![Build Status](https://travis-ci.org/SamVerschueren/gulp-cordova-author.svg?branch=master)](https://travis-ci.org/SamVerschueren/gulp-cordova-author)
8. [gulp-cordova-icon](https://github.com/SamVerschueren/gulp-cordova-icon)
    - Generates all the icons for your Cordova build automatically.
9. [gulp-cordova-xml](https://github.com/SamVerschueren/gulp-cordova-xml)
    - Adds raw xml tags to your `config.xml` file.  
    [![Build Status](https://travis-ci.org/SamVerschueren/gulp-cordova-xml.svg)](https://travis-ci.org/SamVerschueren/gulp-cordova-xml)

## Building

These build plugins can be used to build the cordova project for certain platforms.

1. [gulp-cordova-build-android](https://github.com/SamVerschueren/gulp-cordova-build-android)
    - Build the cordova project for the Android platform.
2. [gulp-cordova-build-bb10](https://github.com/SamVerschueren/gulp-cordova-build-bb10)
    - Build the cordova project for the BlackBerry 10 platform.
3. [gulp-cordova-build-ios](https://github.com/SamVerschueren/gulp-cordova-build-ios)
    - Build the cordova project for the iOS platform.

## Author

- [@SamVerschueren](https://twitter.com/SamVerschueren) [<sam.verschueren@gmail.com>]
