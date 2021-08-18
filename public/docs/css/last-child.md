# :last-child

The `:last-child` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents the last element among a group of sibling elements.

    /* Selects any <p> that is the last element
       among its siblings */
    p:last-child {
      color: lime;
    }

**Note**: As originally defined, the selected element had to have a parent. Beginning with Selectors Level 4, this is no longer required.

## Syntax

    :last-child

## Examples

### Basic example

#### HTML

    <div>
      <p>This text isn't selected.</p>
      <p>This text is selected!</p>
    </div>

    <div>
      <p>This text isn't selected.</p>
      <h2>This text isn't selected: it's not a `p`.</h2>
    </div>

#### CSS

    p:last-child {
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

    ul li:last-child {
      border: 1px solid red;
      color: red;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#the-last-child-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':last-child' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Matching elements are not required to have a parent.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#last-child-pseudo">Selectors Level 3<br />
<span class="small">The definition of ':last-child' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:last-child`

1

12

1

9

9.5

3.2

≤37

18

4

10.1

3.2

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

- [`:-moz-last-node`](:-moz-last-node) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>
- [`:last-of-type`](:last-of-type)
- [`:first-child`](:first-child)
- [`:nth-child`](:nth-child)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:last-child" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:last-child</a>
