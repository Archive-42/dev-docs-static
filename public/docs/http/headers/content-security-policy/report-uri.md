CSP: report-uri
===============

**Deprecated**  
This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#Browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The deprecated HTTP [`Content-Security-Policy`](../content-security-policy) (CSP) `report-uri` directive instructs the user agent to report attempts to violate the Content Security Policy. These violation reports consist of JSON documents sent via an HTTP POST request to the specified URI.

Though the [`report-to`](report-to) directive is intended to replace the deprecated `report-uri` directive, [`report-to`](report-to) isn’t supported in most browsers yet. So for compatibility with current browsers while also adding forward compatibility when browsers get [`report-to`](report-to) support, you can specify both `report-uri` and [`report-to`](report-to):

    Content-Security-Policy: ...; report-uri https://endpoint.com; report-to groupname

In browsers that support [`report-to`](report-to), the `report-uri` directive will be ignored.

The directive has no effect in and of itself, but only gains meaning in combination with other directives.

CSP version

1

Directive type

[Reporting directive](https://developer.mozilla.org/en-US/docs/Glossary/Reporting_directive)

This directive is not supported in the [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) element.

Syntax
------

    Content-Security-Policy: report-uri <uri>;
    Content-Security-Policy: report-uri <uri> <uri>;

&lt;uri&gt;  
A URI where to POST the report to.

Examples
--------

See [`Content-Security-Policy-Report-Only`](../content-security-policy-report-only) for more information and examples.

    Content-Security-Policy: default-src https:; report-uri /csp-violation-report-endpoint/

`/csp-violation-report-endpoint/` could for example run a PHP something like the following that logs the JSON detailing the violation and, if the violation is the first one added to the log file, sends an email to an administrator:

    <?php

    // Start configure
    $log_file = dirname(__FILE__) . '/csp-violations.log';
    $log_file_size_limit = 1000000; // bytes - once exceeded no further entries are added
    $email_address = 'admin@example.com';
    $email_subject = 'Content-Security-Policy violation';
    // End configuration

    $current_domain = preg_replace('/www\./i', '', $_SERVER['SERVER_NAME']);
    $email_subject = $email_subject . ' on ' . $current_domain;

    http_response_code(204); // HTTP 204 No Content

    $json_data = file_get_contents('php://input');

    // We pretty print the JSON before adding it to the log file
    if ($json_data = json_decode($json_data)) {
      $json_data = json_encode($json_data, JSON_PRETTY_PRINT | JSON_UNESCAPED_SLASHES);

      if (!file_exists($log_file)) {
        // Send an email
        $message = "The following Content-Security-Policy violation occurred on " .
          $current_domain . ":\n\n" .
          $json_data .
          "\n\nFurther CPS violations will be logged to the following log file, but no further email notifications will be sent until this log file is deleted:\n\n" .
          $log_file;
        mail($email_address, $email_subject, $message,
             'Content-Type: text/plain;charset=utf-8');
      } else if (filesize($log_file) > $log_file_size_limit) {
        exit(0);
      }

      file_put_contents($log_file, $json_data, FILE_APPEND | LOCK_EX);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-csp/#directive-report-uri">Content Security Policy Level 3<br />
<span class="small">The definition of 'report-uri' in that specification.</span></a></td><td><span class="spec-WD">Working Draft</span></td><td>No changes.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webappsec-csp/2/#directive-report-uri">Content Security Policy Level 2<br />
<span class="small">The definition of 'report-uri' in that specification.</span></a></td><td><span class="spec-REC">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`report-uri`

25

14

23

No

15

7

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`report-uri`

Yes

Yes

23

?

7

Yes

See also
--------

-   [`Content-Security-Policy`](../content-security-policy)
-   [`Content-Security-Policy-Report-Only`](../content-security-policy-report-only)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/report-uri$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/report-uri" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/report-uri</a>
