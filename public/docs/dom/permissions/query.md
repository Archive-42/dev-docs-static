Permissions.query()
===================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Permissions.query()` method of the [`Permissions`](../permissions) interface returns the state of a user permission on the global scope.

Syntax
------

    navigator.permissions.query(PermissionDescriptor).then(function(permissionStatus) { ... })

### Parameters

`PermissionDescriptor`  
An object that sets options for the `query` operation consisting of a comma-separated list of name-value pairs. The available options are:

-   `name`: The name of the API whose permissions you want to query. An up-to-date list of permission names can be found in the spec under the [PermissionName enum](https://w3c.github.io/permissions/#enumdef-permissionname), but bear in mind that the actual permissions supported by browsers is currently much smaller than this. Firefox for example currently supports `geolocation`, `notifications`, `push`, and `persistent-storage` (see our [`Permissions.webidl` file](https://dxr.mozilla.org/mozilla-central/source/dom/webidl/Permissions.webidl#10)).
-   `userVisibleOnly`: (Push only, not supported in Firefox — see the Browser Support section below) Indicates whether you want to show a notification for every message or be able to send silent push notifications. The default is `false`.
-   `sysex`: (Midi only) Indicates whether you need and/or receive system exclusive messages. The default is `false`.

**Note**: As of Firefox 44, the permissions for [Notifications](../notifications_api) and [Push](../push_api) have been merged. If permission is granted (e.g. by the user, in the relevant permissions dialog), `navigator.permissions.query()` will return `true` for both `notifications` and `push`.

**Note**: The `persistent-storage` permission allows an origin to use a persistent box (i.e [persistent storage](https://storage.spec.whatwg.org/#persistence)) for its storage, as per the [Storage API](https://storage.spec.whatwg.org/).

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`PermissionStatus`](../permissionstatus) object.

### Exceptions

<table><thead><tr class="header"><th>Exception</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><code>TypeError</code></td><td>Retrieving the <code>PermissionDescriptor</code> information failed in some way, or the permission doesn't exist or is currently unsupported (e.g. <code>midi</code>, or <code>push</code> with <code>userVisibleOnly</code>).</td></tr></tbody></table>

Example
-------

    navigator.permissions.query({name:'geolocation'}).then(function(result) {
     if (result.state == 'granted') {
       showLocalNewsWithGeolocation();
     } else if (result.state == 'prompt') {
       showButtonToEnableLocalNews();
     }
     // Don't do anything if the permission was denied.
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/permissions/#dom-permissions-query">Permissions<br />
<span class="small">The definition of 'query()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`query`

43

79

46

No

Yes

No

No

43

46

Yes

No

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Permissions/query" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Permissions/query</a>
