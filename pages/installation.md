---
layout: page
title:  "Installation"
---

If you are migrating from ember-cli-cordova, read the [migration
guide](legacy/migration-from-ember-cli-cordova).


#### Requirements
- Ember 1.13+;
- node 0.12+;

#### Installation

```cli
  ember install ember-cordova
```

Existing Cordova projects at ember-cordova/cordova will not be overwritten.

You can optionally pass the following params:

|             | type / desc                       |
|------------ | ----------------------------------|
| name        | String (defaults to com.embercordova.{{yourEmberAppName}}) |
| cordovaid   | String (defaults to your app name) |
| templatePath| String path to cordova template |

```cli
ember install ember-cordova --name=AppName --cordovaid=com.isleofcode.app --templatePath=../template
```

#### A note on cordovaid

By default ember-cordova takes your Ember App name and generates a bundle id of com.embercordova.emberAppName. App ids should generally be reverse domains, and are _required_ for Android builds.

By release, you should update id to com.yourdomain.foo (with real values). This is achieved by setting the `id` property on the `widget` node in the `ember-cordova/cordova/config.xml`.

```
<?xml version='1.0' encoding='utf-8'?>
<widget id="com.myappdevcompany.phoneapp" version="1.0.0" xmlns="http://www.w3.org/ns/widgets" xmlns:cdv="http://cordova.apache.org/ns/1.0">
    <name>phoneApp</name>
    <description>
        A sample Apache Cordova application that responds to the deviceready event.
    </description>
 ...
```

#### Post Install Steps

Next, you will need to add platforms and make some small changes to
your Ember app. See [Project Setup](/pages/workflow/project_setup).