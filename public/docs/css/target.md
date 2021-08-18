# :target

The `:target` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents a unique element (the _target element_) with an [`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-id) matching the URL's fragment.

    /* Selects an element with an ID matching the current URL's fragment */
    :target {
      border: 2px solid black;
    }

For example, the following URL has a fragment (denoted by the _\#_ sign) that points to an element called `section2`:

    http://www.example.com/index.html#section2

The following element would be selected by a `:target` selector when the current URL is equal to the above:

    <section id="section2">Example</section>

## Syntax

    :target

## Examples

### A table of contents

The `:target` pseudo-class can be used to highlight the portion of a page that has been linked to from a table of contents.

#### HTML

    <h3>Table of Contents</h3>
    <ol>
     <li><a href="#p1">Jump to the first paragraph!</a></li>
     <li><a href="#p2">Jump to the second paragraph!</a></li>
     <li><a href="#nowhere">This link goes nowhere,
       because the target doesn't exist.</a></li>
    </ol>

    <h3>My Fun Article</h3>
    <p id="p1">You can target <i>this paragraph</i> using a
      URL fragment. Click on the link above to try out!</p>
    <p id="p2">This is <i>another paragraph</i>, also accessible
      from the links above. Isn't that delightful?</p>

#### CSS

    p:target {
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

### Pure-CSS lightbox

You can use the `:target` pseudo-class to create a lightbox without using any JavaScript. This technique relies on the ability of anchor links to point to elements that are initially hidden on the page. Once targeted, the CSS changes their `display` so that they are shown.

**Note**

A more complete pure-CSS lightbox based on the `:target` pseudo-class is [available on GitHub](https://github.com/madmurphy/takefive.css/) ([demo](https://madmurphy.github.io/takefive.css/)).

#### HTML

    <ul>
      <li><a href="#example1">Open example #1</a></li>
      <li><a href="#example2">Open example #2</a></li>
    </ul>

    <div class="lightbox" id="example1">
      <figure>
        <a href="#" class="close"></a>
        <figcaption>Lorem ipsum dolor sit amet, consectetur adipiscing elit.
          Donec felis enim, placerat id eleifend eu, semper vel sem.</figcaption>
      </figure>
    </div>

    <div class="lightbox" id="example2">
      <figure>
        <a href="#" class="close"></a>
        <figcaption>Cras risus odio, pharetra nec ultricies et,
          mollis ac augue. Nunc et diam quis sapien dignissim auctor.
          Quisque quis neque arcu, nec gravida magna.</figcaption>
      </figure>
    </div>

#### CSS

    /* Unopened lightbox */
    .lightbox {
      display: none;
    }

    /* Opened lightbox */
    .lightbox:target {
      position: absolute;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    /* Lightbox content */
    .lightbox figcaption {
      width: 25rem;
      position: relative;
      padding: 1.5em;
      background-color: lightpink;
    }

    /* Close button */
    .lightbox .close {
      position: relative;
      display: block;
    }

    .lightbox .close::after {
      right: -1rem;
      top: -1rem;
      width: 2rem;
      height: 2rem;
      position: absolute;
      display: flex;
      z-index: 1;
      align-items: center;
      justify-content: center;
      background-color: black;
      border-radius: 50%;
      color: white;
      content: "×";
      cursor: pointer;
    }

    /* Lightbox overlay */
    .lightbox .close::before {
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      position: fixed;
      background-color: rgba(0,0,0,.7);
      content: "";
      cursor: default;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/browsers.html#selector-target">HTML Living Standard<br />
<span class="small">The definition of ':target' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Defines HTML-specific semantics.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-4/#the-target-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':target' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No changes.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-3/#target-pseudo">Selectors Level 3<br />
<span class="small">The definition of ':target' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:target`

1

12

1

9

9.5

1.3

2

18

4

10.1

2

1.0

## See also

- [Using the :target pseudo-class in selectors](css_selectors/using_the_:target_pseudo-class_in_selectors)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:target" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:target</a>
