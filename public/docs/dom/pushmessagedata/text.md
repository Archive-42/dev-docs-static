PushMessageData.text()
======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `text()`method of the [`PushMessageData`](../pushmessagedata) interface extracts push message data as a plain text string.

Syntax
------

    var myText = pushEvent.data.text();

### Parameters

None.

### Returns

A [`USVString`](../usvstring).

Examples
--------

    self.addEventListener('push', function(event) {
      var textObj = event.data.text();

      // do something with your text
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/#dom-pushmessagedata-text">Push API<br />
<span class="small">The definition of 'text()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushMessageData/text" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushMessageData/text</a>
