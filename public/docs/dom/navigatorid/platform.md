# NavigatorID.platform

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Returns a string representing the platform of the browser. The specification allows browsers to always return the empty string, so don't rely on this property to get a reliable answer.

## Syntax

    platform = navigator.platform

### Value

A [`DOMString`](../domstring) identifying the platform on which the browser is running, or an empty string if the browser declines to (or is unable to) identify the platform. `platform` is a string that must be an empty string or a string representing the platform on which the browser is executing.

For example: "`MacIntel`", "`Win32`", "`FreeBSD i386`", "`WebTV OS`"

## Example

    console.log(navigator.platform);

## Usage notes

Most browsers, including Chrome, Edge, and Firefox 63 and later, return `"Win32"` even if running on a 64-bit version of Windows. Internet Explorer and versions of Firefox prior to version 63 still report `"Win64"`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-navigator-platform">HTML Living Standard<br />
<span class="small">The definition of 'NavigatorID.platform' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`platform`

1

12

1

\["Prior to Firefox 69, `platform` would report running on a 32-bit CPU if running the 32-bit version of Firefox on a 64-bit system.", "You can override the value returned by `platform` by setting the preference `general.platform.override` to the string you wish to be returned instead."\]

4

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/platform" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/platform</a>
