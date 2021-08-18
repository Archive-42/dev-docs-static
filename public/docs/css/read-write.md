# :read-write

The `:read-write` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents an element (such as `input` or `textarea`) that is editable by the user.

    input:read-write, textarea:read-write {
      background-color: #bbf;
    }

    p:read-write {
      background-color: #bbf;
    }

## Syntax

    :read-write

## Examples

### Confirming form information in read-only/read-write controls

One use of `readonly` form controls is to allow the user to check and verify information that they may have entered in an earlier form (for example, shipping details), while still being able to submit the information along with the rest of the form. We do just this in the example below.

The `:read-only` pseudo-class is used to remove all the styling that makes the inputs look like clickable fields, making them look more like read-only paragraphs.The `:read-write` pseudo-class on the other hand is used to provide some nicer styling to the editable `<textarea>`.

    input:-moz-read-only, textarea:-moz-read-only,
    input:read-only, textarea:read-only {
      border: 0;
      box-shadow: none;
      background-color: white;
    }

    textarea:-moz-read-write,
    textarea:read-write {
      box-shadow: inset 1px 1px 3px #ccc;
      border-radius: 5px;
    }

You can find the full source code at [readonly-confirmation.html](https://github.com/mdn/learning-area/blob/master/html/forms/pseudo-classes/readonly-confirmation.html); this renders like so:

### Styling read-write non-form controls

This selector doesn't just select [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)/[`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) elements — it will select _any_ element that can be edited by the user, such as a [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) element with [`contenteditable`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-contenteditable) set on it.

    <p contenteditable>This paragraph is editable; it is read-write.</p>

    <p>This paragraph is not editable; it is read-only.</p>

    p {
      font-size: 150%;
      padding: 5px;
      border-radius: 5px;
    }

    p:read-only {
      background-color: red;
      color: white;
    }

    p:read-write {
      background-color: lime;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#selector-read-write">HTML Living Standard<br />
<span class="small">The definition of ':read-write' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/#selector-read-write">HTML5<br />
<span class="small">The definition of ':read-write' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defines the semantics regarding HTML and constraint validation.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#rw-pseudos">Selectors Level 4<br />
<span class="small">The definition of ':read-write' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Defines the pseudo-class, but not the associated semantics.</td></tr></tbody></table>

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

`:read-write`

1

13

78

1.5

No

9

4

≤37

18

4

10.1

3.2

1.0

## See also

- [`:read-only`](:read-only)
- HTML [`contenteditable`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-contenteditable) attribute

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:read-write" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:read-write</a>
