# Element.scrollWidth

The `Element.scrollWidth` read-only property is a measurement of the width of an element's content, including content not visible on the screen due to overflow.

The `scrollWidth` value is equal to the minimum width the element would require in order to fit all the content in the viewport without using a horizontal scrollbar. The width is measured in the same way as [`clientWidth`](clientwidth): it includes the element's padding, but not its border, margin or vertical scrollbar (if present). It can also include the width of pseudo-elements such as [`::before`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before) or [`::after`](https://developer.mozilla.org/en-US/docs/Web/CSS/::after). If the element's content can fit without a need for horizontal scrollbar, its `scrollWidth` is equal to [`clientWidth`](clientwidth)

This property will round the value to an integer. If you need a fractional value, use [`element.getBoundingClientRect()`](getboundingclientrect).

## Syntax

    var xScrollWidth = element.scrollWidth;

`xScrollWidth` is the width of the content of `element` in pixels.

## Example

    <!DOCTYPE html>
    <html>
    <head>
        <title>Example</title>
        <style>
            div {
                overflow: hidden;
                white-space: nowrap;
                text-overflow: ellipsis;
            }

            #aDiv {
                width: 100px;
            }

            button {
                margin-bottom: 2em;
            }
        </style>
    </head>

    <body>
        <div id="aDiv">
            FooBar-FooBar-FooBar-FooBar
        </div>
        <button id="aButton">
            Check for overflow
        </button>

        <div id="anotherDiv">
            FooBar-FooBar-FooBar-FooBar
        </div>
        <button id="anotherButton">
            Check for overflow
        </button>
    </body>
    <script>
        var buttonOne = document.getElementById('aButton'),
        buttonTwo = document.getElementById('anotherButton'),
        divOne = document.getElementById('aDiv'),
        divTwo = document.getElementById('anotherDiv');

        //check to determine if an overflow is happening
        function isOverflowing(element) {
            return (element.scrollWidth > element.offsetWidth);
        }

        function alertOverflow(element) {
            if (isOverflowing(element)) {
                alert('Contents are overflowing the container.');
            } else {
                alert('No overflows!');
            }
        }

        buttonOne.addEventListener('click', function() {
            alertOverflow(divOne);
        });

        buttonTwo.addEventListener('click', function() {
            alertOverflow(divTwo);
        });
    </script>
    </html>

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-element-scrollwidth">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Element.scrollWidth' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`scrollWidth`

1

12

1

5

In Internet Explorer 5 through 7, if padding is set, the value of `scrollWidth` is equal to the sum of the left and right padding. This behavior was fixed in Internet Explorer 8.

≤12.1

1

1

18

4

≤12.1

1

1.0

## See also

- [`Element.clientWidth`](clientwidth)
- [`HTMLElement.offsetWidth`](../htmlelement/offsetwidth)
- [Determining the dimensions of elements](../css_object_model/determining_the_dimensions_of_elements)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollWidth" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollWidth</a>
