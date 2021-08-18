Navigator.doNotTrack
====================

The `Navigator.doNotTrack` property returns the user's Do Not Track setting, which indicates whether the user is requesting web sites and advertisers to not track them.

The value of the property reflects that of the [`DNT`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/DNT) HTTP header, i.e. values of `"1"`, `"0"`, or `"unspecified"`.

Example
-------

    console.log(navigator.doNotTrack);
    // prints "1" if DNT is enabled; "0" if the user opted-in for tracking; otherwise this is "unspecified"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/tracking-dnt/#dom-navigator-donottrack">Tracking Preference Expression (DNT)<br />
<span class="small">The definition of 'Navigator.doNotTrack' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

See also
--------

-   [The Do Not Track field guide](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/DNT)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/doNotTrack" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/doNotTrack</a>
