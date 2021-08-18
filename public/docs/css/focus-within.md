# :focus-within

The `:focus-within` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents an element that has received focus or _contains_ an element that has received focus. In other words, it represents an element that is itself matched by the [`:focus`](:focus) pseudo-class or has a descendant that is matched by `:focus`. (This includes descendants in [shadow trees](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM).)

    /* Selects a <div> when one of its descendants is focused */
    div:focus-within {
      background: cyan;
    }

This selector is useful, to take a common example, for highlighting an entire [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) container when the user focuses on one of its [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) fields.

## Syntax

    :focus-within

## Examples

In this example, the form will receive special coloring styles when either text input receives focus.

### HTML

    <p>Try typing into this form.</p>

    <form>
      <label for="given_name">Given Name:</label>
      <input id="given_name" type="text">
      <br>
      <label for="family_name">Family Name:</label>
      <input id="family_name" type="text">
    </form>

### CSS

    form {
      border: 1px solid;
      color: gray;
      padding: 4px;
    }

    form:focus-within {
      background: #ff8;
      color: black;
    }

    input {
      margin: 4px;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#the-focus-within-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':focus-within' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:focus-within`

60

79

52

No

47

10.1

60

60

52

44

10.3

8.0

## See also

- [`:focus`](:focus)
- [`:focus-visible`](:focus-visible) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [Grab your user's attention with the focus-within selector](https://dev.to/vtrpldn/grab-your-user-s-attention-with-the-focus-within-css-selector-4d4)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-within" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-within</a>
