# :out-of-range

The `:out-of-range` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element whose current value is outside the range limits specified by the [`min`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-min) and [`max`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-max) attributes.

    /* Selects any <input>, but only when it has a range
       specified, and its value is outside that range */
    input:out-of-range {
      background-color: rgba(255, 0, 0, 0.25);
    }

This pseudo-class is useful for giving the user a visual indication that a field's current value is outside the permitted limits.

**Note:** This pseudo-class only applies to elements that have (and can take) a range limitation. In the absence of such a limitation, the element can neither be "in-range" nor "out-of-range."

## Syntax

    :out-of-range

## Examples

### HTML

    <form action="" id="form1">
     <p>Values between 1 and 10 are valid.</p>
      <ul>
        <li>
          <input id="value1" name="value1" type="number" placeholder="1 to 10" min="1" max="10" value="12">
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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#selector-out-of-range">HTML Living Standard<br />
<span class="small">The definition of ':out-of-range' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Defines when <code>:out-of-range</code> matches elements in HTML.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-4/#out-of-range-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':out-of-range' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:out-of-range`

10

13

29

No

11

5.1

2.3

18

16

11

5

1.0

## See also

- [`:in-range`](:in-range)
- [Form data validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range</a>
