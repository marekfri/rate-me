Rate-Me [![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-Rate--Me-brightgreen.svg?style=flat)](https://android-arsenal.com/details/1/1032)
=======

Rate Me is an Android library that shows dialog to suggest the user to rate the application in the Google Play Store.

With a little twist: if the rating is positive, we take the user to the Play Store directly. Otherwise, we ask him for feedback via email. (This is all configurable.)

<strong>This repository is forked from <a href="https://github.com/androidsx/rate-me">androidsx/rate-me</a> repository.

What is new:
<ul>
<li>Rate-Me dialog is not dismissed when clicked outside</li>
<li>Slovak and Czech localizations</li>
</ul>
</strong>

<p>
<img src="https://raw.githubusercontent.com/androidsx/rate-me/master/readme-images/rate-me-dialog-in-helium.png" width="256" />
<img src="https://raw.githubusercontent.com/androidsx/rate-me/master/readme-images/rate-me-dialog-in-pixable.png" width="256" />
</p>

How to integrate
================
This library can be integrated to your project using <a href="https://jitpack.io/">jitpack.io</a>.

Add this repository in your `build.gradle`:

```xml
repositories {
    maven { url "https://jitpack.io" }
}
```

Add this dependency in your `build.gradle`:

```xml
dependencies {
    compile 'com.github.marekfri:rate-me:v4.1.1'
}
```

How to use
==========

The simplest integration:

```java
new RateMeDialog.Builder(getPackageName())
        .enableFeedbackByEmail("email@example.com")
        .build()
        .show(getFragmentManager(), "plain-dialog");
```

Have a look at the sample project for other examples.

Automatic timer
---------------

You can make the dialog appear after a number of times your app has been opened or after a number of days after the install date:

```java
RateMeDialogTimer.onStart(this);
if (RateMeDialogTimer.shouldShowRateDialog(this, 7, 3)) {
	// show the dialog with the code above
}
```

License
=======

Licensed under the MIT License. See the [LICENSE.md](LICENSE.md) file for more details.
