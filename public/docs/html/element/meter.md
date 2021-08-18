&lt;meter&gt;: The HTML Meter element
=====================================

The `<meter>` represents either a scalar value within a known range or a fractional value.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, labelable content, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>, but there must be no <code>&lt;meter&gt;</code> element among its descendants.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMeterElement"><code>HTMLMeterElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

`value`  
The current numeric value. This must be between the minimum and maximum values (`min` attribute and `max` attribute) if they are specified. If unspecified or malformed, the value is `0`. If specified, but not within the range given by the `min` attribute and `max` attribute, the value is equal to the nearest end of the range.

**Note:** Unless the `value` attribute is between `0` and `1` (inclusive), the `min` and `max` attributes should define the range so that the `value` attribute's value is within it.

`min`  
The lower numeric bound of the measured range. This must be less than the maximum value (`max` attribute), if specified. If unspecified, the minimum value is `0`.

`max`  
The upper numeric bound of the measured range. This must be greater than the minimum value (`min` attribute), if specified. If unspecified, the maximum value is `1`.

`low`  
The upper numeric bound of the low end of the measured range. This must be greater than the minimum value (`min` attribute), and it also must be less than the high value and maximum value (`high` attribute and `max` attribute, respectively), if any are specified. If unspecified, or if less than the minimum value, the `low` value is equal to the minimum value.

`high`  
The lower numeric bound of the high end of the measured range. This must be less than the maximum value (`max` attribute), and it also must be greater than the low value and minimum value (`low` attribute and `min` attribute, respectively), if any are specified. If unspecified, or if greater than the maximum value, the `high` value is equal to the maximum value.

`optimum`  
This attribute indicates the optimal numeric value. It must be within the range (as defined by the `min` attribute and `max` attribute). When used with the `low` attribute and `high` attribute, it gives an indication where along the range is considered preferable. For example, if it is between the `min` attribute and the `low` attribute, then the lower range is considered preferred. The browser may color the meter's bar differently depending on whether the value is less than or equal to the optimum value.

`form`  
The [`<form>`](form) element to associate the `<meter>` element with (its *form owner*). The value of this attribute must be the [`id`](../global_attributes#attr-id) of a `<form>` in the same document. If this attribute is not set, the `<meter>` is associated with its ancestor `<form>` element, if any. This attribute is only used if the `<meter>` element is being used as a form-associated element, such as one displaying a range corresponding to an [`<input type="number">`](input/number).

Examples
--------

### Simple example

#### HTML

    <p>Heat the oven to <meter min="200" max="500"
      value="350">350 degrees</meter>.</p>

#### Result

On Google Chrome, the resulting meter looks like this:

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAfgAAABKBAMAAAClc1uGAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAqUExURe/v78vLyw98EP///+rq6uPj4/n5+dXV1UmSRNnZ2Za2krnEuGyiZyeDJAJKgaMAAAGfSURBVHja7du/TsMwEAbwQwpCjJaA8G/yK7SEOUIFMVYgdhT6ABETa9+AqXsnZibEyMTcJ8KJQrCDw2gjf9+NyfSr7fPFvsoEOIR44oknnnjiiSceAl/MVirZeLqt/sI/1CrpyC/H8QuVfNyN4c8UQNz48UWNgM8rL75UELHnw0/bV++fGx0wJGBks+eWeOHBtwP/osOGhI1re+hlMPCh7aHxcmUNvYW/N09Pdep4mRvmwS+8SfUny/Tx203CH+KbPf5Np4+Xst/rxZn1SwR81s/7H/w8xoqPgW9W/b6LL8zvscbA7xhq5eCncWZ9DHz2vdn1+HOljjUGXkyd9+jgTb47RMGXXcYTq7Z9RcFvdRWuWMl+jYLf7dJ9jzfr4AMFb4q8Iwdfx0n2sfC5gzfpf4OCb/a6IV4TD4AXDx532kMnPOitDrrIgS5voT9soD9poQ8zoI+xoA8wsY+uoS8tUK6rMt91FfZFJfQVNXRzAkJbymq0LQW6IQm7FQ26CRG7/RS78Ri75Zz/tCCeeOKJJ5544oknnnjiiSee+P8fX5yWztyF8YffAAAAAElFTkSuQmCC" alt="current look of &lt;meter&gt; in google chrome" width="504" height="74" />

### High and Low range example

Note that in this example the [`min`](#attr-min) attribute is omitted. This is allowed, as it will default to `0`.

#### HTML

    <p>He got a <meter low="69" high="80" max="100"
      value="84">B</meter> on the exam.</p>

#### Result

On Google Chrome, the resulting meter looks like this:

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAfIAAABGBAMAAADFkws0AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAqUExURe/v78vLy9c6Av///+rq6uPj4/n5+dXV1d1hQNnZ2dugkd59ZNG9uNlHHbr3U/sAAAGaSURBVHja7ds9TsNAEAXgQTJClCsB5q/aKySY2kIBUUYgemRyAIuKNjegSp+KmoqaClHmRKwdO2vHNrjE896U7r7sema8O5ERagjllFNOOeWUU065Enk0WRi18XKfdMqfUqM6wusO+cyoj4dW+YUBiLsWeZQiyMOkKY8NRBw05OP8+ffHyg45pDuCyWtOvNqW50v+Zgce8mvcVhddqks+ePgfcrmpLHopf3SPzqx2uUwd86gud4n9fK5fvpul95o8q+VfVr9c4k1NF7/Z5wjyYLPdC/lUxVveQ5696YcVeeR+iSWGfM9REy8fK9nsPeRBWdfW8ktjTi2GXFwn9+zlLsEdo8jjIsVJ2bp+osh3igZWytS+RJHvF8l9LXd7/x1F7tq4Ey9PlaT2nvLQy12mX6HIs7JWk1vKtctlWw6623EzHG5Vw+1kcLtX3C8W3K9U3JMJ3NMo3BNI4FNn3JsGlNuloHG7BHyjiHuLjDs5gDAtsmifFsGdEAKeCsOdBASe/gSe+AWe8uZ/GiinnHLKKaeccsopp/xfxg8doV+rvwCEDgAAAABJRU5ErkJggg==" alt="red meter in google chrome" width="498" height="70" />

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#the-meter-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;meter&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sec-forms.html#the-meter-element">HTML5<br />
<span class="small">The definition of '&lt;meter&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`meter`

6

≤18

16

No

11

6

No

18

16

11

10.3

1.0

`form`

6

≤18

16

No

11

6

No

18

16

11

10.3

1.0

`high`

6

≤18

16

No

11

6

No

18

16

11

10.3

1.0

`low`

6

≤18

16

No

11

6

No

18

16

11

10.3

1.0

`max`

6

≤18

16

No

11

6

No

18

16

11

10.3

1.0

`min`

6

≤18

16

No

11

6

No

18

16

11

10.3

1.0

`optimum`

6

≤18

16

No

11

6

No

18

16

11

10.3

1.0

`value`

6

≤18

16

No

11

6

No

18

16

11

10.3

1.0

See also
--------

-   [`<progress>`](progress)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meter</a>
