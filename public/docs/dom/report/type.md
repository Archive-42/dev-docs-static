Report.type
===========

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `type` read-only property of the [`Report`](../report) interface returns the type of report generated, e.g. `deprecation` or `intervention`.

Syntax
------

    let reportType = reportInstance.type

### Returns

A string representing the type of the report. Currently the available types are `deprecation`, `intervention`, and `crash`.

Examples
--------

    let options = {
      types: ['deprecation'],
      buffered: true
    }

    let observer = new ReportingObserver(function(reports, observer) {
      let firstReport = reports[0];
      // Log the first report's report type, i.e. "deprecation"
      console.log(firstReport.type);
    }, options);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/reporting/#dom-report-body">Reporting API<br />
<span class="small">The definition of 'Report.body' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.Report.body`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [Reporting API](../reporting_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Report/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Report/type</a>
