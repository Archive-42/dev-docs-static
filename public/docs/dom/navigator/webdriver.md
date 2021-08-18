Navigator.webdriver
===================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `webdriver` read-only property of the [`navigator`](../navigator) interface indicates whether the user agent is controlled by automation.

It defines a standard way for co-operating user agents to inform the document that it is controlled by [WebDriver](https://developer.mozilla.org/en-US/docs/Web/WebDriver), for example, so that alternate code paths can be triggered during automation.

The `navigator.``webdriver` property is true when in:

Chrome  
The `--enable-automation` or the `--headless` flag or the `--remote-debugging-port` is used.

Firefox  
The `marionette.enabled` preference or `--marionette` flag is passed.

Syntax
------

    var isAutomated = navigator.webdriver

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webdriver/#dom-navigatorautomationinformation-webdriver">WebDriver<br />
<span class="small">The definition of 'webdriver' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`webdriver`

63

12

60

11

50

10

No

63

60

46

10

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/webdriver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/webdriver</a>
