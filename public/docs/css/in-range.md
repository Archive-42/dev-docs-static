# :in-range

The `:in-range` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element whose current value is within the range limits specified by the [`min`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-min) and [`max`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-max) attributes.

    /* Selects any <input>, but only when it has a range
       specified, and its value is inside that range */
    input:in-range {
      background-color: rgba(0, 255, 0, 0.25);
    }

This pseudo-class is useful for giving the user a visual indication that a field's current value is within the permitted limits.

**Note:** This pseudo-class only applies to elements that have (and can take) a range limitation. In the absence of such a limitation, the element can neither be "in-range" nor "out-of-range."

## Syntax

    :in-range

## Examples

### HTML

    <form action="" id="form1">
      <ul>Values between 1 and 10 are valid.
        <li>
          <input id="value1" name="value1" type="number" placeholder="1 to 10" min="1" max="10" value="12" required>
          <label for="value1">Your value is </label>
        </li>
      </ul>
    </form>

### CSS

    li {
      list-style: none;
      margin-bottom: 1em;
    }

    input {
      border: 1px solid black;
    }

    input:in-range {
      background-color: rgba(0, 255, 0, 0.25);
    }

    input:out-of-range {
      background-color: rgba(255, 0, 0, 0.25);
      border: 2px solid red;
    }

    input:in-range + label::after {
      content: 'okay.';
    }

    input:out-of-range + label::after {
      content: 'out of range!';
    }

### Result

**Note**: An empty `<input>` does not count as out of range, and will not be selected using the `:out-of-range` pseudo-class selector. The `:blank` pseudo-class exists to select blank inputs, although at the time of writing this is experimental and not well-supported. You could also use the `required` attribute and the `:invalid` pseudo-class to provide more general logic and styling for making inputs mandatory (`:invalid` will style blank _and_ out-of-range inputs).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#selector-in-range">HTML Living Standard<br />
<span class="small">The definition of ':in-range' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Defines when <code>:in-range</code> matches elements in HTML.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-4/#in-range-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':in-range' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

`:in-range`

10

Before Chrome 52, `:in-range` matched disabled and read-only inputs (see [Chromium bug 602568](https://crbug.com/602568)). In Chrome 52, it was changed to only match enabled read-write inputs.

13

29

Before Firefox 50, `:in-range` matched disabled and read-only inputs (see [bug 1264157](https://bugzil.la/1264157)). In Firefox 50, it was changed to only match enabled read-write inputs.

No

11

Before Opera 39, `:in-range` matched disabled and read-only inputs (see [Chromium bug 602568](https://crbug.com/602568)). In Opera 39, it was changed to only match enabled read-write inputs.

5.1

In Safari, `:in-range` matched disabled and read-only inputs (see [bug 156530](https://webkit.org/b/156530)). It was later changed to only match enabled read-write inputs.

2.3

Before version 52, `:in-range` matched disabled and read-only inputs (see [Chromium bug 602568](https://crbug.com/602568)). In version 52, it was changed to only match enabled read-write inputs.

18

Before Chrome 52, `:in-range` matched disabled and read-only inputs (see [Chromium bug 602568](https://crbug.com/602568)). In Chrome 52, it was changed to only match enabled read-write inputs.

16

11

Before Opera 39, `:in-range` matched disabled and read-only inputs (see [Chromium bug 602568](https://crbug.com/602568)). In Opera 39, it was changed to only match enabled read-write inputs.

5

In Safari, `:in-range` matched disabled and read-only inputs (see [bug 156530](https://webkit.org/b/156530)). It was later changed to only match enabled read-write inputs.

1.0

Before version 6.0, `:in-range` matched disabled and read-only inputs (see [Chromium bug 602568](https://crbug.com/602568)). In version 6.0, it was changed to only match enabled read-write inputs.

## See also

- [`:out-of-range`](:out-of-range)
- [Form data validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:in-range" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:in-range</a>
