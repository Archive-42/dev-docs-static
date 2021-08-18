&lt;progress&gt;: The Progress Indicator element
================================================

The `<progress>` displays an indicator showing the completion progress of a task, typically displayed as a progress bar.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, labelable content, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>, but there must be no <code>&lt;progress&gt;</code> element among its descendants.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>progressbar</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLProgressElement"><code>HTMLProgressElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

`max`  
This attribute describes how much work the task indicated by the `progress` element requires. The `max` attribute, if present, must have a value greater than `0` and be a valid floating point number. The default value is `1`.

`value`  
This attribute specifies how much of the task that has been completed. It must be a valid floating point number between `0` and `max`, or between `0` and `1` if `max` is omitted. If there is no `value` attribute, the progress bar is indeterminate; this indicates that an activity is ongoing with no indication of how long it is expected to take.

**Note:** Unlike the [`<meter>`](meter) element, the minimum value is always 0, and the `min` attribute is not allowed for the `<progress>` element.

**Note:** The [`:indeterminate`](https://developer.mozilla.org/en-US/docs/Web/CSS/:indeterminate) pseudo-class can be used to match against indeterminate progress bars. To change the progress bar to indeterminate after giving it a value you must remove the value attribute with [`element.removeAttribute('value')`](https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttribute).

Examples
--------

    <progress value="70" max="100">70 %</progress>

### Result

On Windows 7, the resulting progress looks like this:

<img src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAgGBgcGBQgHBwcJCQgKDBQNDAsLDBkSEw8UHRofHh0aHBwgJC4nICIsIxwcKDcpLDAxNDQ0Hyc5PTgyPC4zNDL/2wBDAQkJCQwLDBgNDRgyIRwhMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjL/wgARCAAZAKkDASIAAhEBAxEB/8QAGgAAAgMBAQAAAAAAAAAAAAAAAAUBAgYDBP/EABgBAQEBAQEAAAAAAAAAAAAAAAABAgME/9oADAMBAAIQAxAAAAHb18C7j5tDCXtjm0F0qwlZQbCWjL4z8JoTN0t1EpvT29bIWmtspWQM+i5iKV+mOfHPdXhnKWXAqWj4TPV0YmaNKJmqagVJ3aHXutGRdLatA8HvA//EAB8QAAICAwEAAwEAAAAAAAAAAAACARMDEhQEERUiQP/aAAgBAQABBQJn+JsYsYsYsYsYsYsYsYsYsY3Y3YsYh2NmN2N2N2LHFf8AR68lbR7ZI9RGctLS46DqOs7JO2Tuk75MGaXTeTeTeTeTeTzt85j04GyzwsR5HI87lLlLlLnO5yscbHExxMfXufXMY8DYl0Yqcqcqcrcw42XJ/P8A/8QAHREAAQQDAQEAAAAAAAAAAAAAAAECAxQRIFESE//aAAgBAwEBPwGSdGOwpaQsFpC40vMLjRjvTc6PgY9cqVo+Hwj4VoypFwpw8KkPBGo1MJp//8QAHBEAAgIDAQEAAAAAAAAAAAAAABMBAgMRICES/9oACAECAQE/AbZPmRw4cPgfA+Cs7jfE4629kVQTUVQRQRQTQiNecf/EACcQAAEDBAEDAwUAAAAAAAAAAAACMqEBMZHRERAzkhIhYSBAcYHB/9oACAEBAAY/AuKUG0yNpkbTI2mRtMjaZG0yNpkbTI2mRqcjaZLUyNT5DU+QxPkMT5DE+Q1PkcVpx+K9Ofin9GyNksWLFiw2RsjZGyMkZJz9X6r09qV4+Cyo2NVGxio2MVGxio2MVGxqo2NVGxqo2WVGyyo2WVGyyo2en0KrjZ21QdpUbO0qNnaVGztqg5rTj2+4/8QAJhAAAgEDAwMEAwAAAAAAAAAAAAHREfDxITFREMHhIEBBgWFxkf/aAAgBAQABPyF9ON7uroWODJ4MzgyWC6wZPBm8FjgtcGTwZrBmcGj38DWzPtBfoLlBcoLlBdYHOjNSq1L36aPVfyBi/sNYNfmV5FeQ3XkNl5jZA3VnYu+I7OB3MD51/wBDXTTXatfSAOiMVV3LprEMktmlK8tciTGSWz/okOrUGMubjq8JPwpYcsWVSMsKXzViv5mVLKllSb1p/eZU3WtatfNOG+Pcf//aAAwDAQACAAMAAAAQwd5oMf5RAUU1huxqsCx88c//xAAdEQEBAAIBBQAAAAAAAAAAAAABABExIBBBUWHw/9oACAEDAQE/EMoobTY+ZDbI7b2Q+mxXDgjB9EU7Ss+KwVIcL//EABoRAAMAAwEAAAAAAAAAAAAAAAABYRARIFH/2gAIAQIBAT8Q3iJeFvBYTDTeuHGgkRIESZMSqTj/xAAmEAEAAQIFAwUBAQAAAAAAAAABABFBECExYfFRofAgMHHB0ZGx/9oACAEBAAE/EKDACo0CoWejOWSHiwrp5VjinOWTyT0TkT4hRO5yINHIlpof2SAfdkA+7IB92ebSESG2ZBBsU0YI2htMl4UpVCl54DrUedoMa/HxHwPyXL4+Jf752l+xdskrodVgG7AlamdlXQJunebp3m6d5uneGyJ3mXUW/nCE6iRSsyDDwzvZyhyGpCj+suUkiBbeDNlUatOrxqmhJupAuNStckcv6FYsWVWk2hWBNA1VPLQH+8T3DWX9j//Z" alt="progress-firefox.JPG" class="default internal" width="169" height="25" />

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#the-progress-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;progress&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sec-forms.html#the-progress-element">HTML5<br />
<span class="small">The definition of '&lt;progress&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`progress`

6

12

6

\["Prior to Firefox 14, the `<progress>` element was incorrectly classified as a form element, and therefore had a `form` attribute. This has been fixed.", "Firefox provides the `::-moz-progress-bar` pseudo-element, which lets you style the part of the interior of the progress bar representing the amount of work completed so far."\]

10

11

6

Yes

Yes

6

\["Prior to Firefox 14, the `<progress>` element was incorrectly classified as a form element, and therefore had a `form` attribute. This has been fixed.", "Firefox provides the `::-moz-progress-bar` pseudo-element, which lets you style the part of the interior of the progress bar representing the amount of work completed so far."\]

11

7

Safari on iOS does not support indeterminate progress bars (they are rendered like 0%-completed progress bars).

Yes

`max`

6

12

6

10

11

6

Yes

Yes

6

11

7

Yes

`value`

6

12

6

10

11

6

Yes

Yes

6

11

7

Yes

See also
--------

-   [`<meter>`](meter)
-   [`:indeterminate`](https://developer.mozilla.org/en-US/docs/Web/CSS/:indeterminate)
-   [`-moz-orient`](https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-orient)
-   [`::-moz-progress-bar`](https://developer.mozilla.org/en-US/docs/Web/CSS/::-moz-progress-bar)
-   <span class="page-not-created">`::-ms-fill`</span>
-   [`::-webkit-progress-bar`](https://developer.mozilla.org/en-US/docs/Web/CSS/::-webkit-progress-bar)
-   [`::-webkit-progress-value`](https://developer.mozilla.org/en-US/docs/Web/CSS/::-webkit-progress-value)
-   [`::-webkit-progress-inner-element`](https://developer.mozilla.org/en-US/docs/Web/CSS/::-webkit-progress-inner-element)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/progress" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/progress</a>
