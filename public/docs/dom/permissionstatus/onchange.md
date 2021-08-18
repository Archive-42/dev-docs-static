PermissionStatus.onchange
=========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `onchange` event handler of the [`PermissionStatus`](../permissionstatus) interface is called whenever the [`PermissionStatus.state`](state) property changes.

Syntax
------

    PermissionStatus.onchange = function() { ... }
    PermissionStatus.addEventListener('change', function() { ... })

Example
-------

    navigator.permissions.query({name:'geolocation'}).then(function(permissionStatus) {
      console.log('geolocation permission state is ', permissionStatus.state);
      permissionStatus.onchange = function() {
        console.log('geolocation permission state has changed to ', this.state);
      };
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/permissions/#dom-permissionstatus-onchange">Permissions<br />
<span class="small">The definition of 'onchange' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onchange`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PermissionStatus/onchange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PermissionStatus/onchange</a>
