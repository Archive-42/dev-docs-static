&lt;time&gt;
============

The HTML `<time>` represents a specific period in time. It may include the `datetime` attribute to translate dates into machine-readable format, allowing for better search engine results or custom features such as reminders.

It may represent one of the following:

-   A time on a 24-hour clock.
-   A precise date in the [Gregorian calendar](https://en.wikipedia.org/wiki/Gregorian_calendar) (with optional time and timezone information).
-   [A valid time duration](https://www.w3.org/TR/2014/REC-html5-20141028/infrastructure.html#valid-duration-string).

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTimeElement"><code>HTMLTimeElement</code></a></td></tr></tbody></table>

Attributes
----------

Like all other HTML elements, this element supports the [global attributes](../global_attributes).

`datetime`  
This attribute indicates the time and/or date of the element and must be in one of the formats described below.

Usage notes
-----------

This element is for presenting dates and times in a machine readable format. For example, this can help a user agent offer to add an event to a user's calendar.

This element should not be used for dates prior to the introduction of the Gregorian calendar (due to complications in calculating those dates).

The datetime value (the machine-readable value of the datetime) is the value of the element’s `datetime` attribute, which must be in the proper format (see below). If the element does not have a `datetime` attribute, **it must not have any element descendants**, and the datetime value is the element’s child text content.

### Valid datetime Values

a valid year string  
`2011`

a valid month string  
`2011-11`

a valid date string  
`2011-11-18`

a valid yearless date string  
`11-18`

a valid week string  
`2011-W47`

a valid time string  
`14:54`

`14:54:39`

`14:54:39.929`

a valid local date and time string  
`2011-11-18T14:54:39.929`

`2011-11-18 14:54:39.929`

a valid global date and time string  
`2011-11-18T14:54:39.929Z`

`2011-11-18T14:54:39.929-0400`

`2011-11-18T14:54:39.929-04:00`

`2011-11-18 14:54:39.929Z`

`2011-11-18 14:54:39.929-0400`

`2011-11-18 14:54:39.929-04:00`

a valid duration string  
`PT4H18M3S`

Examples
--------

### Simple example

#### HTML

    <p>The concert starts at <time datetime="2018-07-07T20:00:00">20:00</time>.</p>

#### Output

### `datetime` example

#### HTML

    <p>The concert took place on <time
      datetime="2001-05-15T19:00">May 15</time>.</p>

#### Output

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-time-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;time&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html51/">HTML 5.1</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/textlevel-semantics.html#the-time-element">HTML 5.1<br />
<span class="small">The definition of '&lt;time&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/text-level-semantics.html#the-time-element">HTML5<br />
<span class="small">The definition of '&lt;time&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`time`

62

≤18

22

No

49

11.5-12

7

62

62

22

46

11.5-12

4

8.0

`datetime`

62

≤18

22

No

49

11.5-12

7

62

62

22

46

11.5-12

4

8.0

See also
--------

-   The [`<data>`](data) element, allowing to signal other kind of values.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/time" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/time</a>
