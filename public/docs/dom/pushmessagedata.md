# PushMessageData

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `PushMessageData` interface of the [Push API](push_api) provides methods which let you retrieve the push data sent by a server in various formats.

Unlike the similar methods in the [Fetch API](fetch_api), which only allow the method to be invoked once, these methods can be called multiple times.

Messages received through the Push API are sent encrypted by push services and then automatically decrypted by browsers before they are made accessible through the methods of the `PushMessageData` interface.

## Properties

None.

## Methods

[`PushMessageData.arrayBuffer()`](pushmessagedata/arraybuffer)  
Extracts the data as an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) object.

[`PushMessageData.blob()`](pushmessagedata/blob)  
Extracts the data as a [`Blob`](blob) object.

[`PushMessageData.json()`](pushmessagedata/json)  
Extracts the data as a [JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON) object.

[`PushMessageData.text()`](pushmessagedata/text)  
Extracts the data as a plain text string.

## Examples

    self.addEventListener('push', function(event) {
      var obj = event.data.json();

      if(obj.action === 'subscribe' || obj.action === 'unsubscribe') {
        fireNotification(obj, event);
        port.postMessage(obj);
      } else if(obj.action === 'init' || obj.action === 'chatMsg') {
        port.postMessage(obj);
      }
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/#pushmessagedata-interface">Push API<br />
<span class="small">The definition of 'PushMessageData' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PushMessageData`

50

≤79

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

37

No

No

See [bug 421921](https://crbug.com/421921)

50

48

37

No

5.0

`arrayBuffer`

50

≤79

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

37

No

No

50

48

37

No

5.0

`blob`

50

≤79

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

37

No

No

50

48

37

No

5.0

`json`

50

≤79

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

37

No

No

50

48

37

No

5.0

`text`

50

≤79

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

37

No

No

50

48

37

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushMessageData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushMessageData</a>
