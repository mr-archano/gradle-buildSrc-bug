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

I could reproduce the issue using Gradle 3.4+ and Android Studio 2.3.+ (up to 2.4 EAP 6). I haven't tested other versions of Android Studio yet.

Note: using `Refresh all gradle projects` (from the `Gradle Projects` panel in the IDE) seems to workaround this issue. Building from the command line is not affected by this either.
