# ExtendableMessageEvent.data

The `data` read-only property of the [`ExtendableMessageEvent`](../extendablemessageevent) interface returns the event's data. It can be any data type.

## Syntax

    var myData = extendableMessageEvent.data;

### Value

Any data type.

## Examples

When the following code is used inside a service worker to respond to a push messages by sending the data received via [`PushMessageData`](../pushmessagedata) to the main context via a [channel message](../channel_messaging_api), the event object of `onmessage` will be a `ExtendableMessageEvent`.

    var port;

    self.addEventListener('push', function(e) {
      var obj = e.data.json();

      if(obj.action === 'subscribe' || obj.action === 'unsubscribe') {
        port.postMessage(obj);
      } else if(obj.action === 'init' || obj.action === 'chatMsg') {
        port.postMessage(obj);
      }
    });

    self.onmessage = function(e) {
      console.log(e.data);
      port = e.ports[0];
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-extendablemessageevent-data">Service Workers<br />
<span class="small">The definition of 'ExtendableMessageEvent.data' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`data`

51

17

45

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

?

No

No

51

45

?

No

5.0

## See also

- [Using Service Workers](../service_worker_api/using_service_workers)
- [Service workers basic code example](https://github.com/mdn/sw-test)
- [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
- [Channel Messaging](../channel_messaging_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ExtendableMessageEvent/data" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ExtendableMessageEvent/data</a>
