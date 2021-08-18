# Specificity

**Specificity** is the means by which browsers decide which CSS property values are the most relevant to an element and, therefore, will be applied. Specificity is based on the matching rules which are composed of different sorts of [CSS selectors](reference#selectors).

## How is specificity calculated?

Specificity is a weight that is applied to a given CSS declaration, determined by the number of each [selector type](#selector_types) in the matching selector. When multiple declarations have equal specificity, the last declaration found in the CSS is applied to the element. Specificity only applies when the same element is targeted by multiple declarations. As per CSS rules, [directly targeted elements](#directly_targeted_elements_vs._inherited_styles) will always take precedence over rules which an element inherits from its ancestor.

**Note:** [Proximity of elements](#tree_proximity_ignorance) in the document tree has no effect on the specificity.

### Selector Types

The following list of selector types increases by specificity:

1.  [Type selectors](type_selectors) (e.g., `h1`) and pseudo-elements (e.g., `::before`).
2.  [Class selectors](class_selectors) (e.g., `.example`), attributes selectors (e.g., `[type="radio"]`) and pseudo-classes (e.g., `:hover`).
3.  [ID selectors](id_selectors) (e.g., `#example`).

Universal selector ([`*`](universal_selectors)), combinators ([`+`](adjacent_sibling_combinator), [`>`](child_combinator), [`~`](general_sibling_combinator), [''](descendant_combinator), [`||`](column_combinator)) and negation pseudo-class ([`:not()`](:not)) have no effect on specificity. (The selectors declared _inside_ `:not()` do, however.)

For more information, visit: ["Specificity" in "Cascade and inheritance"](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance#specificity_2), you can also visit: <https://specifishity.com>

Inline styles added to an element (e.g., `style="font-weight: bold;"`) always overwrite any styles in external stylesheets, and thus can be thought of as having the highest specificity.

### The !important exception

When an `important` rule is used on a style declaration, this declaration overrides any other declarations. Although technically `!important` has nothing to do with specificity, it interacts directly with it. Using `!important,` however, is **bad practice** and should be avoided because it makes debugging more difficult by breaking the natural [cascading](cascade) in your stylesheets. When two conflicting declarations with the `!important` rule are applied to the same element, the declaration with a greater specificity will be applied.

**Some rules of thumb:**

- **Always** look for a way to use specificity before even considering `!important`
- **Only** use `!important` on page-specific CSS that overrides foreign CSS (from external libraries, like Bootstrap or normalize.css).
- **Never** use `!important` when you're writing a plugin/mashup.
- **Never** use `!important` on site-wide CSS.

`!important`

1.  Make better use of the CSS cascade
2.  Use more specific rules. By indicating one or more elements before the element you're selecting, the rule becomes more specific and gets higher priority:

        <div id="test">
          <span>Text</span>
        </div>

        div#test span { color: green; }
        div span { color: blue; }
        span { color: red; }

    No matter the order, text will be green because that rule is most specific. (Also, the rule for blue overwrites the rule for red, notwithstanding the order of the rules)

3.  As a nonsense special case for (2), duplicate simple selectors to increase specificity when you have nothing more to specify.

        #myId#myId span { color: yellow; }
        .myClass.myClass span { color: orange; }

#### How !important can be used:

##### A) Overriding inline styles

Your global CSS file that sets visual aspects of your site globally may be overwritten by inline styles defined directly on individual elements. Both inline styles and !important are considered very bad practice, but sometimes you need the latter to override the former.

In this case, you could set certain styles in your global CSS file as !important, thus overriding inline styles set directly on elements.

    <div class="foo" style="color: red;">What color am I?</div>

    .foo[style*="color: red"] {
      color: firebrick !important;
    }

Many JavaScript frameworks and libraries add inline styles. Using `!important` with a very targeted selector is one way to override these inline styles.

##### B) Overriding high specificity

    #someElement p {
      color: blue;
    }

    p.awesome {
      color: red;
    }

How do you make `awesome` paragraphs always turn red, even ones inside `#someElement`? Without `!important`, the first rule will have more specificity and will win over the second rule.

#### How to override `!important`

A) Add another CSS rule with `!important`, and either give the selector a higher specificity (adding a tag, id or class to the selector), or add a CSS rule with the same selector at a later point than the existing one. This works because in a specificity tie, the last rule defined wins.

Some examples with a higher specificity:

    table td    { height: 50px !important; }
    .myTable td { height: 50px !important; }
    #myTable td { height: 50px !important; }

B) Or add the same selector after the existing one:

    td { height: 50px !important; }

C) Or, preferably, rewrite the original rule to avoid the use of `!important` altogether.

    [id="someElement"] p {
      color: blue;
    }

    p.awesome {
      color: red;
    }

Including an id as part of an attribute selector instead of as an id selector gives it the same specificity as a class. Both selectors above now have the same weight. In a specificity tie, the last rule defined wins.

#### For more information, visit:

- <https://stackoverflow.com/questions/3706819/what-are-the-implications-of-using-important-in-css>
- <https://stackoverflow.com/questions/9245353/what-does-important-in-css-mean>
- <https://stackoverflow.com/questions/5701149/when-to-use-important-property-in-css>
- <https://stackoverflow.com/questions/11178673/how-to-override-important>
- <https://stackoverflow.com/questions/2042497/when-to-use-important-to-save-the-day-when-working-with-css>

### The :is() and :not() exceptions

The matches-any pseudo-class [`:is()`](:is) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> and the negation pseudo-class [`:not()`](:not) are _not_ considered a pseudo-class in the specificity calculation. But selectors placed into the pseudo-class count as normal selectors when determining the count of [selector types](#selector_types).

This chunk of CSS ...

    div.outer p {
      color: orange;
    }

    div:not(.outer) p {
      color: blueviolet;
    }

... when used with the following HTML ...

    <div class="outer">
      <p>This is in the outer div.</p>
      <div class="inner">
        <p>This text is in the inner div.</p>
      </div>
    </div>

... appears on the screen like this:

### The :where() exception <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The specificity-adjustment pseudo-class [`:where()`](:where) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> always has its specificity replaced with zero.

This chunk of CSS ...

    div:where(.outer) p {
      color: orange;
    }

    div p {
      color: blueviolet;
    }

... when used with the following HTML ...

    <div class="outer">
      <p>This is in the outer div.</p>
      <div class="inner">
        <p>This text is in the inner div.</p>
      </div>
    </div>

... appears on the screen like this:

### Form-based specificity

Specificity is based on the form of a selector. In the following case, the selector `*[id="foo"]` counts as an attribute selector for the purpose of determining the selector's specificity, even though it selects an ID.

The following CSS styles ...

    *#foo {
      color: green;
    }

    *[id="foo"] {
      color: purple;
    }

... when used with this markup ...

    <p id="foo">I am a sample text.</p>

... end up looking like this:

This is because it matches the same element but the ID selector has a higher specificity.

### Tree proximity ignorance

The proximity of an element to other elements that are referenced in a given selector has no impact on specificity. The following style declaration ...

    body h1 {
      color: green;
    }

    html h1 {
      color: purple;
    }

... with the following HTML ...

    <html>
      <body>
        <h1>Here is a title!</h1>
      </body>
    </html>

... will render as:

This is because the two declarations have equal [selector type](#selector_types) counts, but the `html h1` selector is declared last.

### Directly targeted elements vs. inherited styles

Styles for a directly targeted element will always take precedence over inherited styles, regardless of the specificity of the inherited rule. This CSS ...

    #parent {
      color: green;
    }

    h1 {
      color: purple;
    }

... with the following HTML ...

    <html>
      <body id="parent">
        <h1>Here is a title!</h1>
      </body>
    </html>

... will also render as:

This is because the `h1` selector targets the element specifically, but the green selector is only inherited from its parent.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#specificity-rules">Selectors Level 4<br />
<span class="small">The definition of 'Calculating a selector's specificity' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Add the specificity adjustment selector <a href=":where"><code>:where()</code></a>.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#specificity">Selectors Level 3<br />
<span class="small">The definition of 'Calculating a selector's specificity' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Add <a href="pseudo-elements">pseudo-elements</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/cascade.html#specificity">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'Calculating a selector's specificity' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Add <a href="pseudo-classes">pseudo-classes</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#cascading-order">CSS Level 1<br />
<span class="small">The definition of 'Cascading order' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## See also

- Specificity Calculator: An interactive website to test and understand your own CSS rules - <https://specificity.keegan.st/>
- CSS3 Selectors Specificity - [http://www.w3.org/TR/selectors/\#specificity](https://www.w3.org/TR/selectors/#specificity)
- CSS Key Concepts: [CSS syntax](syntax), [at-rule](at-rule), [comments](comments), [specificity](specificity) and [inheritance](inheritance), the [box](css_box_model/introduction_to_the_css_box_model), [layout modes](layout_mode) and [visual formatting models](visual_formatting_model), and [margin collapsing](css_box_model/mastering_margin_collapsing), or the [initial](initial_value), [computed](computed_value), [resolved](resolved_value), [specified](specified_value), [used](used_value), and [actual](actual_value) values. Definitions of [value syntax](value_definition_syntax), [shorthand properties](shorthand_properties) and [replaced elements](replaced_element).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity</a>
