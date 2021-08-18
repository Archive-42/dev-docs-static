# &lt;frequency&gt;

The `<frequency>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) represents a frequency dimension, such as the pitch of a speaking voice. It is not currently used in any CSS properties.

## Syntax

The `<frequency>` data type consists of a [`<number>`](number) followed by one of the units listed below. As with all CSS dimensions, there is no space between the unit literal and the number.

### Units

`Hz`  
Represents a frequency in hertz. Examples: `0Hz`, `1500Hz`, `10000Hz`.

`kHz`  
Represents a frequency in kilohertz. Examples: `0kHz`, `1.5kHz`, `10kHz`.

**Note:** Although the number `0` is always the same regardless of unit, the unit may not be omitted. In other words, `0` is invalid and does not represent `0Hz` or `0kHz`. Though the units are case-insensitive, it is good practice to use a capital "H" for `Hz` and `kHz`, as specified in the [SI](https://en.wikipedia.org/wiki/International_System_of_Units).

## Examples

### Valid frequency values

    12Hz     Positive integer
    4.3Hz    Non-integer
    14KhZ    The unit is case-insensitive, though non-SI capitalization is not recommended.
    +0Hz     Zero, with a leading + and a unit
    -0kHz    Zero, with a leading - and a unit

### Invalid frequency values

    12.0     This is a <number>, not an <frequency>, because it is missing a unit.
    7 Hz     No space is allowed between the number and the unit.
    0        Although unitless zero is an allowable <length>, it's an invalid <frequency>.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-values-3/#frequency">CSS Values and Units Module Level 3<br />
<span class="small">The definition of '&lt;frequency&gt;' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

**Note:** This data type was initially introduced in [CSS Level 2](https://www.w3.org/TR/CSS2/aural.html#q19.0) for the now-obsolete [aural](@media/aural) [media type](@media#media_types), where it was used to define the pitch of the voice. However, the `<frequency>` data type has been reintroduced in CSS3, though no CSS property is using it at the moment.

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

`frequency`

No

No

No

See [bug 741643](https://bugzil.la/741643).

No

No

No

No

No

No

No

No

No

`hz`

No

No

No

No

No

No

No

No

No

No

No

No

`khz`

No

No

No

No

No

No

No

No

No

No

No

No

## See also

- [`<frequency-percentage>`](frequency-percentage)
- [CSS Values and Units](css_values_and_units)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/frequency" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/frequency</a>
