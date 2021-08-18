# &lt;display-internal&gt;

Some layout models such as `table` and `ruby` have a complex internal structure, with several different roles that their children and descendants can fill. This page defines those "internal" display values, which only have meaning within that particular layout mode.

## Syntax

Valid `<display-internal>` values:

`table-row-group`  
These elements behave like [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody) HTML elements.

`table-header-group`  
These elements behave like [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead) HTML elements.

`table-footer-group`  
These elements behave like [`<tfoot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tfoot) HTML elements.

`table-row`  
These elements behave like [`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr) HTML elements.

`table-cell`  
These elements behave like [`<td>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td) HTML elements.

`table-column-group`  
These elements behave like [`<colgroup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/colgroup) HTML elements.

`table-column`  
These elements behave like [`<col>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/col) HTML elements.

`table-caption`  
These elements behave like [`<caption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption) HTML elements.

`ruby-base` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
These elements behave like [`<rb>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rb) HTML elements.

`ruby-text` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
These elements behave like [`<rt>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rt) HTML elements.

`ruby-base-container` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
These elements behave like [`<rbc>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rbc) HTML elements generated as anonymous boxes.

`ruby-text-container` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
These elements behave like [`<rtc>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rtc) HTML elements.

## Examples

### CSS tables example

The following example demonstrates laying out a simple form using CSS table layout.

#### HTML

    <main>
      <div>
        <label for="name">Name</label>
        <input type="text" id="name" name="name">
      </div>
      <div>
        <label for="age">Age</label>
        <input type="text" id="age" name="age">
      </div>
    </main>

#### CSS

    main {
      display: table;
    }

    div {
      display: table-row;
    }

    label, input {
      display: table-cell;
      margin: 5px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-display/#typedef-display-internal">CSS Display Module Level 3<br />
<span class="small">The definition of 'display-internal' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td></tr></tbody></table>

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

`display-internal`

No

12-79

38

7

No

No

No

No

38

No

No

No

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

`display-internal`

1

12

1

8

7

1

≤37

18

4

14

1

1.0

BCD tables only load in the browser

`table`, `table-cell`, `table-column`, `table-column-group`, `table-footer-group`, `table-header-group`, `table-row`, and `table-row-group`

### Support of ruby values

BCD tables only load in the browser

`ruby`, `ruby-base`, `ruby-base-container`, `ruby-text`, and `ruby-text-container`

## See also

- [`display`](display)
  - [`<display-outside>`](display-outside)
  - [`<display-inside>`](display-inside)
  - [`<display-listitem>`](display-listitem)
  - [`<display-box>`](display-box)
  - [`<display-legacy>`](display-legacy)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/display-internal</a>
