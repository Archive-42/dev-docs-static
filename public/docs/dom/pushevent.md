PushEvent
=========

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `PushEvent` interface of the [Push API](push_api) represents a push message that has been received. This event is sent to the [global scope](serviceworkerglobalscope) of a [`ServiceWorker`](serviceworker). It contains the information sent from an application server to a [`PushSubscription`](pushsubscription).

Constructor
-----------

[`PushEvent.PushEvent()`](pushevent/pushevent)  
Creates a new `PushEvent` object.

Properties
----------

*Inherits properties from its parent, [`ExtendableEvent`](extendableevent). Additional properties:*

 [`PushEvent.data`](pushevent/data) <span class="badge inline readonly">Read only </span>   
Returns a reference to a [`PushMessageData`](pushmessagedata) object containing data sent to the [`PushSubscription`](pushsubscription).

**Methods**

*Inherits methods from its parent, [`ExtendableEvent`](extendableevent)*.

Examples
--------

The following example takes data from a `PushEvent` and displays it on all of the service worker's clients.

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

      var notification = new self.Notification(title, {
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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/#pushevent-interface">Push API<br />
<span class="small">The definition of 'PushEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PushEvent`

42

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

37

No

No

See [bug 421921](https://crbug.com/421921)

42

44

48

Push enabled by default.

37

No

4.0

`PushEvent`

42

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

37

No

No

42

44

48

Push enabled by default.

37

No

4.0

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

See also
--------

-   [Push API](push_api)
-   [Service Worker API](service_worker_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushEvent</a>
