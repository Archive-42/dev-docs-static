# @supports

The `@supports` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [at-rule](at-rule) lets you specify declarations that depend on a browser's support for one or more specific CSS features. This is called a _feature query_. The rule may be placed at the top level of your code or nested inside any other [conditional group at-rule](at-rule#conditional_group_rules).

    @supports (display: grid) {
      div {
        display: grid;
      }
    }

    @supports not (display: grid) {
      div {
        float: right;
      }
    }

In JavaScript, `@supports` can be accessed via the CSS object model interface [`CSSSupportsRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSSupportsRule).

## Syntax

The `@supports` at-rule associates a block of statements with a _supports condition._ The supports condition consists of one or more name-value pairs combined by conjunctions (`and`), disjunctions (`or`), and/or negations (`not`). Precedence of operators can be defined with parentheses.

### Declaration syntax

The most basic supports condition is a simple declaration (a property name followed by a value, separated by a colon). The declaration must be surrounded by parentheses. The following example returns true if the browser's [`transform-origin`](transform-origin) property considers `5% 5%` valid:

    @supports (transform-origin: 5% 5%) {}

### Function syntax

The second basic supports condition is a supports function, the syntax for these is supported by all browsers, but the functions themselves are still being standardized.

#### `selector()` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

Tests if the browser supports the tested selector syntax. The following example returns true if the browser supports the [child combinator](child_combinator):

    @supports selector(A > B) {}

### The not operator

The `not` operator can precede any expression to create a new expression, resulting in the negation of the original one. The following example returns true if the browser's [`transform-origin`](transform-origin) property **doesn't** consider `10em 10em 10em` valid:

    @supports not (transform-origin: 10em 10em 10em) {}

As with any operator, the `not` operator can be applied to a declaration of any complexity. The following examples are both valid:

    @supports not (not (transform-origin: 2px)) {}
    @supports (display: grid) and (not (display: inline-grid)) {}

**Note:** There is no need to enclose the `not` operator between two parentheses at the top level. To combine it with other operators, like `and` and `or`, the parentheses are required.

### The and operator

The `and` operator creates a new expression from the conjunction of two shorter expressions. It returns true only if **both** of the shorter expressions are also true. The following example returns true if and only if the two shorter expressions are simultaneously true:

    @supports (display: table-cell) and (display: list-item) {}

Multiple conjunctions can be juxtaposed without the need of more parentheses. The following are both equivalent:

    @supports (display: table-cell) and (display: list-item) and (display:contents) {}
    @supports (display: table-cell) and ((display: list-item) and (display:contents)) {}

### The or operator

The `or` operator creates a new expression from the disjunction of two shorter expressions. It returns true if **one or both** of the shorter expressions is also true. The following example returns true if at least one of the two shorter expressions is true:

    @supports (transform-style: preserve) or (-moz-transform-style: preserve) {}

Multiple disjunctions can be juxtaposed without the need of more parentheses. The following are both equivalent:

    @supports (transform-style: preserve) or (-moz-transform-style: preserve) or
              (-o-transform-style: preserve) or (-webkit-transform-style: preserve) {}

    @supports (transform-style: preserve-3d) or ((-moz-transform-style: preserve-3d) or
              ((-o-transform-style: preserve-3d) or (-webkit-transform-style: preserve-3d))) {}

**Note**: When using both `and` and `or` operators, the parentheses must be used to define the order in which they apply. Otherwise, the condition is invalid and the whole rule is ignored.

## Formal syntax

    @supports <supports-condition> {
      <group-rule-body>
    }where
    <supports-condition> = not <supports-in-parens> | <supports-in-parens> [ and <supports-in-parens> ]* | <supports-in-parens> [ or <supports-in-parens> ]*where
    <supports-in-parens> = ( <supports-condition> ) | <supports-feature> | <general-enclosed>where
    <supports-feature> = <supports-decl> | <supports-selector-fn>
    <general-enclosed> = [ <function-token> <any-value> ) ] | ( <ident> <any-value> )where
    <supports-decl> = ( <declaration> )
    <supports-selector-fn> = selector( <complex-selector> )where
    <complex-selector> = <compound-selector> [ <combinator>? <compound-selector> ]*where
    <compound-selector> = [ <type-selector>? <subclass-selector>* [ <pseudo-element-selector> <pseudo-class-selector>* ]* ]!
    <combinator> = '>' | '+' | '~' | [ '||' ]where
    <type-selector> = <wq-name> | <ns-prefix>? '*'
    <subclass-selector> = <id-selector> | <class-selector> | <attribute-selector> | <pseudo-class-selector>
    <pseudo-element-selector> = ':' <pseudo-class-selector>
    <pseudo-class-selector> = ':' <ident-token> | ':' <function-token> <any-value> ')'where
    <wq-name> = <ns-prefix>? <ident-token>
    <ns-prefix> = [ <ident-token> | '*' ]?  |
    <id-selector> = <hash-token>
    <class-selector> = '.' <ident-token>
    <attribute-selector> = '[' <wq-name> ']' | '[' <wq-name> <attr-matcher> [ <string-token> | <ident-token> ] <attr-modifier>? ']'
    where
    <attr-matcher> = [ '~' |  |  | '^' | '$' | '*' ]? '='
    <attr-modifier> = i | s

## Examples

### Testing for the support of a given CSS property

    @supports (animation-name: test) {
      … /* CSS applied when animations are supported without a prefix */
      @keyframes { /* Other at-rules can be nested inside */
        …
      }
    }

### Testing for the support of a given CSS property or a prefixed version

    @supports ((perspective: 10px) or (-moz-perspective: 10px) or (-webkit-perspective: 10px) or
             (-ms-perspective: 10px) or (-o-perspective: 10px)) {
      … /* CSS applied when 3D transforms, prefixed or not, are supported */
    }

### Testing for the non-support of a specific CSS property

    @supports not ((text-align-last: justify) or (-moz-text-align-last: justify)) {
      … /* CSS to provide fallback alternative for text-align-last: justify */
    }

### Testing for the support of custom properties

    @supports (--foo: green) {
      body {
        color: var(--varName);
      }
    }

### Testing for the support of a selector (eg. `:is()`)

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

    /* This rule won't be applied in browsers which don't support :is() */
    :is(ul, ol) > li {
      … /* CSS applied when the :is(…) selector is supported */
    }

    @supports not selector(:is(a, b)) {
      /* Fallback for when :is() is unsupported */
      ul > li,
      ol > li {
        … /* The above expanded for browsers which don't support :is(…) */
      }
    }

    /* Note: By far, there's no browser that supports the `of` argument of :nth-child(…) */
    @supports selector(:nth-child(1n of a, b)) {
      /* This rule needs to be inside the @supports block, otherwise
         it will be partially applied in browsers which don't support
         the `of` argument of :nth-child(…) is supported */
      :is(
          :nth-child(1n of ul, ol) a,
          details > summary
      ) {
        … /* CSS applied when the :is(…) selector and
             the `of` argument of :nth-child(…) are both supported */
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-conditional-4/#at-supports-ext">CSS Conditional Rules Module Level 4<br />
<span class="small">The definition of '@supports' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Adds the <code>selector()</code> function.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-conditional-3/#at-supports">CSS Conditional Rules Module Level 3<br />
<span class="small">The definition of '@supports' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`@supports`

28

12

22

No

12.1

9

≤37

28

22

12.1

9

1.5

`selector`

83

83

69

64

No

69

No

See [bug 199237](https://webkit.org/b/199237)

83

83

64

No

See [bug 979041](https://crbug.com/979041).

No

See [bug 199237](https://webkit.org/b/199237)

13.0

## See also

- [Using feature queries](css_conditional_rules/using_feature_queries)
- The CSSOM class [`CSSSupportsRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSSupportsRule), and the [`CSS.supports()`](https://developer.mozilla.org/en-US/docs/Web/API/CSS/supports) method that allows the same check to be performed via JavaScript.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@supports" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@supports</a>
