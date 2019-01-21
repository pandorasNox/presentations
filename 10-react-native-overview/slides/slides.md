---
title: react-native overview
separator: <!-- ========== ========== ========== -->
verticalSeparator: <!-- ---------- ---------- ---------- -->
theme: night
revealOptions:
    # transition: 'fade'
---

# react-native overview

Note: test note

<!-- ========== ========== ========== -->

## why it works

<!-- ========== ========== ========== -->

### native Js app runtime

JavacriptCore VM

https://facebook.github.io/react-native/docs/javascript-environment

<!-- ========== ========== ========== -->

## JS-Bridgte

JS Thread <-> JS-Bridgte (C/C++) <-> Native Threads

<!-- ========== ========== ========== -->

## setup

<!-- ========== ========== ========== -->

## comes in two flavors

#### Create React Native App (CRNA)
```bash
$ create-react-native-app MyApp
```

#### react-native-cli
```bash
$ react-native-cli init
```

<!-- ========== ========== ========== -->

## two states:

#### non-ejected
```bash
$ create-react-native-app MyApp
```

#### ejected
```bash
$ react-native-cli init
```
```bash
$ create-react-native-app MyApp
$ cd MyApp
$ npm run eject
```

<!-- ========== ========== ========== -->

## non-ejected / crna
- pro
    - don't needs native IDE's / simulators
    - uses a wrapper app (Expo) on your phone
    - fast developer feedback (HMR)
- con
    - works only via local network
    - can't use native modules


<!-- ========== ========== ========== -->

## ejected / rn-cli
- pro
    - runs native 3rd party modules
    - you can share app (apk files)
- con
    - needs **xcode** or **android studio**
    - always compiles (slow development)
<!-- ========== ========== ========== -->

## development process

try to get a good mixed workflow
- combine crna + eject
- like xdebug enable disable ?!

<!-- ========== ========== ========== -->

## native community modules (to consider)

- [react-native-camera](https://github.com/react-native-community/react-native-camera)
- [image picker](https://github.com/react-native-community/react-native-image-picker)
- [react-native-image-crop-picker](https://github.com/ivpusic/react-native-image-crop-picker)

<!-- ========== ========== ========== -->

## native module pitfalls

- hard to keep in sync with react-native updates
- have to be linked
    - 95% you cane use build in tool
    - but there are "after-link" tasks
        - e.g. setting module permissions
    - adapting .plist(iOS) / AndroidManifest.xml
- have to use an ejected project
- gradle / groovy

<!-- ========== ========== ========== -->

## android build process

### dependencies
- openjdk
- android-sdk & friends
    - android-components
    - google-components
- gradle
- nodejs / npm
- react-native-cli

<!-- ========== ========== ========== -->

### requirements

- a prepared the keystore file
    - contains key(s) to sign your app
    - you always have to use the exact same key
- gradle.properties file
- app.json
- index.js

<!-- ========== ========== ========== -->

### actual build
- run checks
- sync/cp files
- npm install
- react-native eject
    - generate android/iOS dir
- place keystore file in android dir
- handle apk versioning
- link native modules
- `cd android && ./gradlew assembleRelease`

<!-- ========== ========== ========== -->

[android example build bash script](https://github.com/pandorasNox/docker-rnapk/blob/master/react-native-build/build.sh)

<!-- ========== ========== ========== -->

## iOS build process

### dependencies
- xcode
- ?

<!-- ========== ========== ========== -->

## iOS build process

### build
- do a lot of signing stuff
- adapt plist file
- xcode
- upload to iTunes

<!-- ========== ========== ========== -->

## automation solutions

- [fastlane](https://fastlane.tools/)
- [circle-ci](https://circleci.com/docs/2.0/ios-codesigning/)
- [expo.io](https://expo.io)
- [microsoft code-push](https://github.com/Microsoft/code-push)
- [apphub.io](https://apphub.io/)
