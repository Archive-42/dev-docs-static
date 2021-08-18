# &lt;percentage&gt;

The `<percentage>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) represents a percentage value. It is often used to define a size as relative to an element's parent object. Numerous properties can use percentages, such as [`width`](width), [`height`](height), [`margin`](margin), [`padding`](padding), and [`font-size`](font-size).

**Note:** Only calculated values can be inherited. Thus, even if a percentage value is used on the parent property, a real value (such as a width in pixels for a [`<length>`](length) value) will be accessible on the inherited property, not the percentage value.

## Syntax

The `<percentage>` data type consists of a [`<number>`](number) followed by the percentage sign (`%`). Optionally, it may be preceded by a single `+` or `-` sign, although negative values are not valid for all properties. As with all CSS dimensions, there is no space between the symbol and the number.

## Interpolation

When animated, values of the `<percentage>` data type are interpolated as real, floating-point numbers. The speed of the interpolation is determined by the [timing function](easing-function) associated with the animation.

## Examples

### Width and margin-left

    <div style="background-color:navy;">
      <div style="width:50%; margin-left:20%; background-color:chartreuse;">
        Width: 50%, Left margin: 20%
      </div>
      <div style="width:30%; margin-left:60%; background-color:pink;">
        Width: 30%, Left margin: 60%
      </div>
    </div>

The above HTML will output:

### Font-size

    <div style="font-size:18px;">
      <p>Full-size text (18px)</p>
      <p><span style="font-size:50%;">50% (9px)</span></p>
      <p><span style="font-size:200%;">200% (36px)</span></p>
    </div>

The above HTML will output:

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-values-4/#percentages">CSS Values and Units Module Level 4<br />
<span class="small">The definition of '&lt;percentage&gt;' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>No significant change.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-values-3/#percentages">CSS Values and Units Module Level 3<br />
<span class="small">The definition of '&lt;percentage&gt;' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No significant change from CSS Level 2 (Revision 1).</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/syndata.html#percentage-units">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of '&lt;percentage&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change from CSS Level 1.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#percentage-units">CSS Level 1<br />
<span class="small">The definition of '&lt;percentage&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`percentage`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

## See also

- [`<length-percentage>`](length-percentage)
- [CSS Values and Units](css_values_and_units)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/percentage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/percentage</a>
