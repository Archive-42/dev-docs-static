# Document.documentURIObject

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `Document.documentURIObject` read-only property returns an <span class="page-not-created">`nsIURI`</span> object representing the URI of the [document](../document).

This only works for privileged (UniversalXPConnect) scripts, including extension code. For web content this property doesn't have any special meaning and can be used just like any other custom property.

Privileged code must be careful not to try getting or setting this property on a non-wrapped content object (e.g., on a `wrappedJSObject` of an `XPCNativeWrapper`). See [bug 324464](https://bugzilla.mozilla.org/show_bug.cgi?id=324464)'s comments for details.

## Syntax

    var uri = document.documentURIObject;

## Example

    // Check that the URI scheme of the current tab in Firefox is 'http',
    // assuming this code runs in context of browser.xul
    let uriObj = content.document.documentURIObject;
    let uriPort = uriObj.port;

    if (uriObj.schemeIs('http')) {
      ...
    }

## Specifications

Not part of any specification.

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

`documentURIObject`

No

No

Yes-57

Available only to [legacy extensions](https://developer.mozilla.org/docs/Archive/Add-ons).

No

No

No

No

No

Yes-57

Available only to [legacy extensions](https://developer.mozilla.org/docs/Archive/Add-ons).

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/documentURIObject" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/documentURIObject</a>
