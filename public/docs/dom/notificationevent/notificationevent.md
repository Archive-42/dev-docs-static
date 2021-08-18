NotificationEvent.NotificationEvent()
=====================================

**Draft**

This page is not complete.

The `NotificationEvent()` constructor creates a new [`NotificationEvent`](../notificationevent) object.

Syntax
------

    var myNotificationEvent = new NotificationEvent(type, NotificationEventInit);

### Parameters

`type`  
TBD

 `NotificationEventInit` <span class="badge inline optional">Optional</span>   
A dictionary object containing a [`Notification`](../notification) object to be used as the notification the event is dispatched on. In later drafts of the specification, this parameter is not optional.

Example
-------

    var n = new Notification('Hello');
    var init = { notification: n };
    var myNotificationEvent = new NotificationEvent(type, init);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-notificationevent-notificationevent">Notifications API<br />
<span class="small">The definition of 'NotificationEvent() constructor' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard.</td></tr></tbody></table>

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

`NotificationEvent`

42

≤18

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

37

?

No

42

44

37

?

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NotificationEvent/NotificationEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NotificationEvent/NotificationEvent</a>
