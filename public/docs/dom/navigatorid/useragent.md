# NavigatorID.userAgent

The `NavigatorID.userAgent` read-only property returns the user agent string for the current browser.

The specification asks browsers to provide as little information via this field as possible. Never assume that the value of this property will stay the same in future versions of the same browser. Try not to use it at all, or only for current and past versions of a browser. New browsers may start using the same UA, or part of it, as an older browser: you really have no guarantee that the browser agent is indeed the one advertised by this property.

Also keep in mind that users of a browser can change the value of this field if they want (UA spoofing).

Browser identification based on detecting the user agent string is **unreliable** and **is not recommended**, as the user agent string is user configurable. For example:

- In Firefox, you can change the preference `general.useragent.override` in `about:config`. Some Firefox extensions do that; however, this only changes the HTTP header that gets sent, and doesn't affect browser detection performed by JavaScript code.
- Opera 6+ allows users to set the browser identification string via a menu.
- Microsoft Internet Explorer uses the Windows registry.
- Safari and iCab allow users to change the browser user agent string to predefined Internet Explorer or Netscape strings via a menu.

## Syntax

    var ua = navigator.userAgent;

### Value

A [`DOMString`](../domstring) specifying the complete user agent string the browser provides both in [HTTP](https://developer.mozilla.org/en-US/docs/Glossary/HTTP) headers and in response to this and other related methods on the [`Navigator`](../navigator) object.

The user agent string is built on a formal structure which can be decomposed into several pieces of info. Each of these pieces of info comes from other navigator properties which are also settable by the user. Gecko-based browsers comply with the following general structure:

    userAgent = appCodeName/appVersion number (Platform; Security; OS-or-CPU;
    Localization; rv: revision-version-number) product/productSub
    Application-Name Application-Name-version

## Example

    alert(window.navigator.userAgent)
    // alerts "Mozilla/5.0 (Windows; U; Win98; en-US; rv:0.9.2) Gecko/20010725 Netscape6/6.1"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-navigator-useragent">HTML Living Standard<br />
<span class="small">The definition of 'NavigatorID.userAgent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`userAgent`

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

## See also

- [`User-Agent`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent) HTTP header

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/userAgent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NavigatorID/userAgent</a>
