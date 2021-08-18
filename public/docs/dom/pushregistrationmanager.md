# PushRegistrationManager

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Returns an interface to register or unregister a push registration, get an active registration, or check the permission status of the registration. This interface has been superseded by [`PushManager`](pushmanager).

## Methods

<span class="page-not-created">`PushRegistrationManager.register()`</span>  
Returns a promise that resolves to a <span class="page-not-created">`PushRegistration`</span> with details of a new registration.

<span class="page-not-created">`PushRegistrationManager.unregister()`</span>  
Returns a promise that resolves to a <span class="page-not-created">`PushRegistration`</span> with details of the unregistered registration.

<span class="page-not-created">`PushRegistrationManager.getRegistration()`</span>  
Returns a promise that resolves the <span class="page-not-created">`PushRegistration`</span> associated with the current webapp.

<span class="page-not-created">`PushRegistrationManager.hasPermission()`</span>  
Returns a promise that resolves to the <span class="page-not-created">`PushPermissionStatus`</span> of the requesting webapp.

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

`PushRegistrationManager`

No

No

?

No

No

No

No

No

?

No

No

No

`getRegistration`

No

No

?

No

No

No

No

No

?

No

No

No

`hasPermission`

No

No

?

No

No

No

No

No

?

No

No

No

`register`

No

No

?

No

No

No

No

No

?

No

No

No

`unregister`

No

No

?

No

No

No

No

No

?

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushRegistrationManager" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushRegistrationManager</a>
