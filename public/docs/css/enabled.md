# :enabled

The `:enabled` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents any enabled element. An element is enabled if it can be activated (selected, clicked on, typed into, etc.) or accept focus. The element also has a disabled state, in which it can't be activated or accept focus.

    /* Selects any enabled <input> */
    input:enabled {
      color: blue;
    }

## Syntax

    :enabled

## Examples

The following example makes the color of text and button [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)s green when enabled, and gray when disabled. This helps the user understand which elements can be interacted with.

### HTML

    <form action="url_of_form">
      <label for="FirstField">First field (enabled):</label>
      <input type="text" id="FirstField" value="Lorem"><br>

      <label for="SecondField">Second field (disabled):</label>
      <input type="text" id="SecondField" value="Ipsum" disabled="disabled"><br>

      <input type="button" value="Submit">
    </form>

### CSS

    input:enabled {
      color: #2b2;
    }

    input:disabled {
      color: #aaa;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#selector-enabled">HTML Living Standard<br />
<span class="small">The definition of ':enabled' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/#selector-enabled">HTML5<br />
<span class="small">The definition of ':enabled' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defines the semantics for HTML and forms.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#enableddisabled">Selectors Level 4<br />
<span class="small">The definition of ':enabled' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#enableddisabled">Selectors Level 3<br />
<span class="small">The definition of ':enabled' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defines the pseudo-class, but not the associated semantics.</td></tr></tbody></table>

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

`:enabled`

1

12

1

9

9

3.1

2

18

4

10.1

3.1

1.0

## See also

- [`:disabled`](:disabled)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:enabled" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:enabled</a>
