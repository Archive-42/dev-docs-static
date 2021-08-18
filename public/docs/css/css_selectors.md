# CSS selectors

**CSS selectors** define the elements to which a set of CSS rules apply.

**Note**: There are no selectors or combinators to select parent items, siblings of parents, or children of parent siblings.

## Basic selectors

[Universal selector](universal_selectors)  
Selects all elements. Optionally, it may be restricted to a specific namespace or to all namespaces.  
**Syntax:** `*` `ns|*` `*|*`  
**Example:** `*` will match all the elements of the document.

[Type selector](type_selectors)  
Selects all elements that have the given node name.  
**Syntax:** `elementname`  
**Example:** `input` will match any [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element.

[Class selector](class_selectors)  
Selects all elements that have the given `class` attribute.  
**Syntax:** `.classname`  
**Example:** `.index` will match any element that has a class of "index".

[ID selector](id_selectors)  
Selects an element based on the value of its `id` attribute. There should be only one element with a given ID in a document.  
**Syntax:** `#idname`  
**Example:** `#toc` will match the element that has the ID "toc".

[Attribute selector](attribute_selectors)  
Selects all elements that have the given attribute.  
**Syntax:** `[attr]` `[attr=value]` `[attr~=value]` `[attr|=value]` `[attr^=value]` `[attr$=value]` `[attr*=value]`  
**Example:** `[autoplay]` will match all elements that have the `autoplay` attribute set (to any value).

## Grouping selectors

[Selector list](selector_list)  
The `,` is a grouping method, it selects all the matching nodes.  
**Syntax:** `A, B`  
**Example:** `div, span` will match both [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) and [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) elements.

## Combinators

[Descendant combinator](descendant_combinator)  
The (space) combinator selects nodes that are descendants of the first element.  
**Syntax:** `A B`  
**Example:** `div span` will match all [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) elements that are inside a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) element.

[Child combinator](child_combinator)  
The `>` combinator selects nodes that are direct children of the first element.  
**Syntax:** `A > B`  
**Example:** `ul > li` will match all [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li) elements that are nested directly inside a [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) element.

[General sibling combinator](general_sibling_combinator)  
The `~` combinator selects siblings. This means that the second element follows the first (though not necessarily immediately), and both share the same parent.  
**Syntax:** `A ~ B`  
**Example:** `p ~ span` will match all [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) elements that follow a [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p), immediately or not.

[Adjacent sibling combinator](adjacent_sibling_combinator)  
The `+` combinator selects adjacent siblings. This means that the second element directly follows the first, and both share the same parent.  
**Syntax:** `A + B`  
**Example:** `h2 + p` will match all [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) elements that directly follow an [`<h2>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements).

[Column combinator](column_combinator) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The `||` combinator selects nodes which belong to a column.  
**Syntax:** `A || B`  
**Example:** `col || td` will match all [`<td>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td) elements that belong to the scope of the [`<col>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/col).

## Pseudo

[Pseudo classes](pseudo-classes)  
The `:` pseudo allow the selection of elements based on state information that is not contained in the document tree.  
**Example:** `a:visited` will match all [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) elements that have been visited by the user.

[Pseudo elements](pseudo-elements)  
The `::` pseudo represent entities that are not included in HTML.  
**Example:** `p::first-line` will match the first line of all [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) elements.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/">Selectors Level 4</a></td><td><span class="spec-wd">Working Draft</span></td><td>Added the <code>||</code> column combinator, grid structural selectors, logical combinators, location, time-dimensional, resource state, linguistic and UI pseudo-classes, modifier for ASCII case-sensitive and case-insensitive attribute value selection.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/">Selectors Level 3</a></td><td><span class="spec-rec">Recommendation</span></td><td>Added the <code>~</code> general sibling combinator and tree-structural pseudo-classes.<br />
Made pseudo-elements use a <code>::</code> double-colon prefix. Additional attribute selectors</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/selector.html">CSS Level 2 (Revision 1)</a></td><td><span class="spec-rec">Recommendation</span></td><td>Added the <code>&gt;</code> child and <code>+</code> adjacent sibling combinators.<br />
Added the <strong>universal</strong> and <strong>attribute</strong> selectors.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/">CSS Level 1</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

See the [pseudo-class](pseudo-classes#specifications) and [pseudo-element](pseudo-elements#specifications) specification tables for details on those.

## See also

- [CSS Specificity](specificity)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors</a>
