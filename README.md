# LLogger
A tool that write log to local and format logcat's display.

You use this for saving app's log, incule crash log.

# Getting started
In your `build.gradle`:

```
allprojects {
    repositories {
		...
	    maven { url "https://jitpack.io" }
    }
}

...

dependencies {
    compile 'com.github.wxcchdStar:LLogger:v1.1.1'
}
```
In your `Application` class:
``` java
L.Builder builder = new L.Builder();
L.set(builder.addLogCat().addLocalLog(this).logCrash(this).create());
```

In your class:
``` java
L.d("message");
L.d("message1", "message2", 3);
```

# Tips
1. If the sdcard exists, the log path is **/sdcard/#{package_name}/log.txt**.
2. If the sdcard doesn't exists, the log path is **/data/data/#{package_name}/files/#{package_name}/log.txt**.
3. You need to declare the **WRITE_EXTERNAL_STORAGE** permission in the AndroidManifest.xml.
4. It save recently 8 days's log at most.
