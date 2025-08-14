# React Native #

Building APK see guide for [Generating Keystore](https://reactnative.dev/docs/signed-apk-android)
```
gradlew clean
gradlew assembleRelease
```
And go to
```
/android/app/build/outputs/apk/release/app-release.apk
```


---

## Global Gradle Configuration

set the CMake object path max length globally, add the following to your global `gradle.properties` file:

android.externalNativeBuild.cmake.arguments=-DCMAKE_OBJECT_PATH_MAX=1024
