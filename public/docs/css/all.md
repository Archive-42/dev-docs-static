# all

The `all` [shorthand](shorthand_properties) [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property resets all of an element's properties except [`unicode-bidi`](unicode-bidi), [`direction`](direction), and [CSS Custom Properties](using_css_custom_properties). It can set properties to their initial or inherited values, or to the values specified in another stylesheet origin.

## Syntax

    /* Global values */
    all: initial;
    all: inherit;
    all: unset;

    /* CSS Cascading and Inheritance Level 4 */
    all: revert;

The `all` property is specified as one of the CSS global keyword values. Note that none of these values affect the [`unicode-bidi`](unicode-bidi) and [`direction`](direction) properties.

### Values

[`initial`](initial)  
Specifies that all the element's properties should be changed to their [initial values](initial_value).

[`inherit`](inherit)  
Specifies that all the element's properties should be changed to their [inherited values](inheritance).

[`unset`](unset)  
Specifies that all the element's properties should be changed to their inherited values if they inherit by default, or to their initial values if not.

[`revert`](revert)  
Specifies behavior that depends on the stylesheet origin to which the declaration belongs:

[User-agent origin](cascade#user-agent_stylesheets)  
Equivalent to `unset`.

[User origin](cascade#user_stylesheets)  
Rolls back the [cascade](cascade) to the user-agent level, so that the [specified values](specified_value) are calculated as if no author-level or user-level rules were specified for the element.

[Author origin](cascade#author_stylesheets)  
Rolls back the [cascade](cascade) to the user level, so that the [specified values](specified_value) are calculated as if no author-level rules were specified for the element. For purposes of `revert`, the Author origin includes the Override and Animation origins.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>There is no practical initial value for it.</td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as the specified value applies to each property this is a shorthand for.</td></tr><tr class="odd"><td>Animation type</td><td>as each of the properties of the shorthand (all properties but <a href="unicode-bidi"><code>unicode-bidi</code></a> and <a href="direction"><code>direction</code></a>)</td></tr></tbody></table>

## Formal syntax

    initial | inherit | unset | revert

## Examples

### HTML

    <blockquote id="quote">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    </blockquote>
    Phasellus eget velit sagittis.

### CSS

    body {
      font-size: small;
      background-color: #F0F0F0;
      color: blue;
    }

    blockquote {
      background-color: skyblue;
      color: red;
    }

### Result

#### No `all` property

The [`<blockquote>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote) uses the browser's default styling which gives it a margin, together with a specific background and text color. It also behaves as a _block_ element: the text that follows it is beneath it.

#### `all:unset`

The [`<blockquote>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote) doesn't use the browser default styling: it is an _inline_ element now (initial value), its [`background-color`](background-color) is `transparent` (initial value), but its [`font-size`](font-size) is still `small` (inherited value) and its [`color`](color) is `blue` (inherited value).

#### `all:initial`

The [`<blockquote>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote) doesn't use the browser default styling: it is an _inline_ element now (initial value), its [`background-color`](background-color) is `transparent` (initial value), its [`font-size`](font-size) is `normal` (initial value) and its [`color`](color) is `black` (initial value).

#### `all:inherit`

The [`<blockquote>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote) doesn't use the browser default styling: it is a _block_ element now (inherited value from its containing [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) element), its [`background-color`](background-color) is `#F0F0F0` (inherited value), its [`font-size`](font-size) is `small` (inherited value) and its [`color`](color) is `blue` (inherited value).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-cascade/#all-shorthand">CSS Cascading and Inheritance Level 4<br />
<span class="small">The definition of 'all' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added the <code>revert</code> value.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-cascade-3/#all-shorthand">CSS Cascading and Inheritance Level 3<br />
<span class="small">The definition of 'all' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`all`

37

79

27

No

24

9.1

37

37

27

24

9.3

3.0

`revert`

84

84

67

No

70

9.1

84

84

67

No

9.3

No

## See also

CSS global keyword values: [`initial`](initial), [`inherit`](inherit), [`unset`](unset), [`revert`](revert)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/all" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/all</a>
