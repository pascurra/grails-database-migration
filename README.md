[![Build Status](https://travis-ci.org/yamkazu/database-migration.svg)](https://travis-ci.org/yamkazu/database-migration)

Database Migration Plugin for Grails 3
======================================

This is a fork of grails migration plugin for grails 3.

The Database Migration plugin helps you manage database changes while developing Grails applications.
The plugin uses the Liquibase library.
Using this plugin (and Liquibase in general) adds some structure and process to managing database changes.
It will help avoid inconsistencies, communication issues, and other problems with ad-hoc approaches.

Database migrations are represented in text form, either using a Groovy DSL or native Liquibase XML, in one or more changelog files.
This approach makes it natural to maintain the changelog files in source control and also works well with branches.
Changelog files can include other changelog files, so often developers create hierarchical files organized with various schemes.
One popular approach is to have a root changelog named changlog.groovy (or changelog.xml) and to include a changelog per feature/branch that includes multiple smaller changelogs. Once the feature is finished and merged into the main development tree/trunk the changelog files can either stay as they are or be merged into one large file.
Use whatever approach makes sense for your applications, but keep in mind that there are many options available for changelog management.

See [documentation](http://grails-plugins.github.io/grails-database-migration/docs/manual/index.html) for further information.

INSTALL
-------

Add a dependency for the plugin in build.gradle:

```
buildscript {
    ...
    dependencies {
        classpath 'org.grails.plugins:database-migration:2.0.0.RC1'
    }
}

dependencies {
    ...
    runtime 'org.grails.plugins:database-migration:2.0.0.RC1'
}
```

And add a path of Changelog directory to `sourceSets` in build.gradle:

```
sourceSets {
    main {
        resources {
            srcDir 'grails-app/migrations'
        }
    }
}
```

