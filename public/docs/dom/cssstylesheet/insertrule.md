# CSSStyleSheet.insertRule()

The `CSSStyleSheet.insertRule()` method inserts a new [CSS rule](../cssrule) into the [current style sheet](../cssstylesheet), with some [restrictions](#restrictions).

**Note:** Although `insertRule()` is exclusively a method of [`CSSStyleSheet`](../cssstylesheet), it actually inserts the rule into `CSSStyleSheet.cssRules` — its internal [`CSSRuleList`](../cssrulelist).

## Syntax

    stylesheet.insertRule(rule [, index])

### Parameters

`rule`  
A [`DOMString`](../domstring) containing the rule to be inserted. What the inserted rule must contain depends on its type:

- **For [rule-sets](https://developer.mozilla.org/en-US/docs/Web/CSS/Syntax#css_statements)**, both a [selector](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors) and a style declaration.
- **For [at-rules](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule)**, both an at-identifier and the rule content.

`index` <span class="badge inline optional">Optional</span>  
A positive integer less than or equal to `stylesheet.cssRules.length`, representing the newly inserted rule's position in `CSSStyleSheet.cssRules`. The default is `0`. (In older implementations, this was required. See [Browser compatibility](#browser_compatibility) for details.)

### Return value

The newly inserted rule's index within the stylesheet's rule-list.

### Restrictions

CSS has some intuitive and not-so-intuitive restrictions affecting where rules can be inserted. Violating them will likely raise a [`DOMException`](../domexception).

- If `index` &gt; `CSSRuleList.length`, the method aborts with an `IndexSizeError`.
- If `rule` cannot be inserted at `index` `0` due to some CSS constraint, the method aborts with a `HierarchyRequestError`.
- If more than one rule is given in the `rule` parameter, the method aborts with a `SyntaxError`.
- If trying to insert an [`@import`](https://developer.mozilla.org/en-US/docs/Web/CSS/@import) at-rule after a style rule, the method aborts with a `HierarchyRequestError`.
- If `rule` is [`@namespace`](https://developer.mozilla.org/en-US/docs/Web/CSS/@namespace) and the rule-list has more than just `@import` at-rules and/or `@namespace` at-rules, the method aborts with an `InvalidStateError`.

## Examples

### Inserting a new rule

This snippet pushes a new rule onto the top of my stylesheet.

    myStyle.insertRule('#blanc { color: white }', 0);

### Function to add a stylesheet rule

    /**
     * Add a stylesheet rule to the document (it may be better practice
     * to dynamically change classes, so style information can be kept in
     * genuine stylesheets and avoid adding extra elements to the DOM).
     * Note that an array is needed for declarations and rules since ECMAScript does
     * not guarantee a predictable object iteration order, and since CSS is
     * order-dependent.
     * @param {Array} rules Accepts an array of JSON-encoded declarations
     * @example
    addStylesheetRules([
      ['h2', // Also accepts a second argument as an array of arrays instead
        ['color', 'red'],
        ['background-color', 'green', true] // 'true' for !important rules
      ],
      ['.myClass',
        ['background-color', 'yellow']
      ]
    ]);
    */
    function addStylesheetRules (rules) {
      var styleEl = document.createElement('style');

      // Append <style> element to <head>
      document.head.appendChild(styleEl);

      // Grab style element's sheet
      var styleSheet = styleEl.sheet;

      for (var i = 0; i < rules.length; i++) {
        var j = 1,
            rule = rules[i],
            selector = rule[0],
            propStr = '';
        // If the second argument of a rule is an array of arrays, correct our variables.
        if (Array.isArray(rule[1][0])) {
          rule = rule[1];
          j = 0;
        }

        for (var pl = rule.length; j < pl; j++) {
          var prop = rule[j];
          propStr += prop[0] + ': ' + prop[1] + (prop[2] ? ' !important' : '') + ';\n';
        }

        // Insert CSS Rule
        styleSheet.insertRule(selector + '{' + propStr + '}', styleSheet.cssRules.length);
      }
    }

## Polyfill

The below polyfill will correct the input of the arguments of `insertRule()` to standardize them in Internet Explorer 5–8. It supplements `insertRule()` with a function that separates the selector from the rules before sending the arguments to the default native `insertRule()`.

    (function(Sheet_proto){
      var originalInsertRule = Sheet_proto.insertRule;

      if (originalInsertRule.length === 2){ // 2 mandatory arguments: (selector, rules)
        Sheet_proto.insertRule = function(selectorAndRule){
          // First, separate the selector from the rule
          a: for (var i=0, Len=selectorAndRule.length, isEscaped=0, newCharCode=0; i !== Len; ++i) {
            newCharCode = selectorAndRule.charCodeAt(i);
            if (!isEscaped && (newCharCode === 123)) { // 123 = "{".charCodeAt(0)
              // Secondly, find the last closing bracket
              var openBracketPos = i, closeBracketPos = -1;

              for (; i !== Len; ++i) {
                newCharCode = selectorAndRule.charCodeAt(i);
                if (!isEscaped && (newCharCode === 125)) { // 125 = "}".charCodeAt(0)
                  closeBracketPos = i;
                }
                isEscaped ^= newCharCode===92?1:isEscaped; // 92 = "\\".charCodeAt(0)
              }

              if (closeBracketPos === -1) break a; // No closing bracket was found!
                /*else*/ return originalInsertRule.call(
                this, // the sheet to be changed
                selectorAndRule.substring(0, openBracketPos), // The selector
                selectorAndRule.substring(closeBracketPos), // The rule
                arguments[3] // The insert index
              );
            }

            // Works by if the char code is a backslash, then isEscaped
            // gets flipped (XOR-ed by 1), and if it is not a backslash
            // then isEscaped gets XORed by itself, zeroing it
            isEscaped ^= newCharCode===92?1:isEscaped; // 92 = "\\".charCodeAt(0)
          }
          // Else, there is no unescaped bracket
          return originalInsertRule.call(this, selectorAndRule, "", arguments[2]);
        };
      }
    })(CSSStyleSheet.prototype);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssstylesheet-insertrule">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSStyleSheet.insertRule' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Style/">Document Object Model (DOM) Level 2 Style Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSStyleSheet-insertRule">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSStyleSheet.insertRule' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`insertRule`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`optional_index`

1

≤79

55

No

≤15

1

1

18

?

≤14

1

1.0

### Legacy browser support

To support Internet Explorer 8 and below, use: `addRule(selector, rule [, index]);`. Example: `addRule('pre', 'font: 14px verdana'); // add rule at end`

Also note the non-standard `removeRule()` and `.rules` instead of [`deleteRule()`](deleterule) and [`.cssRules`](../cssstylesheet), respectively.

## See also

- [`CSSStyleSheet.deleteRule`](deleterule)
- [Cross-Browser CSS-rules ordering (CSS1)](https://www-archive.mozilla.org/docs/web-developer/css1technote/css1tojs.html#priority)
- [Quirksmode - CSS](https://www.quirksmode.org/dom/w3c_css.html)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/insertRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/insertRule</a>
