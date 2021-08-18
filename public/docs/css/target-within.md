# :target-within

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `:target-within` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents an element that is a target element or _contains_ an element that is a target. A target element is a unique element with an `id` matching the URL's fragment. In other words, it represents an element that is itself matched by the [`:target`](:target) pseudo-class or has a descendant that is matched by `:target`. (This includes descendants in [shadow trees](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM).)

    /* Selects a <div> when one of its descendants is a target */
    div:target-within {
      background: cyan;
    }

## Syntax

    :target-within

## Examples

### Highlighting an article

The `:target-within` pseudo-class can be used to highlight the article if anything inside it has been directly linked to. The `:target` pseudo-class is also being used to show which item has been targeted.

#### HTML

    <h3>Table of Contents</h3>
    <ol>
     <li><a href="#p1">Jump to the first paragraph!</a></li>
     <li><a href="#p2">Jump to the second paragraph!</a></li>

    </ol>

    <article>

    <h3>My Fun Article</h3>
    <p id="p1">You can target <i>this paragraph</i> using a
      URL fragment. Click on the link above to try out!</p>
    <p id="p2">This is <i>another paragraph</i>, also accessible
      from the links above. Isn't that delightful?</p>
    </article>

#### CSS

    article:target-within {
      background-color: gold;
    }

    /* Add a pseudo-element inside the target element */
    p:target::before {
      font: 70% sans-serif;
      content: "►";
      color: limegreen;
      margin-right: .25em;
    }

    /* Style italic elements within the target element */
    p:target i {
      color: red;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#the-target-within-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':target-within' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:target-within`

No

No

No

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

- [`:target`](:target)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:target-within" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:target-within</a>
