HTMLElement.innerText
=====================

The `innerText` property of the [`HTMLElement`](../htmlelement) interface represents the "rendered" text content of a node and its descendants. As a getter, it approximates the text the user would get if they highlighted the contents of the element with the cursor and then copied it to the clipboard.

**Note:** `innerText` is easily confused with [`Node.textContent`](../node/textcontent), but there are important differences between the two. Basically, `innerText` is aware of the rendered appearance of text, while `textContent` is not.

Syntax
------

    const renderedText = htmlElement.innerText
    htmlElement.innerText = string

### Value

A [`DOMString`](../domstring) representing the rendered text content of an element. If the element itself is not [being rendered](https://html.spec.whatwg.org/multipage/rendering.html#being-rendered) (e.g detached from the document or is hidden from view), the returned value is the same as the [`Node.textContent`](../node/textcontent) property.

Example
-------

This example compares `innerText` with [`Node.textContent`](../node/textcontent). Note how `innerText` is aware of things like [`<br>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br) elements, and ignores hidden elements.

### HTML

    <h3>Source element:</h3>
    <p id="source">
      <style>#source { color: red;  } #text { text-transform: uppercase; }</style>
    <span id=text>Take a look at<br>how this text<br>is interpreted
           below.</span>
      <span style="display:none">HIDDEN TEXT</span>
    </p>
    <h3>Result of textContent:</h3>
    <textarea id="textContentOutput" rows="6" cols="30" readonly>...</textarea>
    <h3>Result of innerText:</h3>
    <textarea id="innerTextOutput" rows="6" cols="30" readonly>...</textarea>

### JavaScript

    const source = document.getElementById("source");
    const textContentOutput = document.getElementById("textContentOutput");
    const innerTextOutput = document.getElementById("innerTextOutput");

    textContentOutput.value = source.textContent;
    innerTextOutput.value = source.innerText;

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/dom.html#the-innertext-idl-attribute">HTML Living Standard<br />
<span class="small">The definition of 'innerText' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Introduced, based on the <a href="https://github.com/rocallahan/innerText-spec">draft of the innerText specification</a>. See <a href="https://github.com/whatwg/html/issues/465">whatwg/html#465</a> and <a href="https://github.com/whatwg/compat/issues/5">whatwg/compat#5</a> for history.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`innerText`

1

12

45

5.5

9.6

3

4.4

18

45

10.1

1

1.0

See also
--------

-   [`HTMLElement.outerText`](outertext)
-   [`Element.innerHTML`](../element/innerhtml)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/innerText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/innerText</a>
