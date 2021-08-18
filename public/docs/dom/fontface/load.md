# FontFace.load

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `load()` method of the [`FontFace`](../fontface) interface loads a font based on current object's constructor-passed requirements, including a location or source buffer, and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with the current FontFace object.

## Syntax

    var promise = FontFace.load();

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a reference to the current `FontFace` object when the font loads or rejects with a [NetworkError](../domexception#exception-networkerror) if the loading process fails.

### Exceptions

NetworkError  
Indicates that the attempt to load the font failed.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-font-loading/#font-face-load">CSS Font Loading Module Level 3<br />
<span class="small">The definition of 'load' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`load`

45

35-45

Before Chrome 45, the returned promise resolved with void instead of a `FontFace` object as required by the specification.

79

Yes

No

Yes

10

45

37-45

Before WebView 45, the returned promise resolved with void instead of a `FontFace` object as required by the specification.

45

35-45

Before Chrome 45, the returned promise resolved with void instead of a `FontFace` object as required by the specification.

Yes

Yes

10

5.0

4.0-5.0

Before Samsung Internet 5.0, the returned promise resolved with void instead of a `FontFace` object as required by the specification.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FontFace/load" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FontFace/load</a>
