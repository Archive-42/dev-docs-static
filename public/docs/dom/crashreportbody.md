# CrashReportBody

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CrashReportBody` interface of the [Reporting API](reporting_api) represents the body of a crash report (the return value of its [`Report.body`](report/body) property).

A crash report is generated when a document becomes unusable due to the browser (or one of its processes) crashing. For security reasons, no details of the crash are communicated in the body except for a general crash reason.

## Properties

`reason`  
A string representing the reason for the crash. Current possible reasons are:

- `oom`: The browser ran out of memory.
- `unresponsive`: The page was killed due to being unresponsive.

## Examples

Crash reports are generally only retrievable via endpoints set up using the [`Report-To`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Report-To) header. It is difficult to retrieve a crash report via a [`ReportingObserver`](reportingobserver), as by that point the page would have crashed!

Some sample JSON might look like this:

    {
      "type": "crash",
      "age": 42,
      "url": "https://example.com/",
      "user_agent": "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0",
      "body": {
        "reason": "oom"
      }
    }

**Note**: Crash reports are always delivered to the endpoint group named `default`; there is currently no way to override this. If you want to receive other kinds of reports, but not crash reports, make sure to use a different name for the endpoint group that you choose for those reports.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/reporting/#crash-report">Reporting API<br />
<span class="small">The definition of 'CrashReportBody' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.CrashReportBody`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [Reporting API](reporting_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CrashReportBody" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CrashReportBody</a>
