# Using the CSS Typed Object Model

The **[CSS Typed Object Model API](../css_typed_om_api)** exposes CSS values as typed JavaScript objects to allow their performant manipulation.

Converting [CSS Object Model](../css_object_model) value strings into meaningfully-typed JavaScript representations and back (via [`HTMLElement.style`](../elementcssinlinestyle/style) can incur a significant performance overhead.

The CSS Typed OM makes CSS manipulation more logical and performant by providing object features (rather than CSSOM string manipulation), providing access to types, methods, and an object model for CSS values.

This article provides an introduction to all of its main features.

## computedStyleMap()

With the CSS Typed OM API, we can access all the CSS properties and values — including custom properties — that are impacting an element. Let's see how this works by creating our first example, which explores [`computedStyleMap()`](../element/computedstylemap).

We start with some HTML: a paragraph with a link, as well as a definition list to which we will add all the CSS Property / Value pairs.

    <p>
       <a href="https://example.com">Link</a>
    </p>
    <dl id="regurgitation"></dl>

We add JavaScript to grab our unstyled link and return back a definition list of all the default CSS property values impacting the link using `computedStyleMap()`.

    // get the element
    const myElement = document.querySelector('a');

    // get the <dl> we'll be populating
    const stylesList = document.querySelector('#regurgitation');

    // Retrieve all computed styles with computedStyleMap()
    const defaultComputedStyles = myElement.computedStyleMap();

    // iterate thru the map of all the properties and values, adding a <dt> and <dd> for each
    for (const [prop, val] of defaultComputedStyles) {
        // properties
        const cssProperty = document.createElement('dt');
        cssProperty.appendChild(document.createTextNode(prop));
        stylesList.appendChild(cssProperty);

        // values
        const cssValue = document.createElement('dd');
        cssValue.appendChild(document.createTextNode(val));
        stylesList.appendChild(cssValue);
    }

The `computedStyleMap()` method returns a [`StylePropertyMapReadOnly`](../stylepropertymapreadonly) object containing the `size` property, which indicates how many properties are in the map. We iterate through the style map, creating a `<dt>` and `<dd>` for each property and value respectively.

In [browsers that support `computedStyleMap()`](../element/computedstylemap#browser_compatibility), you'll see a list of all the CSS properties and values. In other browsers, you'll just see a link.

Did you realize how many default CSS properties a link had? Update the JavaScript on line 2 to select the [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) rather than the [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a). You'll notice a difference in the `margin-top` and `margin-bottom` default computed values.

### .get() method / custom properties

Let's update our example to only retrieve a few properties and values. Let's start by adding some CSS to our example, including a custom property and an inheritable property:

    p {
      font-weight: bold;
    }

    a {
      --color: red;
      color: var(--color);
    }

Instead of getting _all_ the properties, we create an array of properties of interest and use the [`StylePropertyMapReadOnly.get()`](../stylepropertymapreadonly/get) method to get each of their values:

    // get the element
    const myElement = document.querySelector('a');

    // get the <dl> we'll be populating
    const stylesList = document.querySelector('#regurgitation');

    // Retrieve all computed styles with computedStyleMap()
    const allComputedStyles = myElement.computedStyleMap();

    // array of properties we're interested in
    const ofInterest = ['font-weight', 'border-left-color', 'color', '--color'];

    // iterate through our properties of interest
    for ( let i = 0; i < ofInterest.length; i++ ) {
        // properties
      const cssProperty = document.createElement('dt');
      cssProperty.appendChild(document.createTextNode(ofInterest[i]));
      stylesList.appendChild(cssProperty);
        // values
      const cssValue = document.createElement('dd');
      cssValue.appendChild(document.createTextNode( allComputedStyles.get(ofInterest[i])));
        stylesList.appendChild(cssValue);
    }

We included [`border-left-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-left-color) to demonstrate that, had we included all the properties, every value that defaults to `currentcolor` (including [`caret-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/caret-color), [`outline-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline-color), [`text-decoration-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-color), [`column-rule-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-color), etc.) would return `rgb(255, 0, 0)`. The link has inherited `font-weight: bold;` from the paragraph's styles, listing it as `font-weight: 700`. Custom properties, like our `--color: red` , are properties. As such, they are accessible via `get()`.

You'll note that custom properties retain the value as written in the stylesheet, whereas computed styles will be listed as the computed value — [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) was listed as an [`rgb()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value) value and the [`font-weight`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight) returned was `700` even though we use a [`named color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value) and the `bold` keyword.

### CSSUnitValue and CSSKeywordValue

The power of the CSS Typed OM is that values are separate from units; parsing and concatenating string values may become be a thing of the past. Every CSS property in a style map has a value. If the value is a keyword, the object returned is a `CSSKeywordValue`. If the value is numeric, a `CSSUnitValue` is returned.

`CSSKeywordValue` is a class that defines keywords like `inherit`, `initial`, `unset`, and other strings you don't quote, such as `auto` and `grid`. This subclass gives you a `value` property via [`cssKeywordValue.value`](../csskeywordvalue/value).

`CSSUnitValue` is returned if the value is a unit type. It is a class that defines numbers with units of measurement like `20px`, `40%`, `200ms`, or `7`. It is returned with two properties: a `value` and a `unit`. With this type we can access the numeric value — [`cssUnitValue.value`](../cssunitvalue/value) — and its unit — [`cssUnitValue.unit`](../cssunitvalue/unit).

Let's write a plain paragraph, apply no styles, and inspect a few of its CSS properties by returning a table with the unit and value:

    <p>
       This is a paragraph with some content. Open up this example in Codepen or
       JSFiddle, and change some features. Try adding some CSS, such as a width
       for this paragraph, or adding a CSS property to the ofInterest array.
    </p>
    <table id="regurgitation">
      <thead>
        <tr>
          <th>Property</th>
          <th>Value</th>
          <th>Unit</th>
        </tr>
    </table>

For each property of interest, we list the name of the property, use `.get(propertyName).value` to return the value, and, if the object returned by the `get()` is a `CSSUnitValue`, list the unit type we retrieve with `.get(propertyName).unit`.

    // get the element we're inspecting
    const myElement = document.querySelector('p');

    // get the table we'll be populating
    const stylesTable = document.querySelector('#regurgitation');

    // Retrieve all computed styles with computedStyleMap()
    const allComputedStyles = myElement.computedStyleMap();

    // array of properties we're interested in
    const ofInterest = ['padding-top', 'margin-bottom', 'font-size', 'font-stretch',
         'animation-duration', 'animation-iteration-count', 'width', 'height'];
    // iterate thru our properties of interest
    for ( let i = 0; i < ofInterest.length; i++ ) {
          // create a row
        const row = document.createElement( 'tr' );

          // add the name of the property
        const cssProperty = document.createElement( 'td' );
        cssProperty.appendChild( document.createTextNode( ofInterest[i] ) );
        row.appendChild( cssProperty );

          // and the unitless value
        const cssValue = document.createElement( 'td' );
          // shrink long floats to 1 decimal point
        let propVal = allComputedStyles.get( ofInterest[i] ).value;
        propVal = ( propVal % 1 ) ? propVal.toFixed( 1 ) : propVal;
        cssValue.appendChild(document.createTextNode( propVal ));
        row.appendChild( cssValue );

          // and the type of unit
        const cssUnit = document.createElement( 'td' );
        cssUnit.appendChild( document.createTextNode( allComputedStyles.get( ofInterest[i] ).unit ));
        row.appendChild( cssUnit );

        //add the row to the table
        stylesTable.appendChild( row );
    }

For those of you using a non-supporting browser, the above output should looks something like this:

<table><thead><tr class="header"><th>Property</th><th>Value</th><th>Unit</th></tr></thead><tbody><tr class="odd"><td>padding-top</td><td>0</td><td>px</td></tr><tr class="even"><td>margin-bottom</td><td>16</td><td>px</td></tr><tr class="odd"><td>font-size</td><td>16</td><td>px</td></tr><tr class="even"><td>font-stretch</td><td>100</td><td>percent</td></tr><tr class="odd"><td>animation-duration</td><td>0</td><td>s</td></tr><tr class="even"><td>animation-iteration-count</td><td>1</td><td>number</td></tr><tr class="odd"><td>width</td><td>auto</td><td>undefined</td></tr><tr class="even"><td>height</td><td>auto</td><td>undefined</td></tr></tbody></table>

You'll note the [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) unit returned is `px`, the [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) unit returned is `percent`, the [`<time>`](https://developer.mozilla.org/en-US/docs/Web/CSS/time) unit is `s` for 'seconds', and the unitless [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number) unit is `number`.

We didn't declare a [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) or a [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height) for the paragraph, both of which default to `auto` and therefore return a `CSSKeywordValue` instead of a `CSSUnitValue`. `CSSKeywordValue`s do not have a unit property, so in these cases our `get().unit` returns `undefined`.

Had the `width` or `height` been defined in a `<length>` or `<percent>`, the `CSSUnitValue` unit would have been `px` or `percent` respectively.

There are other types available:

- An `<image>` will return a [`CSSImageValue`](../cssimagevalue).
- A `<color>` would return a [`CSSStyleValue`](../cssstylevalue).
- A [`transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) returns a `CSSTransformValue`.
- A [custom property](https://developer.mozilla.org/en-US/docs/Web/CSS/--*) returns a [`CSSUnparsedValue`](../cssunparsedvalue).

You can use a `CSSUnitValue` or `CSSKeywordValue` to create other objects. For example, the parameters for a [`CSSPositionValue`](../csspositionvalue) is one to two `CSSUnitValues` or `CSSKeywordValues`, or one of each:

    let position = new CSSPositionValue(
        new CSSKeywordValue("center"),
        new CSSUnitValue(10, "px"));

## CSSStyleValue

The `CSSStyleValue` interface of the [CSS Typed Object Model API](../css_object_model#css_typed_object_model) is the base class of all CSS values accessible through the Typed OM API, including [`CSSImageValue`](../cssimagevalue), [`CSSKeywordValue`](../csskeywordvalue), [`CSSNumericValue`](../cssnumericvalue), [`CSSPositionValue`](../csspositionvalue), [`CSSTransformValue`](../csstransformvalue), and [`CSSUnparsedValue`](../cssunparsedvalue).

It has two methods:

- [`CSSStyleValue.parse()`](../cssstylevalue/parse)
- [`CSSStyleValue.parseAll()`](../cssstylevalue/parseall)

As noted above, `StylePropertyMapReadOnly.get('--customProperty')` returns a [`CSSUnparsedValue`](../cssunparsedvalue). We can parse `CSSUnparsedValue` object instances with the inherited [`CSSStyleValue.parse()`](../cssstylevalue/parse) and [`CSSStyleValue.parseAll()`](../cssstylevalue/parseall) methods.

Let's examine a CSS example with several custom properties, transforms, `calc()`s, and other features. We'll take a look at that their types are by employing short JavaScript snippets outputting to [`console.log()`](../console/log):

    :root {
        --mainColor: hsl(198, 43%, 42%);
        --black: hsl(0, 0%, 16%);
        --white: hsl(0,0%,97%);
        --unit: 1.2rem;
    }

    button {
        --mainColor: hsl(198, 100%, 66%);
        display: inline-block;
        padding: var(--unit) calc(var(--unit)*2);
        width: calc(30% + 20px);
        background: no-repeat 5% center url(https://mdn.mozillademos.org/files/16793/magicwand.png) var(--mainColor);
        border: 4px solid var(--mainColor);
        border-radius: 2px;
        font-size: calc(var(--unit)*2); color: var(--white);
        cursor: pointer;
        transform: scale(0.95);
    }

Let's add the class to a button (a button which does nothing).

    <button>Styled Button</button>

We've created a blue button with a magic wand background image.

We grab our `StylePropertyMapReadOnly` with the following JavaScript:

    const allComputedStyles = document.querySelector('button').computedStyleMap();

The following examples reference `allComputedStyles`:

### CSSUnparsedValue

The [`CSSUnparsedValue`](../cssunparsedvalue) represents [custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties):

    // CSSUnparsedValue
    let unit = allComputedStyles.get('--unit');

    console.log( unit )    // CSSUnparsedValue {0: " 1.2rem", length: 1}
    console.log (unit[0] ) // " 1.2rem"

When we invoke `get()`, a custom property of type `CSSUnparsedValue` is returned. Note the space before the ` 1.2rem`. To get a unit and value, we need a `CSSUnitValue`, which we can retrieve using the `CSSStyleValue.parse()` method on the `CSSUnparsedValue`.

    let parsedUnit = CSSNumericValue.parse( unit );
    console.log( parsedUnit );        // CSSUnitValue {value: 1.2, unit: "rem"}
    console.log( parsedUnit.unit );   // "rem"
    console.log( parsedUnit.value );  // 1.2

### CSSMathSum

Although the `<button>` element is an inline element by default, we've added `display: inline-block;` to enable sizing. In our CSS we have `width: calc(30% + 20px);`, which is a `calc()` function to define the width.

When we `get()` the `width`, we get a `CSSMathSum` returned. [`CSSMathSum.values`](../cssmathsum/values) is a [`CSSNumericArray`](../cssnumericarray) with 2 `CSSUnitValues`.

The value of [`CSSMathValue.operator`](../cssmathvalue/operator) is `sum`:

    let btnWidth = allComputedStyles.get('width')

    console.log( btnWidth );             // CSSMathSum
    console.log( btnWidth.values );      // CSSNumericArray {0: CSSUnitValue, 1: CSSUnitValue, length: 2}
    console.log( btnWidth.operator );    // 'sum'

### CSSTransformValue with CSSScale

The `display: inline-block;` also enables transforming. In our CSS we have `transform: scale(0.95);`, which is a [`transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) function.

    let transform = allComputedStyles.get('transform');

    console.log( transform );        // CSSTransformValue {0: CSSScale, 1: CSSTranslate, length: 2, is2D: true}
    console.log( transform.length ); // 1
    console.log( transform[0] );     // CSSScale {x: CSSUnitValue, y: CSSUnitValue, z: CSSUnitValue, is2D: true}
    console.log( transform[0].x );   // CSSUnitValue {value: 0.95, unit: "number"}
    console.log( transform[0].y );      // CSSUnitValue {value: 0.95, unit: "number"}
    console.log( transform[0].z );   // CSSUnitValue {value: 1, unit: "number"}
    console.log( transform.is2D );   // true

When we `get()` the `transform` property, we get a [`CSSTransformValue`](../csstransformvalue). We can query the length (or number) of transform functions with the .`length` property.

Seen as we have a length of `1`, which represents a single transform function, we log the first object and get a `CSSScale` object. We get `CSSUnitValues` when we query the `x`, `y`, and `z` scaling. The readonly `CSSScale.is2D` property is `true` in this scenario.

Had we added `translate()`, `skew()`, and `rotate()` transform functions, the length would have been `4`, each with their own `x`, `y`, `z` values, and each with an `.is2D` property. For example, had we included `transform: translate3d(1px, 1px, 3px)`, the `.get('transform')` would have returned a `CSSTranslate` with `CSSUnitValues` for `x`, `y`, and `z`, and the readonly .i`s2D` property would have been `false`.

### CSSImageValue

Our button has one background image: a magic wand.

    let bgImage = allComputedStyles.get('background-image');

    console.log( bgImage );             // CSSImageValue
    console.log( bgImage.toString() );  // url("https://mdn.mozillademos.org/files/16793/magicwand.png")

When we `get()` the `'background-image'`, a [`CSSImageValue`](../cssimagevalue) is returned. While we used the CSS [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background) shorthand property, the inherited <span class="page-not-created">`Object.prototype.toString()`</span> method, shows we returned only the image, '`url("https://mdn.mozillademos.org/files/16793/magicwand.png")'`.

Notice that the value returned is the absolute path to the image — this is returned even if the original `url()` value was relative. Had the background image been a gradient or multiple background images, `.get('background-image') `would have returned a `CSSStyleValue`. The `CSSImageValue` is returned only if there is a single image, and only if that single image declaration is a URL.

### Summary

This should get you started with understanding the CSS Typed OM. Take a look at all the [CSS Typed OM](guide) interfaces to learn more.

## See also

- [Using the CSS Painting API](../css_painting_api/guide)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSS_Typed_OM_API/Guide" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSS_Typed_OM_API/Guide</a>
