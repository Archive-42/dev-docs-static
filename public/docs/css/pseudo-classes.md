# Pseudo-classes

A [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) **pseudo-class** is a keyword added to a selector that specifies a special state of the selected element(s). For example, [`:hover`](:hover) can be used to change a button's color when the user's pointer hovers over it.

    /* Any button over which the user's pointer is hovering */
    button:hover {
      color: blue;
    }

Pseudo-classes let you apply a style to an element not only in relation to the content of the document tree, but also in relation to external factors like the history of the navigator ([`:visited`](:visited), for example), the status of its content (like [`:checked`](:checked) on certain form elements), or the position of the mouse (like [`:hover`](:hover), which lets you know if the mouse is over an element or not).

**Note:** In contrast to pseudo-classes, [pseudo-elements](pseudo-elements) can be used to style a _specific part_ of an element.

## Linguistic pseudo-classes

These pseudo-classes reflect the document language, and enable the selection of elements based on language or script direction.

[`:dir`](:dir)  
The directionality pseudo-class selects an element based on its directionality as determined by the document language.

[`:lang`](:lang)  
Select an element based on its content language.

## Location pseudo-classes

These pseudo-classes relate to links, and to targeted elements within the current document.

[`:any-link`](:any-link)  
Matches an element if the element would match either [`:link`](:link) or [`:visited`](:visited).

[`:link`](:link)  
Matches links that have not yet been visited.

[`:visited`](:visited)  
Matches links that have been visited.

[`:local-link`](:local-link)  
Matches links whose absolute URL is the same as the target URL, for example anchor links to the same page.

[`:target`](:target)  
Matches the element which is the target of the document URL.

[`:target-within`](:target-within)  
Matches elements which are the target of the document URL, but also elements which have a descendant which is the target of the document URL.

[`:scope`](:scope)  
Represents elements that are a reference point for selectors to match against.

## User action pseudo-classes

These pseudo-classes require some interaction by the user in order for them to apply, such as holding a mouse pointer over an element.

[`:hover`](:hover)  
Matches when a user designates an item with a pointing device, for example holding the mouse pointer over it.

[`:active`](:active)  
Matches when an item is being activated by the user, for example clicked on.

[`:focus`](:focus)  
Matches when an element has focus.

[`:focus-visible`](:focus-visible)  
Matches when an element has focus and the user agent identifies that the element should be visibly focused.

[`:focus-within`](:focus-within)  
Matches an element to which [`:focus`](:focus) applies, plus any element that has a descendant to which [`:focus`](:focus) applies.

## Time-dimensional pseudo-classes

These pseudo-classes apply when viewing something which has timing, such as a [WebVTT](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API) caption track.

[`:current`](:current)  
Represents the element or ancestor of the element that is being displayed.

[`:past`](:past)  
Represents an element that occurs entirely before the [`:current`](:current) element.

[`:future`](:future)  
Represents an element that occurs entirely after the [`:current`](:current) element.

## Resource state pseudo-classes

These pseudo-classes apply to media that is capable of being in a state where it would be described as playing, such as a video.

[`:playing`](:playing)  
Represents a media element that is capable of playing when that element is playing.

[`:paused`](:paused)  
Represents a media element that is capable of playing when that element is paused.

## The input pseudo-classes

These pseudo-classes relate to form elements, and enable selecting elements based on HTML attributes and the state that the field is in before and after interaction.

[`:autofill`](:autofill)  
Matches when an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) has been autofilled by the browser.

[`:enabled`](:enabled)  
Represents a user interface element that is in an enabled state.

[`:disabled`](:disabled)  
Represents a user interface element that is in a disabled state.

[`:read-only`](:read-only)  
Represents any element that cannot be changed by the user.

[`:read-write`](:read-write)  
Represents any element that is user-editable.

[`:placeholder-shown`](:placeholder-shown)  
Matches an input element that is displaying placeholder text, for example from the HTML5 `placeholder` attribute.

[`:default`](:default)  
Matches one or more UI elements that are the default among a set of elements.

[`:checked`](:checked)  
Matches when elements such as checkboxes and radiobuttons are toggled on.

[`:indeterminate`](:indeterminate)  
Matches when UI elements are in an indeterminate state.

[`:blank`](:blank)  
Matches a user-input element which is empty, containing an empty string or other null input.

[`:valid`](:valid)  
Matches an element with valid contents. For example an input element with type 'email' which contains a validly formed email address.

[`:invalid`](:invalid)  
Matches an element with invalid contents. For example an input element with type 'email' with a name entered.

[`:in-range`](:in-range)  
Applies to elements with range limitations, for example a slider control, when the selected value is in the allowed range.

[`:out-of-range`](:out-of-range)  
Applies to elements with range limitations, for example a slider control, when the selected value is outside the allowed range.

[`:required`](:required)  
Matches when a form element is required.

[`:optional`](:optional)  
Matches when a form element is optional.

[`:user-invalid`](:user-invalid)  
Represents an element with incorrect input, but only when the user has interacted with it.

## Tree-structural pseudo-classes

These pseudo-classes relate to the location of an element within the document tree.

[`:root`](:root)  
Represents an element that is the root of the document. In HTML this is usually the `<html>` element.

[`:empty`](:empty)  
Represents an element with no children other than white-space characters.

[`:nth-child`](:nth-child)  
Uses A*n*+B notation to select elements from a list of sibling elements.

[`:nth-last-child`](:nth-last-child)  
Uses A*n*+B notation to select elements from a list of sibling elements, counting backwards from the end of the list.

[`:first-child`](:first-child)  
Matches an element that is the first of its siblings.

[`:last-child`](:last-child)  
Matches an element that is the last of its siblings.

[`:only-child`](:only-child)  
Matches an element that has no siblings. For example a list item with no other list items in that list.

[`:nth-of-type`](:nth-of-type)  
Uses A*n*+B notation to select elements from a list of sibling elements that match a certain type from a list of sibling elements.

[`:nth-last-of-type`](:nth-last-of-type)  
Uses A*n*+B notation to select elements from a list of sibling elements that match a certain type from a list of sibling elements counting backwards from the end of the list.

[`:first-of-type`](:first-of-type)  
Matches an element that is the first of its siblings, and also matches a certain type selector.

[`:last-of-type`](:last-of-type)  
Matches an element that is the last of its siblings, and also matches a certain type selector.

[`:only-of-type`](:only-of-type)  
Matches an element that has no siblings of the chosen type selector.

## Syntax

    selector:pseudo-class {
      property: value;
    }

Like regular classes, you can chain together as many pseudo-classes as you want in a selector.

## Alphabetical index

Pseudo-classes defined by a set of CSS specifications include the following:

A

- [`:active`](:active)
- [`:any-link`](:any-link)
- [`:autofill`](:autofill)

B

- [`:blank`](:blank) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

C

- [`:checked`](:checked)
- [`:current`](:current) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

D

- [`:default`](:default)
- [`:defined`](:defined)
- [`:dir()`](:dir) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`:disabled`](:disabled)

E

- [`:empty`](:empty)
- [`:enabled`](:enabled)

F

- [`:first`](:first)
- [`:first-child`](:first-child)
- [`:first-of-type`](:first-of-type)
- [`:fullscreen`](:fullscreen) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`:future`](:future) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`:focus`](:focus)
- [`:focus-visible`](:focus-visible)
- [`:focus-within`](:focus-within)

H

- [`:has()`](:has) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`:host`](:host)
- [`:host()`](<:host()>)
- [`:host-context()`](<:host-context()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`:hover`](:hover)

I

- [`:indeterminate`](:indeterminate)
- [`:in-range`](:in-range)
- [`:invalid`](:invalid)
- [`:is()`](:is) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

L

- [`:lang()`](:lang)
- [`:last-child`](:last-child)
- [`:last-of-type`](:last-of-type)
- [`:left`](:left)
- [`:link`](:link)
- [`:local-link`](:local-link) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

N

- [`:not()`](:not)
- [`:nth-child()`](:nth-child)
- [`:nth-col()`](:nth-col) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`:nth-last-child()`](:nth-last-child)
- [`:nth-last-col()`](:nth-last-col) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`:nth-last-of-type()`](:nth-last-of-type)
- [`:nth-of-type()`](:nth-of-type)

O

- [`:only-child`](:only-child)
- [`:only-of-type`](:only-of-type)
- [`:optional`](:optional)
- [`:out-of-range`](:out-of-range)

P

- [`:past`](:past) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`:picture-in-picture`](:picture-in-picture)
- [`:placeholder-shown`](:placeholder-shown) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`:paused`](:paused)
- [`:playing`](:playing)

R

- [`:read-only`](:read-only)
- [`:read-write`](:read-write)
- [`:required`](:required)
- [`:right`](:right)
- [`:root`](:root)

S

- [`:scope`](:scope)
- [`:state()`](:state) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

T

- [`:target`](:target)
- [`:target-within`](:target-within) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

U

- [`:user-invalid`](:user-invalid) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

V

- [`:valid`](:valid)
- [`:visited`](:visited)

W

- [`:where()`](:where) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fullscreen.spec.whatwg.org/">Fullscreen API</a></td><td><span class="spec-living">Living Standard</span></td><td>Defined <code>:fullscreen</code>.</td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/#pseudo-classes">HTML Living Standard</a></td><td><span class="spec-living">Living Standard</span></td><td>Defines when particular selectors match HTML elements.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/">Selectors Level 4</a></td><td><span class="spec-wd">Working Draft</span></td><td>Defined <code style="white-space: nowrap;">:any-link</code>, <code>:blank</code>, <code style="white-space: nowrap;">:local-link</code>, <code>:scope</code>, <code>:drop</code>, <code>:current</code>, <code>:past</code>, <code>:future</code>, <code style="white-space: nowrap;">:placeholder-shown</code>, <code style="white-space: nowrap;">:user-invalid</code>, <code style="white-space: nowrap;">:nth-col()</code>, <code style="white-space: nowrap;">:nth-last-col()</code>, <code>:is()</code> and <code>:where()</code>.<br />
Changed <code>:empty</code> to behave like <a href=":-moz-only-whitespace"><code>:-moz-only-whitespace</code></a> <span class="icon non-standard" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This API has not been standardized. </span>.<br />
No significant change for other pseudo-classes defined in <a href="https://drafts.csswg.org/selectors-3/">Selectors Level 3</a> and <a href="https://www.w3.org/TR/html52/">HTML5</a> (though semantic meaning not taken over).</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/">HTML5</a></td><td><span class="spec-rec">Recommendation</span></td><td>Copies the relevant section from the canonical (WHATWG) HTML spec.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/css-ui-3/">CSS Basic User Interface Module Level 3</a></td><td><span class="spec-rec">Recommendation</span></td><td>Defined <code>:default</code>, <code>:valid</code>, <code>:invalid</code>, <code>:in-range</code>, <code>:out-of-range</code>, <code>:required</code>, <code>:optional</code>, <code>:read-only</code> and <code>:read-write</code>, but without the associated semantic meaning.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/">Selectors Level 3</a></td><td><span class="spec-rec">Recommendation</span></td><td>Defined <code>:target</code>, <code>:root</code>, <code>:nth-child()</code>, <code>:nth-last-of-child()</code>, <code>:nth-of-type()</code>, <code>:nth-last-of-type()</code>, <code>:last-child</code>, <code>:first-of-type</code>, <code>:last-of-type</code>, <code>:only-child</code>, <code>:only-of-type</code>, <code>:empty</code> and <code>:not()</code>.<br />
Defined the syntax of <code>:enabled</code>, <code>:disabled</code>, <code>:checked</code>, and <code>:indeterminate</code>, but without the associated semantic meaning.<br />
No significant change for pseudo-classes defined in <a href="https://www.w3.org/TR/CSS2/">CSS Level 2 (Revision 1)</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/">CSS Level 2 (Revision 1)</a></td><td><span class="spec-rec">Recommendation</span></td><td>Defined <code>:lang()</code>, <code>:first-child</code>, <code>:hover</code>, and <code>:focus</code>.<br />
No significant change for pseudo-classes defined in <a href="https://www.w3.org/TR/CSS1/">CSS Level 1</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/">CSS Level 1</a></td><td><span class="spec-rec">Recommendation</span></td><td>Defined <code>:link</code>, <code>:visited</code> and <code>:active</code>, but without the associated semantic meaning.</td></tr></tbody></table>

## See also

- [Pseudo-elements](pseudo-elements)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes</a>
