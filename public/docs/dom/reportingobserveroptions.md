ReportingObserverOptions
========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `ReportingObserverOptions` dictionary of the [Reporting API](reporting_api) allows options to be set in the constructor when creating a [`ReportingObserver`](reportingobserver).

Properties
----------

`types`  
An array of strings representing the types of report to be collected by this observer. Available types include `deprecation`, `intervention`, and `crash`.

`buffered`  
A boolean that defines whether the reports that were generated before the observer was able to be created should be observable (`true`) or not (`false`).

Examples
--------

    let options = {
      types: ['deprecation'],
      buffered: true
    }

    let observer = new ReportingObserver(function(reports, observer) {
      reportBtn.onclick = () => displayReports(reports);
    }, options);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/reporting/#dictdef-reportingobserveroptions">Reporting API<br />
<span class="small">The definition of 'ReportingObserverOptions' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.ReportingObserverOptions`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [Reporting API](reporting_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReportingObserverOptions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReportingObserverOptions</a>
