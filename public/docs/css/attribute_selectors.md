# Attribute selectors

The CSS **attribute selector** matches elements based on the presence or value of a given attribute.

    /* <a> elements with a title attribute */
    a[title] {
      color: purple;
    }

    /* <a> elements with an href matching "https://example.org" */
    a[href="https://example.org"] {
      color: green;
    }

    /* <a> elements with an href containing "example" */
    a[href*="example"] {
      font-size: 2em;
    }

    /* <a> elements with an href ending ".org" */
    a[href$=".org"] {
      font-style: italic;
    }

    /* <a> elements whose class attribute contains the word "logo" */
    a[class~="logo"] {
      padding: 2px;
    }

## Syntax

`[attr]`  
Represents elements with an attribute name of _attr_.

`[attr=value]`  
Represents elements with an attribute name of _attr_ whose value is exactly _value_.

`[attr~=value]`  
Represents elements with an attribute name of _attr_ whose value is a whitespace-separated list of words, one of which is exactly _value_.

`[attr|=value]`  
Represents elements with an attribute name of _attr_ whose value can be exactly _value_ or can begin with _value_ immediately followed by a hyphen, `-` (U+002D). It is often used for language subcode matches.

`[attr^=value]`  
Represents elements with an attribute name of _attr_ whose value is prefixed (preceded) by _value_.

`[attr$=value]`  
Represents elements with an attribute name of _attr_ whose value is suffixed (followed) by _value_.

`[attr*=value]`  
Represents elements with an attribute name of _attr_ whose value contains at least one occurrence of _value_ within the string.

`[attr operator value i]`  
Adding an `i` (or `I`) before the closing bracket causes the value to be compared case-insensitively (for characters within the ASCII range).

`[attr operator value s]` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Adding an `s` (or `S`) before the closing bracket causes the value to be compared case-sensitively (for characters within the ASCII range).

## Examples

### Links

#### CSS

    a {
      color: blue;
    }

    /* Internal links, beginning with "#" */
    a[href^="#"] {
      background-color: gold;
    }

    /* Links with "example" anywhere in the URL */
    a[href*="example"] {
      background-color: silver;
    }

    /* Links with "insensitive" anywhere in the URL,
       regardless of capitalization */
    a[href*="insensitive" i] {
      color: cyan;
    }

    /* Links with "cAsE" anywhere in the URL,
    with matching capitalization */
    a[href*="cAsE" s] {
      color: pink;
    }

    /* Links that end in ".org" */
    a[href$=".org"] {
      color: red;
    }

    /* Links that start with "https" and end in ".org" */
    a[href^="https"][href$=".org"] {
      color: green;
    }

#### HTML

    <ul>
      <li><a href="#internal">Internal link</a></li>
      <li><a href="http://example.com">Example link</a></li>
      <li><a href="#InSensitive">Insensitive internal link</a></li>
      <li><a href="http://example.org">Example org link</a></li>
      <li><a href="https://example.org">Example https org link</a></li>
    </ul>

#### Result

### Languages

#### CSS

    /* All divs with a `lang` attribute are bold. */
    div[lang] {
      font-weight: bold;
    }

    /* All divs without a `lang` attribute are italicized. */
    div:not([lang]) {
      font-style: italic;
    }

    /* All divs in US English are blue. */
    div[lang~="en-us"] {
      color: blue;
    }

    /* All divs in Portuguese are green. */
    div[lang="pt"] {
      color: green;
    }

    /* All divs in Chinese are red, whether
       simplified (zh-CN) or traditional (zh-TW). */
    div[lang|="zh"] {
      color: red;
    }

    /* All divs with a Traditional Chinese
       `data-lang` are purple. */
    /* Note: You could also use hyphenated attributes
       without double quotes */
    div[data-lang="zh-TW"] {
      color: purple;
    }

#### HTML

    <div lang="en-us en-gb en-au en-nz">Hello World!</div>
    <div lang="pt">Olá Mundo!</div>
    <div lang="zh-CN">世界您好！</div>
    <div lang="zh-TW">世界您好！</div>
    <div data-lang="zh-TW">世界您好！</div>

#### Result

### HTML ordered lists

The HTML specification requires the [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type) attribute to be matched case-insensitively due to it primarily being used in the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element, trying to use attribute selectors to with the [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol#attr-type) attribute of an [ordered list](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol) doesn't work without the [case-sensitive](#case-sensitive) modifier.

#### CSS

    /* List types require the case sensitive flag due to a quirk in how HTML treats the type attribute. */
    ol[type="a"] {
      list-style-type: lower-alpha;
      background: red;
    }

    ol[type="a" s] {
      list-style-type: lower-alpha;
      background: lime;
    }

    ol[type="A" s] {
      list-style-type: upper-alpha;
      background: lime;
    }

#### HTML

    <ol type="A">
      <li>Example list</li>
    </ol>

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#attribute-selectors">Selectors Level 4<br />
<span class="small">The definition of 'attribute selectors' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds modifier for ASCII case-sensitive and case-insensitive attribute value selection.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#attribute-selectors">Selectors Level 3<br />
<span class="small">The definition of 'attribute selectors' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/selector.html#attribute-selectors">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'attribute selectors' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`Attribute_selectors`

1

12

1

7

9

3

≤37

18

4

14

1

1.0

`case_insensitive_modifier`

49

79

47

No

36

9

49

49

47

36

9

5.0

`case_sensitive_modifier`

No

See [bug 1041095](https://crbug.com/1041095).

No

See [bug 1041095](https://crbug.com/1041095).

66

No

No

See [bug 1041095](https://crbug.com/1041095).

No

No

See [bug 1041095](https://crbug.com/1041095).

No

See [bug 1041095](https://crbug.com/1041095).

66

No

See [bug 1041095](https://crbug.com/1041095).

No

No

See [bug 1041095](https://crbug.com/1041095).

## See also

- [`attr()`](<attr()>)
- Selecting a single element: [`Document.querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector), [`DocumentFragment.querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/querySelector), or [`Element.querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelector)
- Selecting all matching elements: [`Document.querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll), [`DocumentFragment.querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/querySelectorAll), or [`Element.querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelectorAll)
- The above methods are all implemented based on the [`ParentNode`](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode) mixin; see [`ParentNode.querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/querySelector) and [`ParentNode.querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/querySelectorAll)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors</a>
