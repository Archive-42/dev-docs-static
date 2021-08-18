# Navigator.canShare()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `Navigator.canShare()` method of the Web Share API returns `true` if a call to [`navigator.share()`](share) would succeed.

## Syntax

    const canShare = navigator.canShare(data);

### Parameters

`data` <span class="badge inline optional">Optional</span>  
An object containing data to share that matches what you would pass to [`navigator.share()`](share).

### Return value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). True if data can be shared with [`Navigator.share()`](share).

## Examples

    if(navigator.canShare(data)) {
      // We can use share() to share the data! Woop!
    }

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

## See also

[`navigator.share()`](share)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/canShare" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/canShare</a>
