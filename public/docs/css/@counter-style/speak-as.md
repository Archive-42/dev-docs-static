# speak-as

The `speak-as` descriptor specifies how a counter symbol constructed with a given [`@counter-style`](../@counter-style) will be represented in the spoken form. For example, an author can specify a counter symbol to be either spoken as its numerical value or just represented with an audio cue.

## Syntax

    /* Keyword values */
    speak-as: auto;
    speak-as: bullets;
    speak-as: numbers;
    speak-as: words;
    speak-as: spell-out;

    /* @counter-style name value */
    speak-as: <counter-style-name>;

### Values

`auto`  
If the value of `speak-as` is specified as `auto`, then the effective value of `speak-as` will be determined based on the value of the [`@counter-style/system`](system) descriptor:

- If the value of `system` is `alphabetic`, the effective value of `speak-as` will be `spell-out`.
- If `system` is `cyclic`, the effective value of `speak-as` will be `bullets`.
- If `system` is `extends`, the value of `speak-as` will be the same as if `speak-as: auto` is specified on the extended style.
- For all other cases, specifying `auto` has the same effect as specifying `speak-as: numbers`.

`bullets`  
A phrase or an audio cue defined by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) for representing an unordered list item will be read out.

`numbers`  
The numerical value of the counter will be read out in the document language.

`words`  
The user agent will generate a counter value as normal and read it out as a word in the document language.

`spell-out`  
The user agent will generate a counter representation as normal and would read it out letter by letter. If the user agent doesn't know how to read out a particular counter symbol, the user agent might read it out as if the value of `speak-as` was `numbers`.

`<counter-style-name>`  
The name of another counter style, specified as a [`<custom-ident>`](../custom-ident). If included, the counter will be spoken out in the form specified in that counter style, kind of like specifying the [`@counter-style/fallback`](fallback) descriptor. If the specified style does not exist, `speak-as` defaults to `auto`.

## Accessibility concerns

Assistive technology support is very limited for the `speak-as` property. Do not rely on it to convey information critical to understanding the page's purpose.

[Let's Talk About Speech CSS | CSS Tricks](https://css-tricks.com/lets-talk-speech-css/)

## Formal definition

<table><tbody><tr class="odd"><td>Related <a href="../at-rule">at-rule</a></td><td><a href="../@counter-style"><code>@counter-style</code></a></td></tr><tr class="even"><td><a href="../initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="odd"><td><a href="../computed_value">Computed value</a></td><td>as specified</td></tr></tbody></table>

## Formal syntax

    auto | bullets | numbers | words | spell-out | <counter-style-name>where
    <counter-style-name> = <custom-ident>

## Examples

### Setting the spoken form for a counter

#### HTML

    <ul class="list">
      <li>One</li>
      <li>Two</li>
      <li>Three</li>
      <li>Four</li>
      <li>Five</li>
    </ul>

#### CSS

    @counter-style speak-as-example {
      system: fixed;
      symbols:     ;
      suffix: " ";
      speak-as: numbers;
    }

    .list {
      list-style: speak-as-example;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-counter-styles-3/#counter-style-speak-as">CSS Counter Styles Level 3<br />
<span class="small">The definition of 'speak-as' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`speak-as`

No

No

33

No

No

No

No

No

33

No

No

No

## See also

- [`list-style`](../list-style), [`list-style-image`](../list-style-image), [`list-style-position`](../list-style-position)
- [`symbols()`](<../symbols()>), the functional notation creating anonymous counter styles.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/speak-as" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/speak-as</a>
