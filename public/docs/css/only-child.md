# :only-child

The `:only-child` CSS [pseudo-class](pseudo-classes) represents an element without any siblings. This is the same as `:first-child:last-child` or `:nth-child(1):nth-last-child(1)`, but with a lower specificity.

    /* Selects each <p>, but only if it is the */
    /* only child of its parent */
    p:only-child {
      background-color: lime;
    }

**Note**: As originally defined, the selected element had to have a parent. Beginning with Selectors Level 4, this is no longer required.

## Syntax

    :only-child

## Examples

### Basic example

#### HTML

    <div>
      <div>I am an only child.</div>
    </div>

    <div>
      <div>I am the 1st sibling.</div>
      <div>I am the 2nd sibling.</div>
      <div>I am the 3rd sibling, <div>but this is an only child.</div></div>
    </div>

#### CSS

    div:only-child {
      color: red;
    }

    div {
      display: inline-block;
      margin: 6px;
      outline: 1px solid;
    }

#### Result

### A list example

#### HTML

    <ol>
      <li>First
        <ul>
          <li>This list has just one element.</li>
        </ul>
      </li>
      <li>Second
        <ul>
          <li>This list has three elements.</li>
          <li>This list has three elements.</li>
          <li>This list has three elements.</li>
        </ul>
      </li>
    </ol>

#### CSS

    li li {
      list-style-type: disc;
    }

    li:only-child {
      color: red;
      list-style-type: square;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#only-child-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':only-child' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Matching elements are not required to have a parent.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#only-child-pseudo">Selectors Level 3<br />
<span class="small">The definition of ':only-child' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:only-child`

2

12

1.5

9

9.5

3.1

≤37

18

4

10.1

3.1

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

- [`:only-of-type`](:only-of-type)
- [`:first-child`](:first-child)
- [`:last-child`](:last-child)
- [`:nth-child`](:nth-child)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:only-child" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:only-child</a>
