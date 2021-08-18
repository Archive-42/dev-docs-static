PermissionStatus
================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `PermissionStatus` interface of the [Permissions API](permissions_api) provides the state of an object and an event handler for monitoring changes to said state.

Properties
----------

 [`PermissionStatus.state`](permissionstatus/state) <span class="badge inline readonly">Read only </span>   
Returns the state of a requested permission; one of `'granted'`, `'denied'`, or `'prompt'`.

 `PermissionStatus.status`<span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns the state of a requested permission; one of `'granted'`, `'denied'`, or `'prompt'`. Later versions of the specification replace this with [`PermissionStatus.state`](permissionstatus/state).

### Event Handler

[`PermissionStatus.onchange`](permissionstatus/onchange)  
An event called whenever `PermissionStatus.status` changes.

Example
-------

    navigator.permissions.query({name:'geolocation'}).then(function(permissionStatus) {
      console.log('geolocation permission status is ', permissionStatus.state);
      permissionStatus.onchange = function() {
        console.log('geolocation permission status has changed to ', this.state);
      };
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/permissions/#status-of-a-permission">Permissions<br />
<span class="small">The definition of 'PermissionStatus' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PermissionStatus`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PermissionStatus" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PermissionStatus</a>
