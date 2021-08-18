# Navigator

The `Navigator` interface represents the state and the identity of the user agent. It allows scripts to query it and to register themselves to carry on some activities.

A `Navigator` object can be retrieved using the read-only [`window.navigator`](window/navigator) property.

## Properties

_Doesn't inherit any properties, but implements those defined in [`NavigatorID`](navigatorid), [`NavigatorLanguage`](navigatorlanguage), [`NavigatorOnLine`](navigatoronline), <span class="page-not-created">`NavigatorContentUtils`</span>, [`NavigatorStorage`](navigatorstorage), <span class="page-not-created">`NavigatorStorageUtils`</span>, [`NavigatorConcurrentHardware`](navigatorconcurrenthardware), [`NavigatorPlugins`](navigatorplugins), and <span class="page-not-created">`NavigatorUserMedia`</span>._

### Standard properties

[`Navigator.connection`](navigator/connection) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Provides a [`NetworkInformation`](networkinformation) object containing information about the network connection of a device.

[`Navigator.cookieEnabled`](navigator/cookieenabled) <span class="badge inline readonly">Read only </span>  
Returns false if setting a cookie will be ignored and true otherwise.

[`Navigator.credentials`](navigator/credentials) <span class="badge inline readonly">Read only </span>  
Returns the [`CredentialsContainer`](credentialscontainer) interface which exposes methods to request credentials and notify the user agent when interesting events occur such as successful sign in or sign out.

[`Navigator.deviceMemory`](navigator/devicememory) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns the amount of device memory in gigabytes. This value is an approximation given by rounding to the nearest power of 2 and dividing that number by 1024.

[`Navigator.doNotTrack`](navigator/donottrack) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Reports the value of the user's do-not-track preference. When this value is "yes", your web site or application should not track the user.

[`Navigator.geolocation`](navigator/geolocation) <span class="badge inline readonly">Read only </span>  
Returns a [`Geolocation`](geolocation) object allowing accessing the location of the device.

[`Navigator.hid`](navigator/hid) <span class="badge inline readonly">Read only </span>  
Returns an [`HID`](hid) object providing methods for connecting to HID devices, listing attached HID devices, and event handlers for connected HID devices.

[`NavigatorConcurrentHardware.hardwareConcurrency`](navigatorconcurrenthardware/hardwareconcurrency) <span class="badge inline readonly">Read only </span>  
Returns the number of logical processor cores available.

[`NavigatorPlugins.javaEnabled`](navigatorplugins/javaenabled) <span class="badge inline readonly">Read only </span>  
Returns false.

[`Navigator.keyboard`](navigator/keyboard) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns a [`Keyboard`](keyboard) object which provides access to functions that retrieve keyboard layout maps and toggle capturing of key presses from the physical keyboard.

[`NavigatorLanguage.language`](navigatorlanguage/language) <span class="badge inline readonly">Read only </span>  
Returns a [`DOMString`](domstring) representing the preferred language of the user, usually the language of the browser UI. The `null` value is returned when this is unknown.

[`NavigatorLanguage.languages`](navigatorlanguage/languages) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns an array of [`DOMString`](domstring) representing the languages known to the user, by order of preference.

[`Navigator.locks`](navigator/locks) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns a [`LockManager`](lockmanager) object which provides methods for requesting a new [`Lock`](lock) object and querying for an existing [`Lock`](lock) object

[`Navigator.maxTouchPoints`](navigator/maxtouchpoints) <span class="badge inline readonly">Read only </span>  
Returns the maximum number of simultaneous touch contact points are supported by the current device.

[`Navigator.mediaCapabilities`](navigator/mediacapabilities) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns a [`MediaCapabilities`](mediacapabilities) object that can expose information about the decoding and encoding capabilities for a given format and output capabilities.

[`Navigator.mediaDevices`](navigator/mediadevices) <span class="badge inline readonly">Read only </span>  
Returns a reference to a [`MediaDevices`](mediadevices) object which can then be used to get information about available media devices ([`MediaDevices.enumerateDevices()`](mediadevices/enumeratedevices)), find out what constrainable properties are supported for media on the user's computer and user agent ([`MediaDevices.getSupportedConstraints()`](mediadevices/getsupportedconstraints)), and to request access to media using [`MediaDevices.getUserMedia()`](mediadevices/getusermedia).

[`Navigator.mediaSession`](navigator/mediasession) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns [`MediaSession`](mediasession) object which can be used to provide metadata that can be used by the browser to present information about the currently-playing media to the user, such as in a global media controls UI.

[`NavigatorPlugins.mimeTypes`](navigatorplugins/mimetypes) <span class="badge inline readonly">Read only </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns an [`MimeTypeArray`](mimetypearray) listing the MIME types supported by the browser.

[`NavigatorOnLine.onLine`](navigatoronline/online) <span class="badge inline readonly">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the browser is working online.

[`Navigator.permissions`](navigator/permissions) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns a [`Permissions`](permissions) object that can be used to query and update permission status of APIs covered by the [Permissions API](permissions_api).

[`NavigatorPlugins.plugins`](navigatorplugins/plugins) <span class="badge inline readonly">Read only </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns a [`PluginArray`](pluginarray) listing the plugins installed in the browser.

[`Navigator.presentation`](navigator/presentation) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns a reference to the [`Presentation`](presentation) API.

[`Navigator.serial`](navigator/serial) <span class="badge inline readonly">Read only </span>  
Returns a [`Serial`](serial) object, which represents the entry point into the <span class="page-not-created">`Web Serial API`</span> to enable the control of serial ports.

[`Navigator.serviceWorker`](navigator/serviceworker) <span class="badge inline readonly">Read only </span>  
Returns a [`ServiceWorkerContainer`](serviceworkercontainer) object, which provides access to registration, removal, upgrade, and communication with the [`ServiceWorker`](serviceworker) objects for the [associated document](https://html.spec.whatwg.org/multipage/browsers.html#concept-document-window).

[`NavigatorStorage.storage`](navigatorstorage/storage) <span class="badge inline readonly">Read only </span>  
Returns the singleton [`StorageManager`](storagemanager) object used for managing persistence permissions and estimating available storage on a site-by-site/app-by-app basis.

[`NavigatorID.userAgent`](navigatorid/useragent) <span class="badge inline readonly">Read only </span>  
Returns the user agent string for the current browser.

[`Navigator.vendor`](navigator/vendor) <span class="badge inline readonly">Read only </span>  
Returns the vendor name of the current browser (e.g., "Netscape6").

[`Navigator.webdriver`](navigator/webdriver) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Indicates whether the user agent is controlled by automation.

[`Navigator.xr`](navigator/xr) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns [`XRSystem`](xrsystem) object, which represents the entry point into the [WebXR API](webxr_device_api).

### Non-standard properties

[`Navigator.buildID`](navigator/buildid) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Returns the build identifier of the browser. In modern browsers this property now returns a fixed timestamp as a privacy measure, e.g. `20181001000000` in Firefox 64 onwards.

[`Navigator.contacts`](navigator/contacts) <span class="badge inline readonly">Read only </span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Returns a [`ContactsManager`](contactsmanager) interface which allows users to select entries from their contact list and share limited details of the selected entries with a website or application.

<span class="page-not-created">`Navigator.securitypolicy`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Returns an empty string. In Netscape 4.7x, returns "US & CA domestic policy" or "Export policy".

<span class="page-not-created">`Navigator.standalone`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Returns a boolean indicating whether the browser is running in standalone mode. Available on Apple's iOS Safari only.

[`Navigator.wakeLock`](navigator/wakelock) <span class="badge inline readonly">Read only </span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Returns a [`WakeLock`](wakelock) interface you can use to request screen wake locks and prevent screen from dimming, turning off, or showing a screen saver.

### Deprecated properties

[`NavigatorID.appCodeName`](navigatorid/appcodename) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns the internal "code" name of the current browser. Do not rely on this property to return the correct value.

[`NavigatorID.appName`](navigatorid/appname) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns a [`DOMString`](domstring) with the official name of the browser. Do not rely on this property to return the correct value.

[`NavigatorID.appVersion`](navigatorid/appversion) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns the version of the browser as a [`DOMString`](domstring). Do not rely on this property to return the correct value.

[`Navigator.activeVRDisplays`](navigator/activevrdisplays) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns an array containing every [`VRDisplay`](vrdisplay) object that is currently presenting ([`VRDisplay.ispresenting`](vrdisplay/ispresenting) is `true`).

[`Navigator.battery`](navigator/battery) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns a [`BatteryManager`](batterymanager) object you can use to get information about the battery charging status.

[`Navigator.oscpu`](navigator/oscpu) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns a string that represents the current operating system.

[`NavigatorID.platform`](navigatorid/platform) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns a string representing the platform of the browser. Do not rely on this function to return a significant value.

[`NavigatorID.product`](navigatorid/product) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Always returns `'Gecko'`, on any browser. This property is kept only for compatibility purpose.

[`Navigator.productSub`](navigator/productsub) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns the build number of the current browser (e.g., "20060909").

[`Navigator.vendorSub`](navigator/vendorsub) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns the vendor version number (e.g. "6.1").

## Methods

_Doesn't inherit any method, but implements those defined in [`NavigatorID`](navigatorid), <span class="page-not-created">`NavigatorContentUtils`</span>, <span class="page-not-created">`NavigatorUserMedia`</span>, and <span class="page-not-created">`NavigatorStorageUtils`</span>._

[`Navigator.canShare()`](navigator/canshare)  
Returns `true` if a call to `Navigator.share()` would succeed.

[`Navigator.clearAppBadge()`](navigator/clearappbadge)  
Clears a badge on the current app's icon and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

[`Navigator.registerProtocolHandler()`](navigator/registerprotocolhandler)  
Allows web sites to register themselves as a possible handler for a given protocol.

[`Navigator.requestMediaKeySystemAccess()`](navigator/requestmediakeysystemaccess)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) for a MediaKeySystemAccess object.

[`Navigator.sendBeacon()`](navigator/sendbeacon)  
Used to asynchronously transfer a small amount of data using [HTTP](https://developer.mozilla.org/en-US/docs/Glossary/HTTP) from the User Agent to a web server.

[`Navigator.setAppBadge()`](navigator/setappbadge)  
Sets a badge on the icon associated with this app and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

[`Navigator.share()`](navigator/share)  
Invokes the native sharing mechanism of the current platform.

[`Navigator.vibrate()`](navigator/vibrate)  
Causes vibration on devices with support for it. Does nothing if vibration support isn't available.

### Deprecated methods

[`Navigator.getVRDisplays()`](navigator/getvrdisplays) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns a promise that resolves to an array of [`VRDisplay`](vrdisplay) objects representing any available VR devices connected to the computer.

[`Navigator.getUserMedia()`](navigator/getusermedia) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
After having prompted the user for permission, returns the audio or video stream associated to a camera or microphone on the local computer.

[`Navigator.registerContentHandler()`](navigator/registercontenthandler) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Allows web sites to register themselves as a possible handler for a given MIME type.

[`NavigatorID.taintEnabled()`](navigatorid/taintenabled) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns `false`. JavaScript taint/untaint functions removed in JavaScript 1.2.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#the-navigator-object">HTML Living Standard<br />
<span class="small">The definition of 'the Navigator object' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

## Browser compatibility

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`Navigator`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

`activeVRDisplays`

No

15-79

WebVR content requires a Windows Mixed Reality headset or the Windows Mixed Reality Portal Simulator.

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

No

No

No

79-80

Supported only by Google Daydream.

55

No

No

12.0-13.0

Supported only by Google Daydream.

`authentication`

67

79

No

No

?

No

No

67

No

?

No

No

`bluetooth`

70

79

No

No

57

No

70

70

No

49

No

10.0

`buildID`

No

No

64

Returns a fixed timestamp as a privacy measure - `20181001000000`.

2

No

?

?

No

No

64

Returns a fixed timestamp as a privacy measure - `20181001000000`.

Yes

?

?

No

`canShare`

89

Not supported on macOS, see [bug 1144920](https://crbug.com/1144920).

No

No

No

No

No

No

75

No

No

No

11.0

`clearAppBadge`

81

81

No

No

No

No

81

81

No

58

No

13.0

`clipboard`

66

79

63

No

53

13.1

66

66

63

47

13.4

9.0

`connection`

61

79

Yes

No

Yes

No

50

38

14

The Network API is enabled by default. Can be disabled using the `dom.netinfo.enabled` preference.

37

No

3.0

`contacts`

No

No

No

No

No

No

80

80

No

57

No

13.0

`cookieEnabled`

1

12

1

Prior to Firefox 8, `navigator.cookieEnabled` would report the wrong result if a site exception was in place for the page on which the check was performed. This has been fixed.

4

`navigator.cookieEnabled` returns `true even if the browser is set to block cookies (for example, if the page is in the Restricted sites security zone).`

≤12.1

1

1

18

4

Prior to Firefox 8, `navigator.cookieEnabled` would report the wrong result if a site exception was in place for the page on which the check was performed. This has been fixed.

≤12.1

1

1.0

`credentials`

51

18

61

No

38

13

51

51

61

41

13

5.0

`deviceMemory`

63

79

No

No

50

No

63

63

No

46

No

8.0

`doNotTrack`

23

17

Edge prior to version 17 implemented `window.doNotTrack`.

9

Prior to Firefox 32, `navigator.doNotTrack` would report values of `yes` and `no` rather than `1` and `0`.

9-11

For IE11 and subsequent versions, use `window.doNotTrack`

12

5.1-7

Safari 7.1.3+ uses `window.doNotTrack` rather than `navigator.doNotTrack`.

≤37

Yes

9

Prior to Firefox 32, `navigator.doNotTrack` would report values of `yes` and `no` rather than `1` and `0`.

?

?

Yes

`geolocation`

5

12

3.5

9

10.6

5

≤37

18

4

11

4.2

1.0

`getBattery`

38

79

43-52

No

25

No

38

38

43-52

25

No

3.0

`getGamepads`

35

21

12

29

No

22

15

10.1

37

≤37

35

25

No

22

14

10.3

3.0

1.5

`getInstalledRelatedApps`

85

Only supported on Windows. Resolves with an empty array on other platforms.

80-85

Always resolves with an empty array.

85

Only supported on Windows. Resolves with an empty array on other platforms.

80-85

Always resolves with an empty array.

No

No

71

Only supported on Windows. Resolves with an empty array on other platforms.

67-71

Always resolves with an empty array.

No

No

80

No

No

No

13.0

`getUserMedia`

53

21

12

79

17

The constraint syntax described here is available as of Firefox 38. Earlier versions (32-37) used an outdated constraint syntax, but the syntax described here is available there through the [adapter.js](https://github.com/webrtc/adapter) polyfill.

No

40

15

12-15

11-12

53

40

53

25

24

The constraint syntax described here is available as of Firefox 38. Earlier versions (32-37) used an outdated constraint syntax, but the syntax described here is available there through the [adapter.js](https://github.com/webrtc/adapter) polyfill.

41

14

12-14

11-12

6.0

1.5

`getVRDisplays`

No

Available on all platforms behind a flag, but currently only works on desktop in an [experimental version of Chrome](https://webvr.info/get-chrome/) (other builds won't return any devices when `Navigator.getVRDisplays()` is invoked).

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

No

No

No

Yes-80

Currently supported only by Google Daydream.

55

No

No

Yes-13.0

Currently supported only by Google Daydream.

`keyboard`

68

79

No

No

55

No

68

No

No

No

No

No

`locks`

69

79

No

No

56

No

69

69

No

48

No

10.0

`maxTouchPoints`

35

12

59

29

11

10

Yes

13

37

35

79

29

See [bug 1426786](https://bugzil.la/1426786).

Yes

13

3.0

`mediaCapabilities`

66

79

63

No

55

13

66

66

63

48

13

9.0

`mediaDevices`

47

12

36

No

34

11

47

47

36

34

11

5.0

`mediaSession`

73

79

82

71

No

No

No

No

57

82

No

No

7.0

`mozIsLocallyAvailable`

No

No

3-35

No

No

No

No

No

4-35

No

No

No

`oscpu`

No

No

1

The preference `"general.oscpu.override"` can be used to set a value to be returned instead of the true CPU description. The preference setting is ignored for calls made by privileged code, which continue to get the actual CPU description.

No

No

No

No

No

4

The preference `"general.oscpu.override"` can be used to set a value to be returned instead of the true CPU description. The preference setting is ignored for calls made by privileged code, which continue to get the actual CPU description.

No

No

No

`permissions`

43

79

46

No

Yes

No

No

See [bug 490120](https://crbug.com/490120)

43

46

Yes

No

4.0

`presentation`

47

79

51-88

No

34

No

No

See [bug 521319](https://crbug.com/521319)

47

51-79

34

No

5.0

`productSub`

1

Always returns `20030107`.

12

Always returns `20030107`.

1

No

15

Always returns `20030107`.

1

Always returns `20030107`.

1

Always returns `20030107`.

18

Always returns `20030107`.

4

14

Always returns `20030107`.

1

Always returns `20030107`.

1.0

Always returns `20030107`.

`registerContentHandler`

4-6

No

2-62

No

≤12.1-15

?

No

No

?

≤12.1-14

?

No

`registerProtocolHandler`

13

\["Allowed schemes include `mailto`, `mms`, `nntp`, `rtsp`, and `webcal`. Custom protocols must be prefixed with `web+`.", "From Chrome 77, the URL parameter only accepts `http` or `https` URLs.", "The obsolete `title` argument is required."\]

79

\["Allowed schemes include `mailto`, `mms`, `nntp`, `rtsp`, and `webcal`. Custom protocols must be prefixed with `web+`.", "The obsolete `title` argument is required."\]

3

No

11.6

The obsolete `title` argument is required.

No

No

No

No

No

No

No

`requestMediaKeySystemAccess`

42

\["The spec requires that the passed `supportedConfigurations` option contain at least one of `audioCapabilities` or `videoCapabilities`, and that said parameters include a codec string.", "The function does not exist in insecure contexts. This was not enforced until Chrome 58."\]

13

38

\["Starting in Firefox 55, if neither `audioCapabilities` nor `videoCapabilities` is specified in `supportedConfigurations`, a warning is output to the web console.", "In addition, starting in Firefox 55, if in `supportedConfigurations`, either `audioCapabilities`'s or `videoCapabilities`'s `contentType` value doesn't specify a \\"codecs\\" substring to define allowed codecs within the media wrapper, a warning is output to the web console. See note below table for example and correction.", "In the future, if neither `audioCapabilities` nor `videoCapabilities` is specified in the `supportedConfigurations`, a `NotSupported` exception will be thrown."\]

No

29

\["The spec requires that the passed `supportedConfigurations` option contain at least one of `audioCapabilities` or `videoCapabilities`, and that said parameters include a codec string.", "The function does not exist in insecure contexts. This was not enforced until Opera 45."\]

13.1

43

\["The spec requires that the passed `supportedConfigurations` option contain at least one of `audioCapabilities` or `videoCapabilities`, and that said parameters include a codec string.", "The function does not exist in insecure contexts. This was not enforced until version 58."\]

42

\["The spec requires that the passed `supportedConfigurations` option contain at least one of `audioCapabilities` or `videoCapabilities`, and that said parameters include a codec string.", "The function does not exist in insecure contexts. This was not enforced until Chrome 58."\]

38

\["Starting in Firefox 55, if neither `audioCapabilities` nor `videoCapabilities` is specified in `supportedConfigurations`, a warning is output to the web console.", "In addition, starting in Firefox 55, if in `supportedConfigurations`, either `audioCapabilities`'s or `videoCapabilities`'s `contentType` value doesn't specify a \\"codecs\\" substring to define allowed codecs within the media wrapper, a warning is output to the web console. See note below table for example and correction.", "In the future, if neither `audioCapabilities` nor `videoCapabilities` is specified in the `supportedConfigurations`, a `NotSupported` exception will be thrown."\]

29

\["The spec requires that the passed `supportedConfigurations` option contain at least one of `audioCapabilities` or `videoCapabilities`, and that said parameters include a codec string.", "The function does not exist in insecure contexts. This was not enforced until Opera 45."\]

13.4

4.0

\["The spec requires that the passed `supportedConfigurations` option contain at least one of `audioCapabilities` or `videoCapabilities`, and that said parameters include a codec string.", "The function does not exist in insecure contexts. This was not enforced until Samsung Internet 7.0."\]

`requestMIDIAccess`

43

79

No

No

30

No

43

43

No

30

No

4.0

`scheduling`

87

No

No

No

No

No

87

87

No

No

No

14.0

`sendBeacon`

39

Starting in Chrome 59, this method cannot send a `Blob` whose type is not CORS safelisted. This is a temporary change until a mitigation can be found for the security issues that this creates. For more information see [Chrome bug 720283](https://crbug.com/720283).

14

31

No

26

Starting in Opera 46, this method cannot send a `Blob` whose type is not CORS safelisted. This is a temporary change until a mitigation can be found for the security issues that this creates. For more information see [Chrome bug 720283](https://crbug.com/720283).

11.1

40

Starting in Chrome 59, this method cannot send a `Blob` whose type is not CORS safelisted. This is a temporary change until a mitigation can be found for the security issues that this creates. For more information see [Chrome bug 720283](https://crbug.com/720283).

42

Starting in Chrome 59, this method cannot send a `Blob` whose type is not CORS safelisted. This is a temporary change until a mitigation can be found for the security issues that this creates. For more information see [Chrome bug 720283](https://crbug.com/720283).

31

26

Starting in Opera 46, this method cannot send a `Blob` whose type is not CORS safelisted. This is a temporary change until a mitigation can be found for the security issues that this creates. For more information see [Chrome bug 720283](https://crbug.com/720283).

11.3

4.0

Starting in Samsung Internet 7.0, this method cannot send a `Blob` whose type is not CORS safelisted. This is a temporary change until a mitigation can be found for the security issues that this creates. For more information see [Chrome bug 720283](https://crbug.com/720283).

`serial`

89

89

No

No

No

No

No

No

No

No

No

No

`serviceWorker`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

`setAppBadge`

81

81

No

No

No

No

81

81

No

58

No

13.0

`share`

89

Not supported on macOS, see [bug 1144920](https://crbug.com/1144920).

81

No

No

No

12.1

No

61

79

Firefox for Android does not support sharing files or text.

48

12.2

8.0

`unregisterProtocolHandler`

38

79

No

No

25

≤12.1-15

No

No

No

No

No

No

No

`usb`

61

79

No

No

48

No

61

61

No

45

No

8.0

`vendor`

1

12

1

11

15

1

1

18

4

14

1

1.0

`vendorSub`

1

12

1

No

15

3

1

18

4

14

1

1.0

`vibrate`

32

79

16

\["Until Firefox 26 included, when the vibration pattern was too long or any of its elements too large, Firefox threw an exception instead of returning `false` ([bug 884935](https://bugzil.la/884935)).", "From Firefox 32 onwards, when the vibration pattern is too long or any of its elements too large, it returns `true` but truncates the pattern ([bug 1014581](https://bugzil.la/1014581)).", "Beginning in Firefox 72, this is not supported in cross-origin iframes."\]

11-true

No

No

No

4.4.3

\["Beginning in version 55, this is not supported in cross-origin iframes.", "Beginning in version 60, this method requires a user gesture. Otherwise it returns `false`."\]

32

\["Beginning in Chrome 55, this is not supported in cross-origin iframes.", "Beginning in Chrome 60, this method requires a user gesture. Otherwise it returns `false`."\]

79

Vibration is disabled. If the window is visible, then `navigator.vibrate()` returns `true`, but no vibration takes place (regardless of hardware support). See [bug 1591113.](https://bugzil.la/1591113)

16-79

\["Until Firefox 26 included, when the vibration pattern was too long or any of its elements too large, Firefox threw an exception instead of returning `false` ([bug 884935](https://bugzil.la/884935)).", "From Firefox 32 onwards, when the vibration pattern is too long or any of its elements too large, it returns `true` but truncates the pattern ([bug 1014581](https://bugzil.la/1014581))."\]

14-true

Yes

Beginning in Opera 47, this method requires a user gesture. Otherwise it returns `false`.

No

2.0

\["Beginning in Samsung Internet 6.0, this is not supported in cross-origin iframes.", "Beginning in Samsung Internet 8.0, this method requires a user gesture. Otherwise it returns `false`."\]

`wakeLock`

84

84

No

No

Yes

No

84

84

No

Yes

No

14.0

`webdriver`

63

12

60

11

50

10

No

63

60

46

10

8.0

`xr`

79

79

No

No

No

No

No

79

No

No

No

11.2

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator</a>
