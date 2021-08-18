ReportingObserver.observe()
===========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `observe()` method of the [`ReportingObserver`](../reportingobserver) interface instructs a reporting observer to start collecting reports in its report queue.

Syntax
------

    reportingObserverInstance.observe()

Examples
--------

    let options = {
      types: ['deprecation'],
      buffered: true
    }

    let observer = new ReportingObserver(function(reports, observer) {
      reportBtn.onclick = () => displayReports(reports);
    }, options);

    observer.observe()

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/reporting/#dom-reportingobserver-observe">Reporting API<br />
<span class="small">The definition of 'ReportingObserver.observe()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr></tbody></table>

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

`observe`

69

79

No

No

56

No

69

69

No

48

No

10.0

See also
--------

-   [Reporting API](../reporting_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReportingObserver/observe" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReportingObserver/observe</a>
