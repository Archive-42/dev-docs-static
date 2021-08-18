TouchEvent.metaKey
==================

Summary
-------

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating whether or not the Meta key is enabled when the touch event is created. If this key is enabled, the attribute's value is `true`. Otherwise, it is `false`.

This property is <span class="badge inline readonly">Read only </span>.

**Note:** On Macintosh keyboards, this is the ⌘ Command key. On Windows keyboards, this is the Windows key (⊞).

Syntax
------

    var metaEnabled = touchEvent.metaKey;

### Return value

`metaEnabled`  
`true` if the Meta key is enabled for this event; and `false` if the Meta is not enabled.

Example
-------

The [TouchEvent.altKey example](altkey#example) includes an example of this property's usage.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#dom-touchevent-metakey">Touch Events – Level 2</a></td><td><span class="spec-draft">Draft</span></td><td>Non-stable version.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/touch-events/#widl-TouchEvent-metaKey">Touch Events</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`metaKey`

22

≤18

52

18-24

No

Yes

No

≤37

Yes

6

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TouchEvent/metaKey" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TouchEvent/metaKey</a>
