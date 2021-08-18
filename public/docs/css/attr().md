# attr()

**Note:** The `attr()` function can be used with any CSS property, but support for properties other than [`content`](content) is experimental, and support for the type-or-unit parameter is sparse.

The `attr()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](css_functions) is used to retrieve the value of an attribute of the selected element and use it in the stylesheet. It can also be used on [pseudo-elements](pseudo-elements), in which case the value of the attribute on the pseudo-element's originating element is returned.

    /* Simple usage */
    attr(data-count);
    attr(title);

    /* With type */
    attr(src url);
    attr(data-count number);
    attr(data-width px);

    /* With fallback */
    attr(data-count number, 0);
    attr(src url, "");
    attr(data-width px, inherit);
    attr(data-something, "default");

## Syntax

### Values

`attribute-name`  
Is the name of an attribute on the HTML element referenced in the CSS.

`<type-or-unit>` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Is a keyword representing either the type of the attribute's value, or its unit, as in HTML some attributes have implicit units. If the use of `<type-or-unit>` as a value for the given attribute is invalid, the `attr()` expression will be invalid too. If omitted, it defaults to `string`. The list of valid values are:

<table><thead><tr class="header"><th>Keyword</th><th>Associated type</th><th>Comment</th><th>Default value</th></tr></thead><tbody><tr class="odd"><td><code>string</code></td><td><a href="string"><code>&lt;string&gt;</code></a></td><td>The attribute value is treated as a CSS <a href="string"><code>&lt;string&gt;</code></a>. It is NOT reparsed, and in particular the characters are used as-is instead of CSS escapes being turned into different characters.</td><td>An empty string.</td></tr><tr class="even"><td><code>color</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td><a href="color_value"><code>&lt;color&gt;</code></a></td><td>The attribute value is parsed as a hash (3- or 6-value hash) or a keyword. It must be a valid CSS <a href="string"><code>&lt;string&gt;</code></a> value.<br />
Leading and trailing spaces are stripped.</td><td><code>currentcolor</code></td></tr><tr class="odd"><td><code>url</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td><a href="url()"><code>&lt;url&gt;()</code></a></td><td>The attribute value is parsed as a string that is used inside a CSS <code>url()</code> function.<br />
Relative URL are resolved relatively to the original document, not relatively to the style sheet.<br />
Leading and trailing spaces are stripped.</td><td>The url <code>about:invalid</code> that points to a non-existent document with a generic error condition.</td></tr><tr class="even"><td><code>integer</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td><a href="integer"><code>&lt;integer&gt;</code></a></td><td>The attribute value is parsed as a CSS <a href="integer"><code>&lt;integer&gt;</code></a>. If it is not valid, that is not an integer or out of the range accepted by the CSS property, the default value is used.<br />
Leading and trailing spaces are stripped.</td><td><code>0</code>, or, if <code>0</code> is not a valid value for the property, the property's minimum value.</td></tr><tr class="odd"><td><code>number</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td><a href="number"><code>&lt;number&gt;</code></a></td><td>The attribute value is parsed as a CSS <a href="number"><code>&lt;number&gt;</code></a>. If it is not valid, that is not a number or out of the range accepted by the CSS property, the default value is used.<br />
Leading and trailing spaces are stripped.</td><td><code>0</code>, or, if <code>0</code> is not a valid value for the property, the property's minimum value.</td></tr><tr class="even"><td><code>length</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td><a href="length"><code>&lt;length&gt;</code></a></td><td>The attribute value is parsed as a CSS <a href="length"><code>&lt;length&gt;</code></a> dimension, that is including the unit (e.g. <code>12.5em</code>). If it is not valid, that is not a length or out of the range accepted by the CSS property, the default value is used.<br />
If the given unit is a relative length, <code>attr()</code> computes it to an absolute length.<br />
Leading and trailing spaces are stripped.</td><td><code>0</code>, or, if <code>0</code> is not a valid value for the property, the property's minimum value.</td></tr><tr class="odd"><td><code>em</code>, <code>ex</code>, <code>px</code>, <code>rem</code>, <code>vw</code>, <code>vh</code>, <code>vmin</code>, <code>vmax</code>, <code>mm</code>, <code>cm</code>, <code>in</code>, <code>pt</code>, or <code>pc</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td><a href="length"><code>&lt;length&gt;</code></a></td><td>The attribute value is parsed as a CSS <a href="number"><code>&lt;number&gt;</code></a>, that is without the unit (e.g. <code>12.5</code>), and interpreted as a <a href="length"><code>&lt;length&gt;</code></a> with the specified unit. If it is not valid, that is not a number or out of the range accepted by the CSS property, the default value is used.<br />
If the given unit is a relative length, <code>attr()</code> computes it to an absolute length.<br />
Leading and trailing spaces are stripped.</td><td><code>0</code>, or, if <code>0</code> is not a valid value for the property, the property's minimum value.</td></tr><tr class="even"><td><code>angle</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td><a href="angle"><code>&lt;angle&gt;</code></a></td><td>The attribute value is parsed as a CSS <a href="angle"><code>&lt;angle&gt;</code></a> dimension, that is including the unit (e.g. <code>30.5deg</code>). If it is not valid, that is not an angle or out of the range accepted by the CSS property, the default value is used.<br />
Leading and trailing spaces are stripped.</td><td><code>0deg</code>, or, if <code>0deg</code> is not a valid value for the property, the property's minimum value.</td></tr><tr class="odd"><td><code>deg</code>, <code>grad</code>, <code>rad</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td><a href="angle"><code>&lt;angle&gt;</code></a></td><td>The attribute value is parsed as a CSS <a href="number"><code>&lt;number&gt;</code></a>, that is without the unit (e.g. <code>12.5</code>), and interpreted as an <a href="angle"><code>&lt;angle&gt;</code></a> with the specified unit. If it is not valid, that is not a number or out of the range accepted by the CSS property, the default value is used.<br />
Leading and trailing spaces are stripped.</td><td><code>0deg</code>, or, if <code>0deg</code> is not a valid value for the property, the property's minimum value.</td></tr><tr class="even"><td><code>time</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td><a href="time"><code>&lt;time&gt;</code></a></td><td>The attribute value is parsed as a CSS <a href="time"><code>&lt;time&gt;</code></a> dimension, that is including the unit (e.g. <code>30.5ms</code>). If it is not valid, that is not a time or out of the range accepted by the CSS property, the default value is used.<br />
Leading and trailing spaces are stripped.</td><td><code>0s</code>, or, if <code>0s</code> is not a valid value for the property, the property's minimum value.</td></tr><tr class="odd"><td><code>s</code>, <code>ms</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td><a href="time"><code>&lt;time&gt;</code></a></td><td>The attribute value is parsed as a CSS <a href="number"><code>&lt;number&gt;</code></a>, that is without the unit (e.g. <code>12.5</code>), and interpreted as an<a href="time"><code>&lt;time&gt;</code></a> with the specified unit. If it is not valid, that is not a number or out of the range accepted by the CSS property, the default value is used.<br />
Leading and trailing spaces are stripped.</td><td><code>0s</code>, or, if <code>0s</code> is not a valid value for the property, the property's minimum value.</td></tr><tr class="even"><td><code>frequency</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td><a href="frequency"><code>&lt;frequency&gt;</code></a></td><td>The attribute value is parsed as a CSS <a href="frequency"><code>&lt;frequency&gt;</code></a> dimension, that is including the unit (e.g. <code>30.5kHz</code>). If it is not valid, that is not a frequency or out of the range accepted by the CSS property, the default value is used.</td><td><code>0Hz</code>, or, if <code>0Hz</code> is not a valid value for the property, the property's minimum value.</td></tr><tr class="odd"><td><code>Hz</code>, <code>kHz</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td><a href="frequency"><code>&lt;frequency&gt;</code></a></td><td>The attribute value is parsed as a CSS <a href="number"><code>&lt;number&gt;</code></a>, that is without the unit (e.g. <code>12.5</code>), and interpreted as a <a href="frequency"><code>&lt;frequency&gt;</code></a> with the specified unit. If it is not valid, that is not a number or out of the range accepted by the CSS property, the default value is used.<br />
Leading and trailing spaces are stripped.</td><td><code>0Hz</code>, or, if <code>0Hz</code> is not a valid value for the property, the property's minimum value.</td></tr><tr class="even"><td><code>%</code> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td><a href="percentage"><code>&lt;percentage&gt;</code></a></td><td>The attribute value is parsed as a CSS <a href="number"><code>&lt;number&gt;</code></a>, that is without the unit (e.g. <code>12.5</code>), and interpreted as a <a href="percentage"><code>&lt;percentage&gt;</code></a>. If it is not valid, that is not a number or out of the range accepted by the CSS property, the default value is used.<br />
If the given value is used as a length, <code>attr()</code> computes it to an absolute length.<br />
Leading and trailing spaces are stripped.</td><td><code>0%</code>, or, if <code>0%</code> is not a valid value for the property, the property's minimum value.</td></tr></tbody></table>

`<fallback>` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The value to be used if the associated attribute is missing or contains an invalid value. If not set, CSS will use the default value defined for each `<type-or-unit>`.

### Formal syntax

    attr( <attr-name> <type-or-unit>? [, <attr-fallback> ]? )where
    <type-or-unit> = string | color | url | integer | number | length | angle | time | frequency | cap | ch | em | ex | ic | lh | rlh | rem | vb | vi | vw | vh | vmin | vmax | mm | Q | cm | in | pt | pc | px | deg | grad | rad | turn | ms | s | Hz | kHz | %

## Examples

### content property

#### HTML

    <p data-foo="hello">world</p>

#### CSS

    [data-foo]::before {
      content: attr(data-foo) " ";
    }

#### Result

### &lt;color&gt; value

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

#### HTML

    <div class="background" data-background="lime">background expected to be red if your browser does not support advanced usage of attr()</div>

#### CSS

    .background {
      background-color: red;
    }

    .background[data-background] {
      background-color: attr(data-background color, red);
    }

## Specifications

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-values-4/#attr-notation">CSS Values and Units Module Level 4<br />
<span class="small">The definition of 'attr()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Changed it to work like <a href="var()"><code>var()</code></a>. Property values involving <code>attr()</code> are valid at parse time, and the validation of the attribute value is deferred to computed value time.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-values-3/#attr-notation">CSS Values and Units Module Level 3<br />
<span class="small">The definition of 'attr()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td><p>Added two optional parameters;<br />
can be used on all properties;<br />
may return values other than <a href="string"><code>&lt;string&gt;</code></a>.</p>These changes are experimental and may be dropped during the CR phase if browser support is too small.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/generate.html#x18">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'attr()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Limited to the <a href="content"><code>content</code></a> property;<br />
always returns a <a href="string"><code>&lt;string&gt;</code></a>.</td></tr></tbody></table>

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

`attr()`

2

12

1

8

9

3.1

≤37

18

4

10.1

3.1

1.0

`fallback`

No

No

No

See [bug 1448248](https://bugzil.la/1448248).

No

No

No

See [bug 204275](https://webkit.org/b/204275).

No

No

No

No

No

No

`type-or-unit`

No

No

No

See [bug 435426](https://bugzil.la/435426).

No

No

No

See [bug 204275](https://webkit.org/b/204275).

No

No

No

No

No

No

## See also

- [Attribute selectors](attribute_selectors)
- [HTML `data-*` attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-*)
- [SVG `data-*` attributes](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/data-*)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/attr()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/attr()</a>
