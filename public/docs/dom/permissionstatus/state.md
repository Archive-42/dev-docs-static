# PermissionStatus.state

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `state` read-only property of the [`PermissionStatus`](../permissionstatus) interface returns the state of a requested permission. This property returns one of `'granted'`, `'denied'`, or `'prompt'`.

## Syntax

    var permission = PermissionStatus.state;

## Example

    navigator.permissions.query({name:'geolocation'}).then(function(permissionStatus) {
      console.log('geolocation permission state is ', permissionStatus.state);
      permissionStatus.onchange = function() {
        console.log('geolocation permission status has changed to ', this.state);
      };
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/permissions/#dom-permissionstatus-state">Permissions<br />
<span class="small">The definition of 'state' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`state`

44

43-44

79

46

No

Yes

No

No

44

43-44

46

Yes

No

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PermissionStatus/state" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PermissionStatus/state</a>
