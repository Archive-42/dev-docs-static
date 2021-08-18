# Using CSS counters

**CSS counters** let you adjust the appearance of content based on its location in a document. For example, you can use counters to automatically number the headings in a webpage. Counters are, in essence, variables maintained by CSS whose values may be incremented by CSS rules to track how many times they're used.

## Using counters

### Manipulating a counter's value

To use a CSS counter, it must first be initialized to a value with the [`counter-reset`](../counter-reset) property (`0` by default). The same property can also be used to change its value to any specific number. Once initialized, a counter's value can be increased or decreased with [`counter-increment`](../counter-increment). The counter's name must not be "none", "inherit", or "initial"; otherwise the declaration is ignored.

### Displaying a counter

The value of a counter can be displayed using either the [`counter()`](<../counter()>) or [`counters()`](<../counters()>) function in a [`content`](../content) property.

The [`counter()`](<../counter()>) function has two forms: 'counter(name)' or 'counter(name, style)'. The generated text is the value of the innermost counter of the given name in scope at the given pseudo-element.The counter is rendered in the specified style (`decimal` by default).

The [`counters()`](<../counters()>) function also has two forms: 'counters(name, string)' or 'counters(name, string, style)'. The generated text is the value of all counters with the given name in scope at the given pseudo-element, from outermost to innermost, separated by the specified string. The counters are rendered in the specified style (`decimal` by default).

### Basic example

This example adds "Section \[the value of the counter\]:" to the beginning of each heading.

#### CSS

    body {
      counter-reset: section;                       /* Set a counter named 'section', and its initial value is 0. */
    }

    h3::before {
      counter-increment: section;                   /* Increment the value of section counter by 1 */
      content: "Section " counter(section) ": ";    /* Display the word 'Section ', the value of
                                                       section counter, and a colon before the content
                                                       of each h3 */
    }

#### HTML

    <h3>Introduction</h3>
    <h3>Body</h3>
    <h3>Conclusion</h3>

#### Result

### A more sophisticated example

A counter must not necessarily be shown every time is incremented. This example counts all links, however the counter is shown only when a link has no text, as a convenient replacement.

#### CSS

    :root {
      counter-reset: link;
    }

    a[href] {
      counter-increment: link;
    }

    a[href]:empty::after {
      content: "[" counter(link) "]";
    }

#### HTML

    <p>See <a href="https://www.mozilla.org/"></a></p>
    <p>Do not forget to <a href="contact-me.html">leave a message</a>!</p>
    <p>See also <a href="https://developer.mozilla.org/"></a></p>

#### Result

## Nesting counters

A CSS counter can be especially useful for making outlined lists, because a new instance of the counter is automatically created in child elements. Using the [`counters()`](<../counters()>) function, separating text can be inserted between different levels of nested counters.

### Example of a nested counter

#### CSS

    ol {
      counter-reset: section;                /* Creates a new instance of the
                                                section counter with each ol
                                                element */
      list-style-type: none;
    }

    li::before {
      counter-increment: section;            /* Increments only this instance
                                                of the section counter */
      content: counters(section, ".") " ";   /* Combines the values of all instances
                                                of the section counter, separated
                                                by a period */
    }

#### HTML

    <ol>
      <li>item</li>          <!-- 1     -->
      <li>item               <!-- 2     -->
        <ol>
          <li>item</li>      <!-- 2.1   -->
          <li>item</li>      <!-- 2.2   -->
          <li>item           <!-- 2.3   -->
            <ol>
              <li>item</li>  <!-- 2.3.1 -->
              <li>item</li>  <!-- 2.3.2 -->
            </ol>
            <ol>
              <li>item</li>  <!-- 2.3.1 -->
              <li>item</li>  <!-- 2.3.2 -->
              <li>item</li>  <!-- 2.3.3 -->
            </ol>
          </li>
          <li>item</li>      <!-- 2.4   -->
        </ol>
      </li>
      <li>item</li>          <!-- 3     -->
      <li>item</li>          <!-- 4     -->
    </ol>
    <ol>
      <li>item</li>          <!-- 1     -->
      <li>item</li>          <!-- 2     -->
    </ol>

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-lists-3/#auto-numbering">CSS Lists Module Level 3<br />
<span class="small">The definition of 'CSS Counters' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/generate.html#counters">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'CSS Counters' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

## See also

- [`counter-reset`](../counter-reset)
- [`counter-set`](../counter-set)
- [`counter-increment`](../counter-increment)
- [`@counter-style`](../@counter-style)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Lists_and_Counters/Using_CSS_counters" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Lists_and_Counters/Using_CSS_counters</a>
