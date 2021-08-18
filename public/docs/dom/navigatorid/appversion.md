# NavigatorID.appVersion

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Returns either "`4.0`" or a string representing version information about the browser.

**Note**

Do not rely on this property to return the correct browser version.

## Syntax

    window.navigator.appVersion

### Value

Either "`4.0`" or a string representing version information about the browser.

## Example

    alert('Your browser version is reported as ' + navigator.appVersion);

## Notes

The `window.navigator.userAgent` property may also contain the version number (for example "`Mozilla/5.0 (Windows; U; Win98; en-US; rv:0.9.2) Gecko/20010725 Netscape 6/6.1`"), but you should be aware of how easy it is to change the user agent string and "spoof" other browsers, platforms, or user agents, and also how cavalier the browser vendor themselves are with these properties.

The `window.navigator.appVersion`, `window.navigator.appName` and `window.navigator.userAgent` properties have been used in "browser sniffing" code: scripts that attempt to find out what kind of browser you are using and adjust pages accordingly. This lead to the current situation, where browsers had to return fake values from these properties in order not to be locked out of some websites.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-navigator-appversion">HTML Living Standard<br />
<span class="small">The definition of 'NavigatorID.appVersion' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`appVersion`

1

12

1

3

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/appVersion" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/appVersion</a>
