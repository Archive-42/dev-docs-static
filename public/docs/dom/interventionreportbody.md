InterventionReportBody
======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `InterventionReportBody` interface of the [Reporting API](reporting_api) represents the body of an intervention report (the return value of its [`Report.body`](report/body) property).

An intervention report is generated when usage of a feature in a web document has been blocked by the browser for reasons such as security, performance, or user annoyance. So for example, a script was been stopped because it was significantly slowing down the browser, or the browser's autoplay policy blocked audio from playing without a user gesture to trigger it.

Properties
----------

`id`  
A string representing the intervention that generated the report. This can be used to group reports by deprecated feature.

`message`  
A string containing a human-readable description of the intervention, including information such how the intervention could be avoided. This typically matches the message a browser will display in its DevTools console when an intervention is imposed, if one is available.

`sourceFile`  
A string containing the path to the source file where the intervention occurred, if known, or `null` otherwise.

`lineNumber`  
A number representing the line in the source file in which the intervention occurred, if known, or `null` otherwise.

`columnNumber`  
A number representing the column in the source file in which the intervention occurred, if known, or `null` otherwise.

Examples
--------

    let options = {
      types: ['intervention'],
      buffered: true
    }

    let observer = new ReportingObserver(function(reports, observer) {
      let firstReport = reports[0];
      console.log(firstReport.type); // intervention
      console.log(firstReport.body.id);
      console.log(firstReport.body.message);
      console.log(firstReport.body.sourceFile);
      console.log(firstReport.body.lineNumber);
      console.log(firstReport.body.columnNumber);
    }, options);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/reporting/#intervention-report">Reporting API<br />
<span class="small">The definition of 'InterventionReportBody' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.DeprecationReportBody`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [Reporting API](reporting_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/InterventionReportBody" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/InterventionReportBody</a>
