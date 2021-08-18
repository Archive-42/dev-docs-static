# ReportingObserver()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `ReportingObserver()` constructor of the [Reporting API](../reporting_api) creates a new [`ReportingObserver`](../reportingobserver) object instance, which can be used to collect and access reports.

## Syntax

    new ReportingObserver(callback[, options]);

### Parameters

`callback`  
A callback function that runs when the observer starts to collect reports (i.e. via [`ReportingObserver.observe()`](observe)). The callback function is given two parameters:

- `reports`: A sequence of [`Report`](../report) objects representing the reports collected in the observer's report queue. This is probably the most common way to retrieve the reports.
- `observer`: A reference to the same `ReportingObserver` object, allowing for recursive report collection, etc.

`options` <span class="badge inline optional">Optional</span>  
An [`ReportingObserverOptions`](../reportingobserveroptions) object allowing you to set the options for creating the object. The available options are:

- `types`: An array of strings representing the types of report to be collected by this observer. Available types include `deprecation`, `intervention`, and `crash` (although this last type usually isn't retrievable via a `ReportingObserver`).
- `buffered`: a boolean that defines whether the reports that were generated before the observer was able to be created should be observable (`true`) or not (`false`).

## Examples

    let options = {
      types: ['deprecation'],
      buffered: true
    }

    let observer = new ReportingObserver(function(reports, observer) {
      reportBtn.onclick = () => displayReports(reports);
    }, options);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/reporting/#dom-reportingobserver-reportingobserver">Reporting API<br />
<span class="small">The definition of 'ReportingObserver()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr></tbody></table>

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

`ReportingObserver`

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

## See also

- [Reporting API](../reporting_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReportingObserver/ReportingObserver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReportingObserver/ReportingObserver</a>
