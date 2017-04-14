This project showcases the misbehavior of Android Studio with regards to `buildSrc/` module.

It seems like adding such module to the root project is enough to break the `Sync project with Gradle files` functionality, and the following error is shown in the IDE:

```
Gradle project sync failed. Basic functionality (e.g. editiing, debugging) will not work properly.
```

The `Messages` panel shows this further message:
 ```
 Error:The modules ['buildSrcBug', 'buildSrc'] point to same directory in the file system.
 Each module has to have a unique path.
 ```

Note: using `Refresh all gradle projects` seems to workaround this issue.
