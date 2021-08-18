MediaKeySystemAccess
====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `MediaKeySystemAccess` interface of the [EncryptedMediaExtensions API](encrypted_media_extensions_api) provides access to a Key System for decryption and/or a content protection provider. You can request an instance of this object using the [`Navigator.requestMediaKeySystemAccess()`](navigator/requestmediakeysystemaccess) method.

Properties
----------

 [`MediaKeySystemAccess.keySystem`](mediakeysystemaccess/keysystem) <span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) identifying the key system being used.

Methods
-------

[`MediaKeySystemAccess.createMediaKeys()`](mediakeysystemaccess/createmediakeys)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a new [`MediaKeys`](mediakeys) object.

[`MediaKeySystemAccess.getConfiguration()`](mediakeysystemaccess/getconfiguration)  
Returns a [`MediaKeySystemConfiguration`](mediakeysystemconfiguration) object with the supported combination of configuration options.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/encrypted-media/#mediakeysystemaccess-interface">Encrypted Media Extensions<br />
<span class="small">The definition of 'MediaKeySystemAccess' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`MediaKeySystemAccess`

42

13

38

No

Yes

12.1

43

42

38

Yes

12.2

4.0

`createMediaKeys`

42

13

38

No

Yes

12.1

43

42

38

Yes

12.2

4.0

`getConfiguration`

42

13

43

No

Yes

12.1

43

42

43

Yes

12.2

4.0

`keySystem`

42

13

38

No

Yes

12.1

43

42

38

Yes

12.2

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySystemAccess" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySystemAccess</a>
