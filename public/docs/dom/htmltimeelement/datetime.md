HTMLTimeElement.dateTime
========================

The `HTMLTimeElement``.dateTime` property is a [`DOMString`](../domstring) that reflects the [`datetime`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/time#attr-datetime) HTML attribute, containing a machine-readable form of the element's date and time value.

The format of the string must follow one of the following HTML microsyntaxes:

<table><thead><tr class="header"><th>Microsyntax</th><th>Description</th><th>Examples</th></tr></thead><tbody><tr class="odd"><td>Valid month string</td><td><em>YYYY</em><code>-</code><em>MM</em></td><td><code>2011-11</code>, <code>2013-05</code></td></tr><tr class="even"><td>Valid date string</td><td><em>YYYY</em><code>-</code><em>MM</em><code>-</code><em>DD</em></td><td><code>1887-12-01</code></td></tr><tr class="odd"><td>Valid yearless date string</td><td><em>MM</em><code>-</code><em>DD</em></td><td><code>11-12</code></td></tr><tr class="even"><td>Valid time string</td><td><em>HH</em><code>:</code><em>MM</em><br />
<em>HH</em><code>:</code><em>MM</em><code>:</code><em>SS</em><br />
<em>HH</em><code>:</code><em>MM</em><code>:</code><em>SS</em><code>.</code><em>mmm</em></td><td><code>23:59</code><br />
<code>12:15:47</code><br />
<code>12:15:52.998</code></td></tr><tr class="odd"><td>Valid local date and time string</td><td><em>YYYY</em><code>-</code><em>MM</em><code>-</code><em>DD</em> <em>HH</em><code>:</code><em>MM</em><br />
<em>YYYY</em><code>-</code><em>MM</em><code>-</code><em>DD</em> <em>HH</em><code>:</code><em>MM</em><code>:</code><em>SS</em><br />
<em>YYYY</em><code>-</code><em>MM</em><code>-</code><em>DD</em> <em>HH</em><code>:</code><em>MM</em><code>:</code><em>SS</em><code>.</code><em>mmm</em><br />
<em>YYYY</em><code>-</code><em>MM</em><code>-</code><em>DD</em><code>T</code><em>HH</em><code>:</code><em>MM</em><br />
<em>YYYY</em><code>-</code><em>MM</em><code>-</code><em>DD</em><code>T</code><em>HH</em><code>:</code><em>MM</em><code>:</code><em>SS</em><br />
<em>YYYY</em><code>-</code><em>MM</em><code>-</code><em>DD</em><code>T</code><em>HH</em><code>:</code><em>MM</em><code>:</code><em>SS</em><code>.</code><em>mmm</em></td><td><code>2013-12-25 11:12     1972-07-25 13:43:07     1941-03-15 07:06:23.678     2013-12-25T11:12     1972-07-25T13:43:07     1941-03-15T07:06:23.678</code></td></tr><tr class="even"><td>Valid time-zone offset string</td><td><code>Z</code><br />
<code>+</code><em>HHMM</em><br />
<code>+</code><em>HH</em><code>:</code><em>MM</em><br />
<code>-</code><em>HHMM</em><br />
<code>-</code><em>HH</em><code>:</code><em>MM</em></td><td><code>Z     +0200     +04:30     -0300     -08:00</code></td></tr><tr class="odd"><td>Valid global date and time string</td><td><em>Any combination of a valid local date and time string followed by a valid time-zone offset string</em></td><td><code>2013-12-25 11:12+0200     1972-07-25 13:43:07+04:30     1941-03-15 07:06:23.678Z     2013-12-25T11:12-08:00</code></td></tr><tr class="even"><td>Valid week string</td><td><em>YYYY</em><code>-W</code><em>WW</em></td><td><code>2013-W46</code></td></tr><tr class="odd"><td>Four or more ASCII digits</td><td><em>YYYY</em></td><td><code>2013</code>, <code>0001</code></td></tr><tr class="even"><td>Valid duration string</td><td><code>P</code><em>d</em><code>D</code><code>T</code><em>h</em><code>H</code><em>m</em><code>M</code><em>s</em><code>S</code><br />
<code>P</code><em>d</em><code>D</code><code>T</code><em>h</em><code>H</code><em>m</em><code>M</code><em>s</em><code>.</code>X<code>S</code><br />
<code>P</code><em>d</em><code>D</code><code>T</code><em>h</em><code>H</code><em>m</em><code>M</code><em>s</em><code>.</code>XX<code>S</code><br />
<code>P</code><em>d</em><code>D</code><code>T</code><em>h</em><code>H</code><em>m</em><code>M</code><em>s</em><code>.</code>XXX<code>S</code><br />
<code>P</code><code>T</code><em>h</em><code>H</code><em>m</em><code>M</code><em>s</em><code>S</code><br />
<code>P</code><code>T</code><em>h</em><code>H</code><em>m</em><code>M</code><em>s</em><code>.</code>X<code>S</code><br />
<code>P</code><code>T</code><em>h</em><code>H</code><em>m</em><code>M</code><em>s</em><code>.</code>XX<code>S</code><br />
<code>P</code><code>T</code><em>h</em><code>H</code><em>m</em><code>M</code><em>s</em><code>.</code>XXX<code>S</code><br />
<em>w</em><code>w </code><em>d</em><code>d </code><em>h</em><code>h </code><em>m</em><code>m </code><em>s</em><code>s</code></td><td><code>P12DT7H12M13S     P12DT7H12M13.3S     P12DT7H12M13.45S     P12DT7H12M13.455S     PT7H12M13S     PT7H12M13.2S     PT7H12M13.56S     PT7H12M13.999S     7d 5h 24m 13s</code></td></tr></tbody></table>

Syntax
------

    dateTimeString = timeElt.dateTime;
    timeElt.dateTime = dateTimeString

Example
-------

    // Assumes there is <time id="t"> element in the HTML

    var t = document.getElementById("t");
    t.dateTime = "6w 5h 34m 5s";

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/text-level-semantics.html#dom-time-datetime">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTimeElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html51/">HTML 5.1</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/text-level-semantics.html#dom-time-datetime">HTML 5.1<br />
<span class="small">The definition of 'HTMLTimeElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/text-level-semantics.html#dom-time-datetime">HTML5<br />
<span class="small">The definition of 'HTMLTimeElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`dateTime`

62

14

22

No

49

11.5-15

10

62

62

22

46

11.5-14

10

8.0

See also
--------

-   The [`HTMLTimeElement`](../htmltimeelement) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTimeElement/dateTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTimeElement/dateTime</a>
