Resource URLs
=============

**Non-standard**  
This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Resource URLs, URLs prefixed with the `resource:` scheme, are used by Firefox and Firefox browser extensions to load resources internally, but some of the information is available to sites the browser connects to as well.

Syntax
------

Resource URLs are composed of two parts: a prefix (`resource:`), and a URL pointing to the resource you want to load:

    resource://<url>

An example:

    resource://gre/res/svg.css

When arrows are found in the resource URL's ('-&gt;'), it means that the first file loaded the next one:

    resource://<File-loader> -> <File-loaded>

Please refer to [Identifying resources on the web](identifying_resources_on_the_web) for more general details.

In this article, we focus on resource URIs, which are used internally by Firefox to point to built-in resources.

Threats
-------

Because some of the information shared by `resource:` URLs is available to websites, a web page could run internal scripts and inspect internal resources of Firefox, including the default preferences, which could be a serious security and privacy issue.

For example, [a script on Browserleaks](https://www.browserleaks.com/firefox) highlights what Firefox reveals when queried by a simple script running on the site (you can find the code in <https://browserleaks.com/firefox#more>).

The file firefox.js passes preference names and values to the pref() function. For example:

    http://searchfox.org/mozilla-central/rev/48ea452803907f2575d81021e8678634e8067fc2/browser/app/profile/firefox.js#575

Web sites can easily collect Firefox default preferences by overriding this `pref()` function and using the script `resource:///defaults/preferences/firefox.js`.

Furthermore, some default values of preferences differ between build configurations, such as platform and locale, which means web sites could identify individual users using this information.

Solution
--------

In order to fix this problem, Mozilla changed the behavior of loading resource: URIs in [bug 863246](https://bugzilla.mozilla.org/show_bug.cgi?id=863246), which landed in [Firefox 57 (Quantum)](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Releases/57).

In the past, web content was able to access whatever `resource:` URIs were desired — not only Firefox’s internal resources, but also extensions’ assets. Now this behavior is prohibited by default.

It is however still necessary for Firefox to load resources in web content under certain circumstances. For example, if you open the view source page (View Page Source or View Selection Source), you will find it requires `viewsource.css` through a `resource:` URI. Resources that have to be exposed to web content have been moved to a new location named `resource://content-accessible/`, which is isolated and only contains non-sensitive resources. In this way we can keep essential resources exposed and have most threats eliminated.

**Note**: It is recommended that web and extension developers don’t try to use resource URLs anymore. Their usage was hacky at best, and most usage won’t work any more.

Specifications
--------------

resource: is not defined in any specification.

Browser compatibility
---------------------

resource: is Firefox only.

See also
--------

-   [Identifying resources on the Web](identifying_resources_on_the_web)
-   [What is a URL?](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL)
-   [IANA list of URI schemes](https://www.iana.org/assignments/uri-schemes/uri-schemes.xhtml) (`resource:` is [covered here](https://www.iana.org/assignments/uri-schemes/prov/resource))

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Resource_URLs$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Resource_URLs" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Resource_URLs</a>
