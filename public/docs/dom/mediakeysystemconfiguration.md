MediaKeySystemConfiguration
===========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `MediaKeySystemConfiguration` dictionary holds configuration information about the media key system in use.

Properties
----------

 [`MediaKeySystemConfiguration.initDataTypes`](mediakeysystemconfiguration/initdatatypes) <span class="badge inline readonly">Read only </span>   
Returns a list of supported initialization data type names. An initialization data type is a string indicating the format of the initialization data.

 [`MediaKeySystemConfiguration.audioCapabilities`](mediakeysystemconfiguration/audiocapabilities) <span class="badge inline readonly">Read only </span>   
Returns a list of supported audio type and capability pairs.

 [`MediaKeySystemConfiguration.videoCapabilities`](mediakeysystemconfiguration/videocapabilities) <span class="badge inline readonly">Read only </span>   
Returns a list of supported video type and capability pairs.

 [`MediaKeySystemConfiguration.distinctiveIdentifier`](mediakeysystemconfiguration/distinctiveidentifier) <span class="badge inline readonly">Read only </span>   
Indicates whether a persistent distinctive identifier is required.

 [`MediaKeySystemConfiguration.persistentState`](mediakeysystemconfiguration/persistentstate) <span class="badge inline readonly">Read only </span>   
Indicates whether the ability to persist state is required.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/encrypted-media/#mediakeysystemconfiguration-dictionary">Encrypted Media Extensions<br />
<span class="small">The definition of 'MediaKeySystemConfiguration' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

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

`MediaKeySystemConfiguration`

42

≤79

?

No

?

?

43

42

?

?

?

4.0

`audioCapabilities`

42

≤79

?

No

?

?

43

42

?

?

?

4.0

`distinctiveIdentifier`

42

≤79

?

No

?

?

43

42

?

?

?

4.0

`initDataTypes`

42

≤79

?

No

?

?

43

42

?

?

?

4.0

`persistentState`

42

≤79

?

No

?

?

43

42

?

?

?

4.0

`videoCapabilities`

42

≤79

?

No

?

?

43

42

?

?

?

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySystemConfiguration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySystemConfiguration</a>
