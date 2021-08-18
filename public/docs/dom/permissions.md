# Permissions

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The Permissions interface of the [Permissions API](permissions_api) provides the core Permission API functionality, such as methods for querying and revoking permissions

## Methods

[`Permissions.query()`](permissions/query)  
Returns the user permission status for a given API.

<span class="page-not-created">`Permissions.request()`</span>  
Requests permission to use a given API. This is not currently supported in any browser.

<span class="page-not-created">`Permissions.requestAll()`</span>  
Requests permission to use a given set of APIs. This is not currently supported in any browser.

[`Permissions.revoke()`](permissions/revoke)  
Revokes the permission currently set on a given API.

## Example

    navigator.permissions.query({name:'geolocation'}).then(function(result) {
      if (result.state === 'granted') {
        showLocalNewsWithGeolocation();
      } else if (result.state === 'prompt') {
        showButtonToEnableLocalNews();
      }
      // Don't do anything if the permission was denied.
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/permissions/#permissions-interface">Permissions<br />
<span class="small">The definition of 'Permissions' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser Support

BCD tables only load in the browser

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Permissions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Permissions</a>
