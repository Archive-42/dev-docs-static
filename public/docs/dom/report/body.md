# Report.body

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `body` read-only property of the [`Report`](../report) interface returns the body of the report, which is a `ReportBody` object containing the detailed report information.

## Syntax

    let reportBody = reportInstance.body

### Returns

A `ReportBody` object containing the detailed report information. Depending on what `type` the [`Report`](../report) is, the object returned will actually be a [`DeprecationReportBody`](../deprecationreportbody), [`InterventionReportBody`](../interventionreportbody), [`CrashReportBody`](../crashreportbody), or <span class="page-not-created">`FeaturePolicyViolationReportBody`</span>. These all inherit from the base `ReportBody` class — study their reference pages for more information on what the particular report body types contain.

## Examples

    let options = {
      types: ['deprecation'],
      buffered: true
    }

    let observer = new ReportingObserver(function(reports, observer) {
      let firstReport = reports[0];
      // Log the first report's report body, i.e. a DeprecationReportBody object
      console.log(firstReport.body);
    }, options);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/reporting/#dom-report-body">Reporting API<br />
<span class="small">The definition of 'Report.body' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.Report.body`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [Reporting API](../reporting_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Report/body" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Report/body</a>
