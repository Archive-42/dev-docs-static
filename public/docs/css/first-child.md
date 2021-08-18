# :first-child

The `:first-child` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents the first element among a group of sibling elements.

    /* Selects any <p> that is the first element
       among its siblings */
    p:first-child {
      color: lime;
    }

**Note**: As originally defined, the selected element had to have a parent. Beginning with Selectors Level 4, this is no longer required.

## Syntax

    :first-child

## Examples

### Basic example

#### HTML

    <div>
      <p>This text is selected!</p>
      <p>This text isn't selected.</p>
    </div>

    <div>
      <h2>This text isn't selected: it's not a `p`.</h2>
      <p>This text isn't selected.</p>
    </div>

#### CSS

    p:first-child {
      color: lime;
      background-color: black;
      padding: 5px;
    }

#### Result

### Styling a list

#### HTML

    <ul>
      <li>Item 1</li>
      <li>Item 2</li>
      <li>Item 3
        <ul>
          <li>Item 3.1</li>
          <li>Item 3.2</li>
          <li>Item 3.3</li>
        </ul>
      </li>
    </ul>

#### CSS

    ul li {
      color: blue;
    }

    ul li:first-child {
      color: red;
      font-weight: bold;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#first-child-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':first-child' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Matching elements are not required to have a parent.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#first-child-pseudo">Selectors Level 3<br />
<span class="small">The definition of ':first-child' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/selector.html#first-child">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of ':first-child' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:first-child`

4

12

3

7

\["Internet Explorer 7 doesn't update `:first-child` styles when elements are added dynamically.", "In Internet Explorer 8, if an element is inserted dynamically by clicking on a link, then the `:first-child` style isn't applied until the link loses focus."\]

9.5

3.1

≤37

18

4

10.1

4

1.0

`no_parent_required`

57

79

52

No

44

No

57

57

52

43

No

7.0

## See also

- [`:-moz-first-node`](:-moz-first-node) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>
- [`:first-of-type`](:first-of-type)
- [`:last-child`](:last-child)
- [`:nth-child()`](:nth-child)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:first-child" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:first-child</a>
