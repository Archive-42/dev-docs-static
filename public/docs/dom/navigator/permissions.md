# Navigator.permissions

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Navigator.permissions` read-only property returns a [`Permissions`](../permissions) object that can be used to query and update permission status of APIs covered by the [Permissions API](../permissions_api).

## Syntax

    permissionsObj = globalObj.navigator.permissions

## Value

A [`Permissions`](../permissions) object.

## Examples

    navigator.permissions.query({name:'geolocation'}).then(function(result) {
      if (result.state === 'granted') {
        showMap();
      } else if (result.state === 'prompt') {
        showButtonToEnableMap();
      }
      // Don't do anything if the permission was denied.
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/permissions/">Permissions</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`permissions`

43

79

46

No

Yes

No

No

See [bug 490120](https://crbug.com/490120)

43

46

Yes

No

4.0

## See also

- [Permissions API](../permissions_api)
- [`Navigator`](../navigator)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/permissions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/permissions</a>
