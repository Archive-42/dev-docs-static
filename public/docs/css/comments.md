# Comments

A CSS **comment** is used to add explanatory notes to the code or to prevent the browser from interpreting specific parts of the style sheet. By design, comments have no effect on the layout of a document.

## Syntax

Comments can be placed wherever white space is allowed within a style sheet. They can be used on a single line, or traverse multiple lines.

    /* Comment */

## Examples

    /* A one-line comment */

    /*
    A comment
    which stretches
    over several
    lines
    */

    /* The comment below is used to
       disable specific styling */
    /*
    span {
      color: blue;
      font-size: 1.5em;
    }
    */

## Notes

The `/* */` comment syntax is used for both single and multiline comments. There is no other way to specify comments in external style sheets. However, when using the [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) element, you may use `<!-- -->` to hide CSS from older browsers, although this is not recommended. As with most programming languages that use the `/* */` comment syntax, comments cannot be nested. In other words, the first instance of `*/` that follows an instance of `/*` closes the comment.

## Specifications

- [CSS 2.1 Syntax and basic data types \#comments](https://www.w3.org/TR/CSS21/syndata.html#comments)

## See also

- CSS Key Concepts: [CSS syntax](syntax), [at-rule](at-rule), [comments](comments), [specificity](specificity) and [inheritance](inheritance), the [box](css_box_model/introduction_to_the_css_box_model), [layout modes](layout_mode) and [visual formatting models](visual_formatting_model), and [margin collapsing](css_box_model/mastering_margin_collapsing), or the [initial](initial_value), [computed](computed_value), [resolved](resolved_value), [specified](specified_value), [used](used_value), and [actual](actual_value) values. Definitions of [value syntax](value_definition_syntax), [shorthand properties](shorthand_properties) and [replaced elements](replaced_element).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Comments" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Comments</a>
