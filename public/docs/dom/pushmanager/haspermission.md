# PushManager.hasPermission()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `PushManager.hasPermission()` method of the [`PushManager`](../pushmanager) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the `PushPermissionStatus` of the requesting webapp, which will be one of `granted`, `denied`, or `default`.

## Syntax

    PushManager.hasPermission().then(function(pushPermissionStatus) { ... } );

## Example

    // TBD

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/">Push API</a></td><td><span class="spec-wd">Working Draft</span></td><td>Defines the <code>PushManager</code> interface.</td></tr></tbody></table>

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

`hasPermission`

42

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

29

No

No

42

48

Push enabled by default.

29

No

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushManager/hasPermission" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushManager/hasPermission</a>
