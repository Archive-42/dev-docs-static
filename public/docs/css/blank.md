# :blank

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Note:** The `:blank` selector is considered at risk, as the CSSWG keeps changing it.

See [CSSWG issue \#1967](https://github.com/w3c/csswg-drafts/issues/1967).

The `:blank` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) selects empty user input elements (e.g. [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)).

## Syntax

    :blank

## Examples

### Simple :blank example

In eventual supporting browsers, the `:blank` pseudo-class will enable developers to highlight in some way input controls that are not required, but still have no content filled in, perhaps as a reminder to users.

#### HTML

    <textarea></textarea>

#### CSS

    textarea:blank {
      border: 3px solid red;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#blank-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':blank' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:blank`

No

No

No

See [bug 1197736](https://bugzil.la/1197736).

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

- [`:empty`](:empty)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:blank" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:blank</a>
