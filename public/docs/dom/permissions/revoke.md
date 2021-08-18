# Permissions.revoke()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `Permissions.revoke()` method of the [`Permissions`](../permissions) interface reverts a currently set permission back to its default state, which is usually `prompt`.

## Syntax

This method is called on the global [`Permissions`](../permissions) object [`navigator.permissions`](../navigator/permissions).

    var revokePromise = navigator.permissions.revoke(descriptor);

### Parameters

`descriptor`  
An object based on the `PermissionDescriptor` dictionary that sets options for the operation consisting of a comma-separated list of name-value pairs. The available options are:

- `name`: The name of the API whose permissions you want to query. Valid values are `'geolocation'`, `'midi'`, `'notifications'`, and `'push'`.
- `userVisibleOnly`: (Push only, not supported in Firefox — see the [Browser compatibility](#browser_compatibility) section below) Indicates whether you want to show a notification for every message or be able to send silent push notifications. The default is `false`.
- `sysex`: (MIDI only) Indicates whether you need and/or receive system exclusive messages. The default is `false`.

**Note**: As of Firefox 44, the permissions for [Notifications](../notifications_api) and [Push](../push_api) have been merged. If permission is granted (e.g. by the user, in the relevant permissions dialog), `navigator.permissions.query()` will return `true` for both `notifications` and `push`.

**Note**: The `persistent-storage` permission allows an origin to use a persistent box (i.e [persistent storage](https://storage.spec.whatwg.org/#persistence)) for its storage, as per the [Storage API](https://storage.spec.whatwg.org/).

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that calls its fulfillment handler with a [`PermissionStatus`](../permissionstatus) object indicating the result of the request.

### Exceptions

`TypeError`  
Retrieving the `PermissionDescriptor` information failed in some way, or the permission doesn't exist or is currently unsupported (e.g. `midi`, or `push` with `userVisibleOnly`).

## Example

This function can be used by an app to request that its own Geolocation API permission be revoked.

    function revokePermission() {
      navigator.permissions.revoke({name:'geolocation'}).then(function(result) {
        report(result.state);
      });
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

`revoke`

46

79

51

47-51

No

33

No

No

46

51

47-51

33

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Permissions/revoke" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Permissions/revoke</a>
