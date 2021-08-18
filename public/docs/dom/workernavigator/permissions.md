WorkerNavigator.permissions
===========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `WorkerNavigator.permissions` read-only property returns a [`Permissions`](../permissions) object that can be used to query and update permission status of APIs covered by the [Permissions API](../permissions_api).

Syntax
------

    permissionsObj = self.permissions

Value
-----

A [`Permissions`](../permissions) object.

Examples
--------

    self.navigator.permissions.query({name:'notifications'}).then(function(result) {
      if (result.state === 'granted') {
        showNotification();
      } else if (result.state === 'prompt') {
        requestNotificationPermission()
      }
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/permissions/">Permissions</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser Support
---------------

BCD tables only load in the browser

See also
--------

-   [Permissions API](../permissions_api)
-   [Web Worker API](../web_workers_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator/permissions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator/permissions</a>
