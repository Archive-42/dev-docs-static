# ruby-align

The `ruby-align` CSS property defines the distribution of the different ruby elements over the base.

    /* Keyword values */
    ruby-align: start;
    ruby-align: center;
    ruby-align: space-between;
    ruby-align: space-around;

    /* Global values */
    ruby-align: inherit;
    ruby-align: initial;
    ruby-align: unset;

## Syntax

### Values

`start`  
Is a keyword indicating that the ruby will be aligned with the start of the base text.

`center`  
Is a keyword indicating that the ruby will be aligned at the middle of the base text.

`space-between`  
Is a keyword indicating that the extra space will be distributed between the elements of the ruby.

`space-around`  
Is a keyword indicating that the extra space will be distributed between the elements of the ruby, and around it.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>space-around</code></td></tr><tr class="even"><td>Applies to</td><td>ruby bases, ruby annotations, ruby base containers, ruby annotation containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    start | center | space-between | space-around

## Examples

### Ruby aligned at the start of the base text

#### HTML

    <ruby>
      <rb>This is a long text to check</rb>
      <rp>（</rp><rt>short ruby</rt><rp>）</rp>
    </ruby>

#### CSS

    ruby {
      ruby-align: start;
    }

#### Result

### Ruby aligned at the center of the base text

#### HTML

    <ruby>
      <rb>This is a long text to check</rb>
      <rp>（</rp><rt>short ruby</rt><rp>）</rp>
    </ruby>

#### CSS

    ruby {
      ruby-align: center;
    }

#### Result

### Extra space distributed between ruby elements

#### HTML

    <ruby>
      <rb>This is a long text to check</rb>
      <rp>（</rp><rt>short ruby</rt><rp>）</rp>
    </ruby>

#### CSS

    ruby {
      ruby-align: space-between;
    }

#### Result

### Extra space distributed between and around ruby elements

#### HTML

    <ruby>
      <rb>This is a long text to check</rb>
      <rp>（</rp><rt>short ruby</rt><rp>）</rp>
    </ruby>

#### CSS

    ruby {
      ruby-align: space-around;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-ruby/#ruby-align-property">CSS Ruby Layout Module Level 1<br />
<span class="small">The definition of 'ruby-align' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`ruby-align`

No

No

38

No

Internet Explorer 9 and later supports an earlier draft of CSS Ruby with non-standard values for this property: `auto`, `left`, `center`, `right`, `distribute-letter`, `distribute-space`, and `line-edge`.

No

No

No

No

38

No

No

No

## See also

- HTML Ruby elements: [`<ruby>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ruby), [`<rt>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rt), [`<rp>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rp), and [`<rtc>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rtc).
- CSS Ruby properties: [`ruby-position`](ruby-position), <span class="page-not-created">`ruby-merge`</span>.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/ruby-align" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/ruby-align</a>
