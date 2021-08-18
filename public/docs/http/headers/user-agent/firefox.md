User-Agent: Firefox
===================

This document describes the user agent string used in Firefox 4 and later and applications based on [Gecko](https://developer.mozilla.org/en-US/docs/Mozilla/Gecko) 2.0 and later. For a breakdown of changes to the string in Gecko 2.0, see [Final User Agent string for Firefox 4](https://hacks.mozilla.org/2010/09/final-user-agent-string-for-firefox-4/) (blog post). See also this document on [user agent sniffing](../../browser_detection_using_the_user_agent) and this [Hacks blog post](https://hacks.mozilla.org/2013/09/user-agent-detection-history-and-checklist/).

General form
------------

The UA string of Firefox itself is broken down into four components:

`Mozilla/5.0 (platform; rv:geckoversion) Gecko/geckotrail Firefox/firefoxversion`

-   `Mozilla/5.0` is the general token that says the browser is Mozilla compatible, and is common to almost every browser today.
-   `platform` describes the native platform the browser is running on (e.g. Windows, Mac, Linux or Android), and whether or not it's a mobile phone. Firefox OS phones simply say "`Mobile`"; the web is the platform. Note that `platform` can consist of multiple "; "-separated tokens. See below for further details and examples.

    Though fixed in Firefox 69, previous 32-bit versions of Firefox running on 64-bit processors would report that the system is using a 32-bit CPU.

-   `rv:geckoversion` indicates the release version of Gecko (such as "`17.0`"). In recent browsers, `geckoversion` is the same as `firefoxversion`.
-   `Gecko/geckotrail` indicates that the browser is based on Gecko.
-   On Desktop, `geckotrail` is the fixed string "`20100101`"
-   `Firefox/firefoxversion` indicates the browser is Firefox, and provides the version (such as "`17.0`").
-   from Firefox 10 on mobile, `geckotrail` is the same as `firefoxversion`.

The recommended way of sniffing for Gecko-based browsers (if you *have to* sniff for the browser engine instead of using feature detection) is by the presence of the "`Gecko`" and "`rv:`" strings, since some other browsers include a "`like Gecko`" token.

For other products based on Gecko, the string can take one of two forms, where the tokens have the same meaning except those noted below:

`Mozilla/5.0 (platform; rv:geckoversion) Gecko/geckotrail appname/appversion`  
`Mozilla/5.0 (platform; rv:geckoversion) Gecko/geckotrail Firefox/firefoxversion appname/appversion`

-   `appname/appversion` indicates the application name and version. For instance, this could be "`Camino/2.1.1`", or "`SeaMonkey/2.7.1`".
-   `Firefox/firefoxversion` is an optional compatibility token that some Gecko-based browsers may choose to incorporate, to achieve maximum compatibility with websites that expect Firefox. `firefoxversion` will generally represent the equivalent Firefox release corresponding to the given Gecko version. Some Gecko-based browsers may not opt into using this token; for this reason, sniffers should be looking for Gecko — not Firefox! Whether this token appears is controlled by the *"general.useragent.compatMode.firefox"* boolean pref.

Mobile and Tablet indicators
----------------------------

Only from Firefox 11 onwards.

The `platform` part of the UA string indicates if Firefox is running on a phone-sized or tablet device. When Firefox runs on a device that has the phone form factor, there is a `Mobile;` token in the `platform` part of the UA string. When Firefox runs on a tablet device, there is a `Tablet;` token in the `platform` part of the UA string instead. For example:

    Mozilla/5.0 (Android 4.4; Mobile; rv:41.0) Gecko/41.0 Firefox/41.0
    Mozilla/5.0 (Android 4.4; Tablet; rv:41.0) Gecko/41.0 Firefox/41.0

The version numbers are not relevant. Avoid inferring materials based on these.

The preferred way to target content to a device form factor is to use CSS Media Queries. However, if you use UA sniffing to target content to a device form factor, please look for **Mobi** (to include Opera Mobile, which uses "Mobi") for the phone form factor and do **not** assume any correlation between "Android" and the device form factor. This way, your code will work if/when Firefox ships on other phone/tablet operating systems or Android is used for laptops. Also, please use touch detection to find touch devices rather than looking for "Mobi" or "Tablet", since there may be touch devices which are not tablets.

Firefox OS devices identify themselves without any operating system indication; for example: "Mozilla/5.0 (Mobile; rv:15.0) Gecko/15.0 Firefox/15.0". The web is the platform.

Windows
-------

Windows user agents have the following variations, where *x.y* is the Windows NT version (for instance, Windows NT 6.1).

<table><thead><tr class="header"><th>Windows version</th><th>Gecko user agent string</th></tr></thead><tbody><tr class="odd"><td>Windows NT on x86 CPU</td><td>Mozilla/5.0 (Windows NT <em>x</em>.<em>y</em>; rv:10.0) Gecko/20100101 Firefox/10.0</td></tr><tr class="even"><td>Windows NT on x64 CPU</td><td>Mozilla/5.0 (Windows NT <em>x</em>.<em>y</em>; Win64; x64; rv:10.0) Gecko/20100101 Firefox/10.0</td></tr></tbody></table>

Macintosh
---------

Here, *x.y* is the version of Mac OS X (for instance, Mac OS X 10.6).

<table><thead><tr class="header"><th>Mac OS X version</th><th>Gecko user agent string</th></tr></thead><tbody><tr class="odd"><td>Mac OS X on Intel x86 or x86_64</td><td>Mozilla/5.0 (Macintosh; Intel Mac OS X <em>x.y</em>; rv:10.0) Gecko/20100101 Firefox/10.0</td></tr><tr class="even"><td>Mac OS X on PowerPC</td><td>Mozilla/5.0 (Macintosh; PPC Mac OS X <em>x.y</em>; rv:10.0) Gecko/20100101 Firefox/10.0</td></tr></tbody></table>

Linux
-----

Linux is a more diverse platform. Your distribution of Linux might include an extension that changes your user-agent. A few common examples are given below.

<table><thead><tr class="header"><th>Linux version</th><th>Gecko user agent string</th></tr></thead><tbody><tr class="odd"><td>Linux desktop on i686 CPU</td><td>Mozilla/5.0 (X11; Linux i686; rv:10.0) Gecko/20100101 Firefox/10.0</td></tr><tr class="even"><td>Linux desktop on x86_64 CPU</td><td>Mozilla/5.0 (X11; Linux x86_64; rv:10.0) Gecko/20100101 Firefox/10.0</td></tr><tr class="odd"><td>Nokia N900 Linux mobile, on the Fennec browser</td><td>Mozilla/5.0 (Maemo; Linux armv7l; rv:10.0) Gecko/20100101 Firefox/10.0 Fennec/10.0</td></tr></tbody></table>

Android (version 40 and below)
------------------------------

<table><thead><tr class="header"><th>Form factor</th><th>Gecko user agent string</th></tr></thead><tbody><tr class="odd"><td>Phone</td><td>Mozilla/5.0 (Android; Mobile; rv:40.0) Gecko/40.0 Firefox/40.0</td></tr><tr class="even"><td>Tablet</td><td>Mozilla/5.0 (Android; Tablet; rv:40.0) Gecko/40.0 Firefox/40.0</td></tr></tbody></table>

Android (version 41 and above)
------------------------------

Beginning in version 41, Firefox for Android will contain the Android version as part of the platform token. For increased interoperability, if the browser is running on a version below 4 it will report 4.4. Android versions 4 and above will report the version accurately. Note that the same Gecko—with the same capabilities—is shipped to all versions of Android.

<table><thead><tr class="header"><th>Form factor</th><th>Gecko user agent string</th></tr></thead><tbody><tr class="odd"><td>Phone</td><td>Mozilla/5.0 (Android 4.4; Mobile; rv:41.0) Gecko/41.0 Firefox/41.0</td></tr><tr class="even"><td>Tablet</td><td>Mozilla/5.0 (Android 4.4; Tablet; rv:41.0) Gecko/41.0 Firefox/41.0</td></tr></tbody></table>

Focus for Android
-----------------

From version 1, Focus is powered by Android WebView and uses the following user agent string format:

    Mozilla/5.0 (Linux; <Android Version> <Build Tag etc.>) AppleWebKit/<WebKit Rev> (KHTML, like Gecko) Version/4.0 Focus/<focusversion> Chrome/<Chrome Rev> Mobile Safari/<WebKit Rev>

Tablet versions on WebView mirror mobile, but do not contain a `Mobile` token.

Starting in Version 6, users can opt into using a GeckoView-based Focus for Android with a hidden preference: it uses a GeckoView UA string to advertise Gecko compatibility.

<table><thead><tr class="header"><th>Focus Version (Rendering Engine)</th><th>User Agent string</th></tr></thead><tbody><tr class="odd"><td>1.0 (WebView Mobile)</td><td>Mozilla/5.0 (Linux; Android 7.0) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Focus/1.0 Chrome/59.0.3029.83 Mobile Safari/537.36</td></tr><tr class="even"><td>1.0 (WebView Tablet)</td><td>Mozilla/5.0 (Linux; Android 7.0) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Focus/1.0 Chrome/59.0.3029.83 Safari/537.36</td></tr><tr class="odd"><td>6.0 (GeckoView)</td><td>Mozilla/5.0 (Android 7.0; Mobile; rv:62.0) Gecko/62.0 Firefox/62.0</td></tr></tbody></table>

Klar for Android
----------------

Since version 4.1, Klar for Android uses the same UA string as [Focus for Android](#Focus_for_Android). Before version 4.1, it sent a Klar/&lt;version&gt; product/version token.

<table><thead><tr class="header"><th>Klar Version (Rendering Engine)</th><th>User Agent string</th></tr></thead><tbody><tr class="odd"><td>1.0 (WebView)</td><td>Mozilla/5.0 (Linux; Android 7.0) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Klar/1.0 Chrome/58.0.3029.83 Mobile Safari/537.36</td></tr><tr class="even"><td>4.1+ (WebView)</td><td>Mozilla/5.0 (Linux; Android 7.0) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Focus/4.1 Chrome/62.0.3029.83 Mobile Safari/537.36</td></tr><tr class="odd"><td>6.0+ (GeckoView)</td><td>Mozilla/5.0 (Android 7.0; Mobile; rv:62.0) Gecko/62.0 Firefox/62.0</td></tr></tbody></table>

Focus for iOS
-------------

Version 7 of Focus for iOS uses a user agent string with the following format:

    Mozilla/5.0 (iPhone; CPU iPhone OS 12_1 like Mac OS X) AppleWebKit/605.1.15 (KHTML, like Gecko) FxiOS/7.0.4 Mobile/16B91 Safari/605.1.15

Note: this user agent was retrieved from an iPhone XR simulator and may be different on device.

Firefox for Fire TV
-------------------

Version 3 (and probably earlier) of Firefox for Fire TV use a user agent string with the following format:

    Mozilla/5.0 (Linux; <Android version>) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Focus/<firefoxversion> Chrome/<Chrome Rev> Safari/<WebKit Rev>

<table><tbody><tr class="odd"><td><strong>Firefox TV version</strong></td><td><strong>User Agent string</strong></td></tr><tr class="even"><td>v3.0</td><td>Mozilla/5.0 (Linux; Android 7.1.2) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Focus/3.0 Chrome/59.0.3017.125 Safari/537.36</td></tr></tbody></table>

Firefox for Echo Show
---------------------

From version 1.1, Firefox for Echo Show uses a user agent string with the following format:

    Mozilla/5.0 (Linux; <Android version>) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Focus/<firefoxversion> Chrome/<Chrome Rev> Safari/<WebKit Rev>

<table><tbody><tr class="odd"><td><strong>Firefox for Echo Show version</strong></td><td><strong>User agent string</strong></td></tr><tr class="even"><td>v1.1</td><td>Mozilla/5.0 (Linux; Android 5.1.1) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Focus/1.1 Chrome/59.0.3017.125 Safari/537.36</td></tr></tbody></table>

Firefox OS
----------

<table><thead><tr class="header"><th>Form factor</th><th>Gecko user agent string</th></tr></thead><tbody><tr class="odd"><td>Phone</td><td>Mozilla/5.0 (Mobile; rv:26.0) Gecko/26.0 Firefox/26.0</td></tr><tr class="even"><td>Tablet</td><td>Mozilla/5.0 (Tablet; rv:26.0) Gecko/26.0 Firefox/26.0</td></tr><tr class="odd"><td>TV</td><td>Mozilla/5.0 (TV; rv:44.0) Gecko/44.0 Firefox/44.0</td></tr><tr class="even"><td>Device-specific</td><td>Mozilla/5.0 (Mobile; <em><strong>nnnn;</strong></em> rv:26.0) Gecko/26.0 Firefox/26.0</td></tr></tbody></table>

### Device-specific user agent strings

Although it is **strongly discouraged** by Mozilla, some handset manufacturers unfortunately include a token in their device's UA string that represents their device id. If this is the case, the Firefox OS UA string will look like the device-specific string in the table above, where ***nnnn;*** is the manufacturer's code for the device (see [Guidelines](https://wiki.mozilla.org/B2G/User_Agent/Device_Model_Inclusion_Requirements)). Some of them we have noticed are of the form "**NexusOne;**", "**ZTEOpen;**", or "**Open C;**" (note that putting space is also discouraged). We provide this information to assist with your UA detection logic, but Mozilla discourages the detection of a device id in UA strings.

Here is a JavaScript regular expression that will detect all mobile devices, including devices with a device id in their UA string:

    /mobi/i

The `i` makes it case-insensitive, and `mobi` matches all mobile browsers.

### Firefox OS version number

While the version number for Firefox OS is not included in the UA string, it is possible to infer version information from the Gecko version number present in the UA string.

<table><thead><tr class="header"><th>Firefox OS version number</th><th>Gecko version number</th></tr></thead><tbody><tr class="odd"><td>1.0.1</td><td>18.0</td></tr><tr class="even"><td>1.1</td><td>18.1</td></tr><tr class="odd"><td>1.2</td><td>26.0</td></tr><tr class="even"><td>1.3</td><td>28.0</td></tr><tr class="odd"><td>1.4</td><td>30.0</td></tr><tr class="even"><td>2.0</td><td>32.0</td></tr><tr class="odd"><td>2.1</td><td>34.0</td></tr><tr class="even"><td>2.2</td><td>37</td></tr><tr class="odd"><td>2.5</td><td>44</td></tr></tbody></table>

It's easy to find the correspondences by looking at the [Mercurial repository names](https://hg.mozilla.org/releases): repositories starting by `mozilla-b2g` are the release repositories for Firefox OS, and have both Firefox OS and Gecko versions in their names.

Firefox OS has a four-digit version number: X.X.X.Y. The first two digits are owned by the Mozilla product team and denote versions with new features (eg: v1.1, 1.2, etc). The third digit is incremented with regular version tags (about every 6 weeks) for security updates, and the fourth is owned by the OEM.

Firefox for iOS
---------------

Firefox for iOS uses the default Mobile Safari UA string, with an additional **FxiOS/&lt;version&gt;** token, similar to how [Chrome for iOS identifies itself](https://developer.chrome.com/multidevice/user-agent#chrome_for_ios_user_agent).

<table><thead><tr class="header"><th>Form factor</th><th>Firefox for iOS user agent string</th></tr></thead><tbody><tr class="odd"><td>iPod</td><td>Mozilla/5.0 (iPod touch; CPU iPhone OS 8_3 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) <strong>FxiOS/1.0</strong> Mobile/12F69 Safari/600.1.4</td></tr><tr class="even"><td>iPhone</td><td>Mozilla/5.0 (iPhone; CPU iPhone OS 8_3 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) <strong>FxiOS/1.0</strong> Mobile/12F69 Safari/600.1.4</td></tr><tr class="odd"><td>iPad</td><td>Mozilla/5.0 (iPad; CPU iPhone OS 8_3 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) <strong>FxiOS/1.0</strong> Mobile/12F69 Safari/600.1.4</td></tr></tbody></table>

Firefox Web Runtime
-------------------

The Web Runtime uses the same user agent string as desktop Firefox.

Other Gecko-based browsers
--------------------------

These are some sample UA strings from other Gecko-based browsers on various platforms. Note that many of these have not yet been released on Gecko 2.0!

<table><thead><tr class="header"><th>Browser</th><th>Gecko user agent string</th></tr></thead><tbody><tr class="odd"><td>Firefox for Maemo (Nokia N900)</td><td>Mozilla/5.0 (Maemo; Linux armv7l; rv:10.0.1) Gecko/20100101 Firefox/10.0.1 Fennec/10.0.1</td></tr><tr class="even"><td>Camino on Mac</td><td>Mozilla/5.0 (Macintosh; Intel Mac OS X 10.5; rv:2.0.1) Gecko/20100101 Firefox/4.0.1 Camino/2.2.1</td></tr><tr class="odd"><td>SeaMonkey on Windows</td><td>Mozilla/5.0 (Windows NT 5.2; rv:10.0.1) Gecko/20100101 Firefox/10.0.1 SeaMonkey/2.7.1</td></tr><tr class="even"><td>SeaMonkey on Mac</td><td>Mozilla/5.0 (Macintosh; Intel Mac OS X 10.5; rv:10.0.1) Gecko/20100101 Firefox/10.0.1 SeaMonkey/2.7.1</td></tr><tr class="odd"><td>SeaMonkey on Linux</td><td>Mozilla/5.0 (X11; Linux i686; rv:10.0.1) Gecko/20100101 Firefox/10.0.1 SeaMonkey/2.7.1</td></tr></tbody></table>

Implementation notes for applications, vendors, and extensions
--------------------------------------------------------------

Prior to Firefox 4 and Gecko 2.0, it was possible for extensions to add user agent parts through the `general.useragent.extra.identifier` preferences, (see the [obsolete User Agent Strings Reference](https://developer.mozilla.org/En/User_Agent_Strings_Reference)). But that has not been possible since [bug 581008](https://bugzilla.mozilla.org/show_bug.cgi?id=581008).

In the past, specific plug-ins, add-ons or extensions added user agent parts to notify sites they were installed. The recommended way to do this, if it's absolutely necessary (remember that it slows down every request) is to [set a custom HTTP header](https://developer.mozilla.org/en/Setting_HTTP_request_headers).

See Also
--------

-   [Firefox OS User Agent String](http://lawrencemandel.com/2012/07/27/decision-made-firefox-os-user-agent-string/) (blog post w/[bug 777710](https://bugzilla.mozilla.org/show_bug.cgi?id=777710) reference)
-   [Final User Agent string for Firefox 4](https://hacks.mozilla.org/2010/09/final-user-agent-string-for-firefox-4/) (blog post)
-   Recommendations on [sniffing the UA string for cross-browser support](https://developer.mozilla.org/en/Browser_Detection_and_Cross_Browser_Support)
-   [window.navigator.userAgent](https://developer.mozilla.org/en-US/docs/en/DOM/window.navigator.userAgent)
-   [Add Android version to Fennec UA String (bug 1169772)](https://bugzilla.mozilla.org/show_bug.cgi?id=1169772)

Comments to <a href="news://news.mozilla.org/netscape.public.mozilla.netlib" class="link-news">mozilla.dev.platform</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent/Firefox$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent/Firefox" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent/Firefox</a>
