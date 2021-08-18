# :scope

The `:scope` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents elements that are a reference point for selectors to match against.

    /* Selects a scoped element */
    :scope {
      background-color: lime;
    }

Currently, when used in a stylesheet, `:scope` is the same as [`:root`](:root), since there is not at this time a way to explicitly establish a scoped element. When used from a DOM API such as [`querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelector), [`querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelectorAll), [`matches()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/matches), or [`Element.closest()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/closest), `:scope` matches the element on which the method was called.

## Syntax

    :scope

## Examples

### Identity match

In this simple example, we demonstrate that using the `:scope` pseudo-class from the [`Element.matches()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/matches) method matches the element on which it's called.

#### JavaScript

    let paragraph = document.getElementById("para");
    let output = document.getElementById("output");

    if (paragraph.matches(":scope")) {
      output.innerText = "Yep, the element is its own scope as expected!";
    }

#### HTML

    <p id="para">
      This is a paragraph. It is not an interesting paragraph. Sorry about that.
    </p>
    <p id="output"></p>

#### Result

### Direct children

A situation where the `:scope` pseudo-class prove to be useful is when you need to get direct descendant of an already retrieved [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element).

#### JavaScript

    var context = document.getElementById('context');
    var selected = context.querySelectorAll(':scope > div');

    document.getElementById('results').innerHTML = Array.prototype.map.call(selected, function (element) {
        return '#' + element.getAttribute('id');
    }).join(', ');

#### HTML

    <div id="context">
        <div id="element-1">
            <div id="element-1.1"></div>
            <div id="element-1.2"></div>
        </div>
        <div id="element-2">
            <div id="element-2.1"></div>
        </div>
    </div>
    <p>
        Selected elements ids :
        <span id="results"></span>
    </p>

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#the-scope-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':scope' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:scope`

27

79

32

Firefox 55 removes support for `<style scoped>` but not for the `:scope` pseudo-class, which is still supported. `<style scoped>` made it possible to explicitly set up element scopes, but ongoing discussions about the design of this feature as well as lack of other implementations resulted in the decision to remove it.

20-32

No

15

7

≤37

27

32

Firefox 55 removes support for `<style scoped>` but not for the `:scope` pseudo-class, which is still supported. `<style scoped>` made it possible to explicitly set up element scopes, but ongoing discussions about the design of this feature as well as lack of other implementations resulted in the decision to remove it.

20

15

7

1.5

`dom_api`

27

79

32

No

15

7

≤37

27

32

15

7

1.5

## See also

- The [`:root`](:root) [pseudo-class](pseudo-classes)
- [Locating DOM elements using selectors](https://developer.mozilla.org/en-US/docs/Web/API/Document_object_model/Locating_DOM_elements_using_selectors)
- [`Element.querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelector) and [`Element.querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelectorAll)
- [`Document.querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector) and [`Document.querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll)
- [`DocumentFragment.querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/querySelector) and [`DocumentFragment.querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/querySelectorAll)
- [`ParentNode.querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/querySelector) and [`ParentNode.querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/querySelectorAll)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:scope" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:scope</a>
