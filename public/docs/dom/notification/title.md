Notification.title
==================

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `title` read-only property of the [`Notification`](../notification) interface indicates the title of the notification, as specified in the `title` parameter of the [`Notification()`](notification) constructor.

Syntax
------

    var title = Notification.title;

### Value

A [`DOMString`](../domstring).

Examples
--------

    function spawnNotification(theBody,theIcon,theTitle) {
      var options = {
          body: theBody,
          icon: theIcon
      }

      var n = new Notification(theTitle,options);

      console.log(n.title)
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-notification-title">Notifications API<br />
<span class="small">The definition of 'title' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard</td></tr></tbody></table>

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

`title`

Yes

14

26

No

Yes

11

No

Yes

26

Yes

No

Yes

See also
--------

-   [Using the Notifications API](../notifications_api/using_the_notifications_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Notification/title" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Notification/title</a>
