# MediaKeyStatusMap

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `MediaKeyStatusMap` interface of the [EncryptedMediaExtensions API](encrypted_media_extensions_api) is a read-only map of media key statuses by key IDs.

## Properties

[`MediaKeyStatusMap.size`](mediakeystatusmap/size) <span class="badge inline readonly">Read only </span>  
Returns the number of key/value pars in the status map.

## Methods

[`MediaKeyStatusMap.entries()`](mediakeystatusmap/entries) <span class="badge inline readonly">Read only </span>  
Returns a new `Iterator` object containing an array of `[key, value]` for each element in the status map, in insertion order.

[`MediaKeyStatusMap.forEach(callback[, argument])`](mediakeystatusmap/foreach) <span class="badge inline readonly">Read only </span>  
Calls `callback` once for each key-value pair in the status map, in insertion order. If `argument` is present it will be passed to the callback.

[`MediaKeyStatusMap.get()`](mediakeystatusmap/get) <span class="badge inline readonly">Read only </span>  
Returns the value associated with the given key, or `undefined` if there is none.

[`MediaKeyStatusMap.has()`](mediakeystatusmap/has) <span class="badge inline readonly">Read only </span>  
Returns a boolean asserting whether a value has been associated with the given key.

[`MediaKeyStatusMap.keys()`](mediakeystatusmap/keys) <span class="badge inline readonly">Read only </span>  
Returns a new `Iterator` object containing keys for each element in the status map, in insertion order.

[`MediaKeyStatusMap.values()`](mediakeystatusmap/values) <span class="badge inline readonly">Read only </span>  
Returns a new `Iterator` object containing values for each element in the status map, in insertion order.

<span class="page-not-created">`MediaKeyStatusMap.[@@iterator]()`</span> <span class="badge inline readonly">Read only </span>  
Returns a new `Iterator` object containing an array of `[key, value]` for each element in the status map, in insertion order.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/encrypted-media/#mediakeystatusmap-interface">Encrypted Media Extensions<br />
<span class="small">The definition of 'MediaKeyStatusMap' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`MediaKeyStatusMap`

42

13

38

No

29

12.1

43

42

38

29

12.2

4.0

`entries`

42

16

38

No

29

12.1

43

42

38

29

12.2

4.0

`forEach`

42

13

47

No

29

12.1

43

42

47

29

12.2

4.0

`get`

42

13

45

No

29

12.1

43

42

45

29

12.2

4.0

`has`

42

13

45

No

29

12.1

43

42

45

29

12.2

4.0

`keys`

42

16

38

No

29

12.1

43

42

38

29

12.2

4.0

`size`

42

13

38

No

29

12.1

43

42

38

29

12.2

4.0

`values`

42

16

38

No

29

12.1

43

42

38

29

12.2

4.0

`@@iterator`

42

16

45

No

29

12.1

43

42

45

29

12.2

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaKeyStatusMap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaKeyStatusMap</a>
