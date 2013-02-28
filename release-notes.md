---
layout: default
title: Release Notes
---

# Release Notes

-----
## 2.x Branch

-----
## [Release 2.0-alpha-2](http://repo1.maven.org/maven2/org/robolectric/robolectric/2.0-alpha-2/) - February 26, 2013
-----

_Note:_
This is an unstable alpha release: expect bugs and upcoming changes to the API.

See [this blog post](http://robolectric.blogspot.com/2013/02/migrating-to-robolectric-20.html) for notes on upgrading.

#### Features
- Switched from Javassist to ASM for bytecode manipulation: much faster.
- All classes in android.support.* are now unshadowed and should work as expected.
- Improved resource and library project support.

-----
## [Release 2.0-alpha-1](http://repo1.maven.org/maven2/org/robolectric/robolectric/2.0-alpha-1/) - January 29, 2013
-----

_Note:_
This is an unstable alpha release: expect bugs and upcoming changes to the API.

#### Features
- Support for library projects.
- More realistic resource loading, including system resources.
- Much better support for resource qualifiers (e.g. locale, resolution, etc.).
- Groundwork to remove many shadows and use actual android sdk code.
- Moved to org.robolectric package and maven groupId.


-----
## 1.x Branch

-----
### [Release 1.2](http://repo1.maven.org/maven2/com/pivotallabs/robolectric/1.2) - February 15, 2013
-----

This release contains all updates since April 2nd, including numerous contributions from the Robolectric community
(thanks!). There's partial support for Fragments, and tons of other shadow updates and bug fixes.

_Note:_
This marks the last major release of the 1.x branch; the Robolectric core team is now focusing on the 2.x branch.

-----
### [Release 1.1](http://repo1.maven.org/maven2/com/pivotallabs/robolectric/1.1) - April 2, 2012
-----

_Note:_
We had a little lapse in record-keeping here, sorry.

-----
### [Release 1.0](http://repo1.maven.org/maven2/com/pivotallabs/robolectric/1.0) - October 13, 2011
-----

_Note:_
We had a little lapse in record-keeping here, sorry.

-----
### [Release 1.0-RC4](http://repo1.maven.org/maven2/com/pivotallabs/robolectric/1.0-RC4/) - August 11, 2011
-----

_Note:_
We had a little lapse in record-keeping here, sorry.

-----
### [Release 1.0-RC1](http://repo1.maven.org/maven2/com/pivotallabs/robolectric/1.0-RC1/) - February 13, 2011
-----

#### Features
- Loads Android platform resources, looks at ANDROID_HOME, local.properties and "which android" to find the Android SDK
- General code cleanup and refactorings, Repackaging of source trees
- Improvements to TestAttributeSet (Thanks Ronald D.!)
- Ant task for mvn that adds the maps.jar to the local mvn repo
- Shadow for ViewStub
- Improvements for Http layer Shadows and fakes
- AndroidManifest.xml parsing improvements
- Added ShadowNotificationManager

#### Bug Fixes
- Fix bug where layouts were getting included twice
- Fix regressions for early API versions related to BluetoothAdaptor
- Fix bugs in menu view loading
- Various View loading improvements and bug fixes

#### Note
ant maven-install-jars will update Maven with the correct version of maps.jar

-----
### [Release 0.9.8](http://repo1.maven.org/maven2/com/pivotallabs/robolectric/0.9.8/) - January 21, 2011
-----

#### One step back...
- Temporarily reverted loading of Android platform resources -- sorry, jumped the gun a bit, it wasn't quite ready.


-----
### [Release 0.9.7](http://repo1.maven.org/maven2/com/pivotallabs/robolectric/0.9.7/) - January 19, 2011
-----

#### Features
- Loading of Android platform resources - Thanks palfrey!

#### Bug Fix
- Fixed ClassNotFoundExceptions when maps.jar is not being used by the project under test


-----
### [Release 0.9.6](http://repo1.maven.org/maven2/com/pivotallabs/robolectric/0.9.6/) - January 13, 2011
-----

#### Features
- Shadow implementation of MenuInflater - Thanks palfrey!
- Lots more shadows, including <code>Camera</code>, <code>Configuration</code>, <code>WebView</code>,
  <code>WebSettings</code>, and <code>WebViewClient</code>; better shadows for
  <code>Activity.startActivityForResult()</code> and <code>SharedPreferences</code> - Thanks mportuesi!
- Fixed a failure caused by the size of <code>Integer</code> in h2 being different than in SQLite - Thanks billmccord!
- The android-test and maps jars no longer need to be on your project's test classpath to use Robolectric. You now need
  to use <code>RobolectricForMaps.shadowOf()</code> to get the shadow of <code>GeoPoint</code>s, <code>MapView</code>s,
  <code>MapController</code>s, and <code>ItemizedOverlay</code>s.


-----
### [Release 0.9.5](http://repo1.maven.org/maven2/com/pivotallabs/robolectric/0.9.5/) - December 23, 2010
-----

#### Note
We have recently changed the Robolectric project structure to work with Maven. If you are developing directly from the
repository rather than from a jar release then you should close your IDE, delete its project files (.classpath,
&#42;.iml, etc...) and reload the project by importing the pom.xml into your IDE. This process has been tested with
both IntelliJ and Eclipse.

#### Features
- Improved testing of asynchronous and background tasks. <code>Looper</code>s and <code>AsyncTask</code> background
  threads are now un-paused by default (see <code>Robolectric.pauseMainLooper()</code> et al.).
- Shadows for <code>Bitmap</code>, <code>BitmapFactory</code>, and <code>Canvas</code>, and related classes, with
  textual descriptions (see <code>Robolectric.visualize()</code>) - Thanks xtremelabs!
- Improved HTTP testing (see <code>Robolectric.addHttpResponseRule()</code>).
- Shadow for <code>Camera</code>, <code>Camera.Parameters</code>, <code>MediaRecorder</code> - Thanks mportuesi!
- Shadow for <code>ArrayAdapter</code> - Thanks mylacc!
- Shadow for <code>ExpandableListView</code> - Thanks casidiablo!
- Nicer stack traces from within shadowed methods.
- Now available from Maven Central (and built with Maven).
- More shadowed methods on numerous classes.
- The <code>onCreate()</code> method of the application is no longer called automatically as part of test setup and
  must now be called manually.


-----
### Release 0.9.4 - December 14, 2010
-----

#### Features
- Gingerbread support
- HTTP client support and shadowing
- Shadow for <code>AssetManager</code> - Thanks gnorsilva!
- Support string references in string resources.
- Support for View background attribute resource id - Thanks macarse!

#### Bug Fixes
- Remove errant semicolon from generated ShadowSQLiteQueryBuilder - Thanks billmccord!


-----
### Release 0.9.3 - December 3, 2010
-----

#### Features
- Shadow for <code>AsyncTask</code>
- Integrated contributions for <code>ShadowConnectivityManager</code> and <code>ShadowNetworkInfo</code> - Thanks
  macarse!
- A HUGE contribution from the team at [Zoodles](http://www.zoodles.com), the in test SQLite database
  (<code>ShadowSQLiteDababase</code>) is backed by h2, reducing the need for database mocking. Thank You Zoodles!
- Robolectric now instantiates applications that are of the type specified in the AndroidManifest.xml - Thanks
  Mike Burton!
- The Robolectric jars will now work for projects that use the standard Android SDK (and not the Android Google APIs
  version which contains optional APIs such as Google Maps).

#### Bug Fixes
- Windows fixes for path separators
- Windows users can ant build the robolectric library and run the robolectric tests
- Colors that reference other colors
- Robolectric will now work on projects that do not use the Google Maps API and other optional packages.

#### Other
- We have added [Roboguice](http://code.google.com/p/roboguice/) integration to the
  [RobolectricSample](http://github.com/pivotal/RobolectricSample) project.
- Support for maven and submission to central is WIP


-----
### Release 0.9.2 - November 24, 2010
-----

#### Features
- Shadow classes for SQLite database (Thanks mportuesi!)
- Lint test for shadow methods that match Android methods but are not annotated with @Implementation
- Shadow support for raw resources (Thanks macarse!)
- Improved quick start documentation

#### Bug Fixes
- Ignore non xml files in layouts directory (Subversion .svn directories were causing cryptic errors, Thanks rlgomes!)

-----
### Release 0.9.1 - November 19, 2010
-----

#### Features
- Integrated support for several new Shadow classes from pull requests -- thank you mportuesi!

#### Bug Fixes
- Fixed JSON "stub!" exceptions.


-----
### Release 0.9 - November 17, 2010
-----

#### Features
- Integrated support for several new Shadow classes from pull requests - Thank you contributors!
- Made the default RobolectricTestRunner robust enough to work without modification for most projects
- Improved the extensibility of RobolectricTestRunner for those projects that do need to add more functionality
- Encapsulated most of the fields on the Shadow classes
- Added support for the android.net.Uri class so that it works the same way in tests that it does in production. This is
a departure from the behavior of the Shadow classes. We did this because Uri is a utility class, and it would be
almost impossible to write a useful Shadow class for it.
- Improved documentation
- Added run configurations to make it easier to get Robolectric working out of the box

#### Bug Fixes
- Fixed support for equals(), hashcode(), and toString()
- Improved the documentation for getting Robolectric to work under Eclipse


-----
### Release 0.8 - November 5, 2010
-----

#### Features
- &lt;include&gt; tags apply their attributes to the imported element
- equals(), hashcode(), and toString() can be overridden on all Shadow classes
- Put a link to the Tracker project in the Robolectric User Guide
- Added support for Eclipse

#### Bug Fixes
- ResourceLoader obtained from context, not stored statically
- Instrumented class cache no longer retains stale entries