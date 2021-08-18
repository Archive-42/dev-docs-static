# &lt;dimension&gt;

The `<dimension>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) represents a [`<number>`](number) with a unit attached to it, for example `10px`.

CSS uses dimensions to specify distances ([`<length>`](length)), durations ([`<time>`](time)), frequencies ([`<frequency>`](frequency)), resolutions ([`<resolution>`](resolution)), and other quantities.

## Syntax

The syntax of `<dimension>` is a [`<number>`](number) immediately followed by a unit which is an identifier. Unit identifiers are case insensitive.

## Examples

### Valid dimensions

    12px      12 pixels
    1rem      1 rem
    1.2pt     1.2 points
    2200ms    2200 milliseconds
    5s        5 seconds
    200hz     200 Hertz
    200Hz     200 Hertz (values are case insensitive)

### Invalid dimensions

    12 px       The unit must come immediately after the number.
    12"px"      Units are identifiers and therefore unquoted.
    3sec        The seconds unit is abbreviated "s" not "sec".

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-values-4/#dimensions">CSS Values and Units Module Level 4<br />
<span class="small">The definition of '&lt;dimension&gt;' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Adds <code>cap</code>, <code>ic</code>, <code>lh</code>, <code>rlh</code>, <code>vi</code>, <code>vb</code></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-values-3/#dimensions">CSS Values and Units Module Level 3<br />
<span class="small">The definition of '&lt;dimension&gt;' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Adds <code>ch</code>, <code>rem</code>, <code>vw</code>, <code>vw</code>, <code>vmin</code>,<code> vmax</code>, <code>Q</code></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/syndata.html#numbers">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of '&lt;dimension&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defined under Numbers and Length</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/">CSS Level 1<br />
<span class="small">The definition of '&lt;dimension&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition under "length units"</td></tr></tbody></table>

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

`dimension`

1

12

1

5

3.5

1

≤37

18

4

10.1

1

1.0

## See also

- [CSS data types](css_types)
- [Learn to style HTML using CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS)
- CSS distances ([`<length>`](length)), durations ([`<time>`](time)), frequencies ([`<frequency>`](frequency)), and resolutions ([`<resolution>`](resolution))

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/dimension" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/dimension</a>
