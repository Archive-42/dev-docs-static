PushEvent.data
==============

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `data` read-only property of the `PushEvent` interface returns a reference to a [`PushMessageData`](../pushmessagedata) object containing data sent to the [`PushSubscription`](../pushsubscription).

Syntax
------

    var myPushData = PushEvent.data;

### Value

A [`PushMessageData`](../pushmessagedata) object.

**Examples**

The following example takes data from a PushEvent and displays it on all of the service workers' clients.

    self.addEventListener('push', function(event) {
      if (!(self.Notification && self.Notification.permission === 'granted')) {
        return;
      }

      var data = {};
      if (event.data) {
        data = event.data.json();
      }
      var title = data.title || "Something Has Happened";
      var message = data.message || "Here's something you might want to check out.";
      var icon = "images/new-notification.png";

      var notification = new Notification(title, {
        body: message,
        tag: 'simple-push-demo-notification',
        icon: icon
      });

      notification.addEventListener('click', function() {
        if (clients.openWindow) {
          clients.openWindow('https://example.blog.com/2015/03/04/something-new.html');
        }
      });
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/#dom-pushevent-data">Push API<br />
<span class="small">The definition of 'data' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`data`

57

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

44

No

No

57

44

48

Push enabled by default.

43

No

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushEvent/data" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushEvent/data</a>
