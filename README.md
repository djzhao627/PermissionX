# PermissionX

PermissionX是一个可以简化权限申请的框架

PermissionX is a tool for simplify the permissions request in android

## Usage

1. Add it in your root `build.gradle` at the end of repositories:

```groovy
allprojects {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}
```

2. Add the dependency in the `build.gradle` of the Module

```groovy
dependencies {
        implementation 'com.github.djzhao627:PermissionX:1.0'
}
```

3. do permissions request

```kotlin
PermissionX.request(
    this,
    Manifest.permission.CALL_PHONE,
    Manifest.permission.READ_CONTACTS
) { allGranted, deniedList ->
    if (allGranted) {
        // continue to work...
    } else {
        Toast.makeText(this, "You Denied $deniedList", Toast.LENGTH_SHORT).show()
    }
}
```