# Pseudo-elements

A CSS **pseudo-element** is a keyword added to a selector that lets you style a specific part of the selected element(s). For example, [`::first-line`](::first-line) can be used to change the font of the first line of a paragraph.

    /* The first line of every <p> element. */
    p::first-line {
      color: blue;
      text-transform: uppercase;
    }

**Note:** In contrast to pseudo-elements, [`pseudo-classes`](pseudo-classes) can be used to style an element based on its _state_.

## Syntax

    selector::pseudo-element {
      property: value;
    }

You can use only one pseudo-element in a selector. It must appear after the simple selectors in the statement.

**Note:** As a rule, double colons (`::`) should be used instead of a single colon (`:`). This distinguishes pseudo-classes from pseudo-elements. However, since this distinction was not present in older versions of the W3C spec, most browsers support both syntaxes for the original pseudo-elements.

## Index

Pseudo-elements defined by a set of CSS specifications include the following:

A

- [`::after (:after)`](::after)

B

- [`::backdrop`](::backdrop) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`::before (:before)`](::before)

C

- [`::cue`](::cue)
- [`::cue-region`](::cue-region)

F

- [`::first-letter (:first-letter)`](::first-letter)
- [`::first-line (:first-line)`](::first-line)
- [`::file-selector-button`](::file-selector-button)

G

- [`::grammar-error`](::grammar-error) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

M

- [`::marker`](::marker) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

P

- [`::part()`](::part) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`::placeholder`](::placeholder) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

S

- [`::selection`](::selection)
- [`::slotted()`](::slotted)
- [`::spelling-error`](::spelling-error) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

T

- [`::target-text`](::target-text) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/">CSS Level 1</a></td><td><span class="spec-rec">Recommendation</span></td><td>Defined pseudo-classes and pseudo-elements.</td></tr></tbody></table>

## Browser compatibility

## See also

- [Pseudo-classes](pseudo-classes)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements</a>
