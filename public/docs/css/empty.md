# :empty

The `:empty` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents any element that has no children. Children can be either element nodes or text (including whitespace). Comments, processing instructions, and CSS [`content`](content) do not affect whether an element is considered empty.

**Note:** In [Selectors Level 4](https://drafts.csswg.org/selectors-4/#the-empty-pseudo) the `:empty` pseudo-class was changed to act like <span style="white-space: nowrap;">[`:-moz-only-whitespace`](:-moz-only-whitespace)</span>, but no browser currently supports this yet.

    /* Selects any <div> that contains no content */
    div:empty {
      background: lime;
    }

## Syntax

    :empty

## Examples

### HTML

    <div class="box"><!-- I will be lime. --></div>
    <div class="box">I will be pink.</div>
    <div class="box">
        <!-- I will be pink in older browsers because of the whitespace around this comment. -->
    </div>
    <div class="box">
        <p><!-- I will be pink in all browsers because of the non-collapsible whitespace and elements around this comment. --></p>
    </div>

### CSS

    .box {
      background: pink;
      height: 80px;
      width: 80px;
    }

    .box:empty {
      background: lime;
    }

### Result

## Accessibility concerns

Assistive technology such as screen readers cannot parse interactive content that is empty. All interactive content must have an accessible name, which is created by providing a text value for the interactive control's parent element ([anchors](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a), [buttons](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button), etc.). Accessible names expose the interactive control to the [accessibility tree](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#accessibility_apis), an API that communicates information useful for assistive technologies.

The text that provides the interactive control's accessible name can be hidden using [a combination of properties](https://gomakethings.com/hidden-content-for-better-a11y/#hiding-the-link) that remove it visually from the screen but keep it parsable by assistive technology. This is commonly used for buttons that rely solely on an icon to convey purpose.

- [What is an accessible name? | The Paciello Group](https://developer.paciellogroup.com/blog/2017/04/what-is-an-accessible-name/)
- [Hidden content for better a11y | Go Make Things](https://gomakethings.com/hidden-content-for-better-a11y/)
- [MDN Understanding WCAG, Guideline 2.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Operable#guideline_2.4_%e2%80%94_navigable_provide_ways_to_help_users_navigate_find_content_and_determine_where_they_are)
- [Understanding Success Criterion 2.4.4 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-refs.html)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#the-empty-pseudo">Selectors Level 4<br />
<span class="small">The definition of 'the <code>:empty</code> pseudo-class' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Changed to act like <a href=":-moz-only-whitespace"><code>:-moz-only-whitespace</code></a>.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#empty-pseudo">Selectors Level 3<br />
<span class="small">The definition of 'the <code>:empty</code> pseudo-class' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`:empty`

1

12

1

9

9.5

3.1

2

18

4

10.1

3.1

1.0

`matches_whitespace`

No

No

No

See [bug 1106296](https://bugzil.la/1106296).

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

- [`:-moz-only-whitespace`](:-moz-only-whitespace) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> – The <span class="page-not-created">prefixed</span> implementation of the changes in [Selectors Level 4](https://drafts.csswg.org/selectors-4/#the-empty-pseudo)
- [`:blank`](:blank) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:empty" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:empty</a>
