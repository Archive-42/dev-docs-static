SyncEvent.lastChance
====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `SyncEvent.lastChance` read-only property of the [`SyncEvent`](../syncevent) interface returns `true` if the user agent will not make further synchronization attempts after the current attempt. This is the value passed in the `lastChance` parameter of the [`SyncEvent()`](syncevent) constructor.

Syntax
------

    var lastChance = SyncEvent.lastChance

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether the user agent will not make further synchronization attempts after the current attempt.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-sync/spec/#sync-event">Web Background Synchronization</a></td></tr></tbody></table>

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

`lastChance`

49

≤79

?

No

?

?

No

49

?

?

?

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SyncEvent/lastChance" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SyncEvent/lastChance</a>
