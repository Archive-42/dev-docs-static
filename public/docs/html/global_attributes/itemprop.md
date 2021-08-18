itemprop
========

The `itemprop` [global attribute](../global_attributes) is used to add properties to an item. Every HTML element can have an `itemprop` attribute specified, and an `itemprop` consists of a name-value pair. Each name-value pair is called a **property**, and a group of one or more properties forms an **item**. Property values are either a string or a URL and can be associated with a very wide range of elements including [`<audio>`](../element/audio), [`<embed>`](../element/embed), [`<iframe>`](../element/iframe), [`<img>`](../element/img), [`<link>`](../element/link), [`<object>`](../element/object), [`<source>`](../element/source) , [`<track>`](../element/track), and [`<video>`](../element/video).

Examples
--------

The example below shows the source for a set of elements marked up with `itemprop` attributes, followed by a table showing the resulting structured data.

### HTML

    <div itemscope itemtype="http://schema.org/Movie">
      <h1 itemprop="name">Avatar</h1>
      <span>Director:
        <span itemprop="director">James Cameron</span>
        (born August 16, 1954)</span>
      <span itemprop="genre">Science fiction</span>
      <a href="../movies/avatar-theatrical-trailer.html"
        itemprop="trailer">Trailer</a>
    </div>

### Structured data

**Item**

**itemprop name**

**itemprop value**

itemprop

name

Avatar

itemprop

director

James Cameron

itemprop

genre

Science fiction

itemprop

trailer

../movies/avatar-theatrical-trailer.html

Properties
----------

Properties have values that are either a string or a URL. When a string value is a URL, it is expressed using the [`<a>`](../element/a) element and its [`href`](../element/a#attr-href) attribute, the [`<img>`](../element/img) element and its [`src`](../element/img#attr-src) attribute, or other elements that link to or embed external resources.

### Three properties with values that are strings

    <div itemscope>
     <p>My name is
       <span itemprop="name">Neil</span>.</p>
     <p>My band is called
       <span itemprop="band">Four Parts Water</span>.</p>
     <p>I am
       <span itemprop="nationality">British</span>.</p>
    </div>

### One property, "image", whose value is a URL

    <div itemscope>
     <img itemprop="image"
       src="google-logo.png" alt="Google">
    </div>

When a string value can't be easily read and understood by a person (e.g., a long string of numbers and letters), it can be displayed using the value attribute of the data element, with the more easily-understood-by-a human-version given in the element's contents (which is not part of the structured data - see example below).

### An item with a property whose value is a product ID

The ID is not human-friendly, so the product's name is used the human-visible text instead of the ID.

    <h1 itemscope>
     <data itemprop="product-id"
       value="9678AOU879">The Instigator 2000</data>
    </h1>

For numeric data, the meter element and its value attribute can be used.

### A meter element

    <div itemscope itemtype="http://schema.org/Product">
     <span itemprop="name">Panasonic White
       60L Refrigerator</span>
     <img src="panasonic-fridge-60l-white.jpg" alt="">
      <div itemprop="aggregateRating"
           itemscope
           itemtype="http://schema.org/AggregateRating">
       <meter itemprop="ratingValue"
         min=0 value=3.5 max=5>Rated 3.5/5</meter>
       (based on <span
         itemprop="reviewCount">11</span>
         customer reviews)
      </div>
    </div>

Similarly, for date- and time-related data, the time element and its datetime attribute can be used.

### An item with one property, "birthday", whose value is a date

    <div itemscope>
     I was born on <time
       itemprop="birthday"
       datetime="2009-05-10">May 10th 2009</time>.
    </div>

Properties can also be groups of name-value pairs, by putting the itemscope attribute on the element that declares the property. Each value is either a string or a group of name-value pairs (i.e. an item).

### An outer item representing a person, and an inner one representing a band

    <div itemscope>
     <p>Name:
       <span itemprop="name">Amanda</span></p>
     <p>Band:
       <span itemprop="band" itemscope>
         <span itemprop="name">Jazz Band</span>
         (<span itemprop="size">12</span>
         players)</span></p>
    </div>

The outer item above has two properties, "name" and "band". The "name" is "Amanda", and the "band" is an item in its own right, with two properties, "name" and "size". The "name" of the band is "Jazz Band", and the "size" is "12". The outer item in this example is a top-level microdata item. Items that are not part of others are called top-level microdata items.

### All the properties separated from their items

This example is the same as the previous one, but all the properties are separated from their items

    <div itemscope id="amanda" itemref="a b"></div>
    <p id="a">Name:
      <span itemprop="name">Amanda</span></p>
    <div id="b"
      itemprop="band"
      itemscope itemref="c"></div>
    <div id="c">
     <p>Band:
       <span itemprop="name">Jazz Band</span></p>
     <p>Size:
       <span itemprop="size">12</span> players</p>
    </div>

This gives the same result as the previous example. The first item has two properties, "name", set to "Amanda", and "band", set to another item. That second item has two further properties, "name", set to "Jazz Band", and "size", set to "12".

An item can have multiple properties with the same name and different values.

### Ice cream with two flavors

    <div itemscope>
     <p>Flavors in my favorite ice cream:</p>
     <ul>
      <li itemprop="flavor">Lemon sorbet</li>
      <li itemprop="flavor">Apricot sorbet</li>
     </ul>
    </div>

This results in an item with two properties, both with the name "flavor" and having the values "Lemon sorbet" and "Apricot sorbet".

An element introducing a property can also introduce multiple properties at once, to avoid duplication when some of the properties have the same value.

### An item with two properties, "favorite-color" and "favorite-fruit", both set to the value "orange"

    <div itemscope>
     <span
      itemprop="favorite-color
        favorite-fruit">orange</span>
    </div>

Note: There is no relationship between the microdata and the content of the document where the microdata is marked up.

### Same structured data marked up in two different ways

There is no semantic difference between the following two examples

    <figure>
     <img src="castle.jpeg">
     <figcaption><span
       itemscope><span
       itemprop="name">The Castle</span></span>
         (1986)</figcaption>
    </figure>

    <span itemscope><meta
      itemprop="name"
      content="The Castle"></span>
    <figure>
     <img src="castle.jpeg">
     <figcaption>The Castle
      (1986)</figcaption>
    </figure>

Both have a figure with a caption, and both, completely unrelated to the figure, have an item with a name-value pair with the name "name" and the value "The Castle". The only difference is that if the user drags the figcaption out of the document, the item will be included in the drag-and-drop data. The image associated with the item won't be included.

Names and values
----------------

A property is an unordered set of unique tokens that are case-sensitive and represent the name-value pairs. The property value must have at least one token. In the example below, each data cell is a token.

### Names examples

Item

itemprop **name**

itemprop **value**

itemprop

country

Ireland

itemprop

Option

2

itemprop

https://www.flickr.com/photos/nlireland/6992065114/

Ring of Kerry

itemprop

img

https://www.flickr.com/photos/nlireland/6992065114/

itemprop

website

flickr

itemprop

(token)

(token)

**Tokens** are either strings or URL's. An item is called a **typed item** if it is a URL. Otherwise, it is a string. Strings cannot contain a period or a colon (see below).

1.  If the item is a typed item it must be either:
    1.  A defined property name, or
    2.  A valid URL, which refers to the vocabulary definition, or
    3.  A valid URL that is used as a proprietary item property name (i.e. one not defined in a public specification), or
2.  If the item is not a typed item it must be:
    1.  A string that contains no "`.`" (U+002E FULL STOP) characters and no "`:`" characters (U+003A COLON) and is used as a proprietary item property name (again, one not defined in a public specification).

**Note:** the rules above disallow ":" characters in non-URL values because otherwise they could not be distinguished from URLs. Values with "." characters are reserved for future extensions. Space characters are disallowed because otherwise the values would be parsed as multiple tokens.

Values
------

The property value of a name-value pair is as given for the first matching case in the following list:

-   If the element has an `itemscope` attribute
    -   The value is the **item** created by the element.
-   If the element is a `meta` element
    -   The value is the value of the element's `content` attribute
-   If the element is an `audio`, `embed`, `iframe`, `img`, `source`, `track`, or `video` element
    -   The value is the resulting URL string that results from parsing the value of the element's src attribute relative to the node document (part of the [Microdata DOM API](https://developer.mozilla.org/en-US/docs/Web/API/Microdata_DOM_API)) of the element at the time the attribute is set
-   If the element is an `a`, `area`, or `link` element
    -   The value is the resulting URL string that results from parsing the value of the element's href attribute relative to the node document of the element at the time the attribute is set
-   If the element is an `object` element
    -   The value is the resulting URL string that results from parsing the value of the element's data attribute relative to the node document of the element at the time the attribute is set
-   If the element is a `data` element
    -   The value is the value of the element's value attribute
-   If the element is a `meter` element
    -   The value is the value of the element's `value` attribute
-   If the element is a `time` element
    -   The value is the element's `datetime` value

Otherwise

-   The value is the element's textContent.

If a property's value is a `URL`, the property must be specified using a URL property element. The URL property elements are the `a`, `area`, `audio`, `embed`, `iframe`, `img`, `link`, `object`, `source`, `track`, and `video` elements.

### Name order

Names are unordered relative to each other, but if a particular name has multiple values, they do have a relative order.

In the following example, the "a" property has the values "1" and "2", *in that order*, but whether the "a" property comes before the "b" property or not is not important

    <div itemscope>
     <p itemprop="a">1</p>
     <p itemprop="a">2</p>
     <p itemprop="b">test</p>
    </div>

The following is equivalent

    <div itemscope>
     <p itemprop="b">test</p>
     <p itemprop="a">1</p>
     <p itemprop="a">2</p>
    </div>

As is the following

    <div itemscope>
     <p itemprop="a">1</p>
     <p itemprop="b">test</p>
     <p itemprop="a">2</p>
    </div>

And the following

    <div id="x">
     <p itemprop="a">1</p>
    </div>
    <div itemscope itemref="x">
     <p itemprop="b">test</p>
     <p itemprop="a">2</p>
    </div>

Other examples
--------------

### HTML

    <dl itemscope
      itemtype="http://vocab.example.net/book"
      itemid="urn:isbn:0-330-34032-8">
     <dt>Title
       <dd
        itemprop="title">The Reality Dysfunction
     <dt>Author
       <dd
         itemprop="author">Peter F. Hamilton
     <dt>Publication date
     <dd><time
       itemprop="pubdate"
       datetime="1996-01-26">26 January 1996</time>
    </dl>

### Structured data

itemscope

itemtype: itemid

http://vocab.example.net/book: urn:isbn:0-330-34032-8

itemprop

title

The Reality Dysfunction

itemprop

author

Peter F. Hamilton

itemprop

pubdate

1996-01-26

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/microdata.html#names:-the-itemprop-attribute">HTML Living Standard<br />
<span class="small">The definition of 'itemprop' in that specification.</span></a></td></tr></tbody></table>

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

`itemprop`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [Other different global attributes](../global_attributes)
-   Other, microdata related, global attributes:
    -   [`itemid`](../global_attributes#attr-itemid)
    -   [`itemprop`](../global_attributes#attr-itemprop)
    -   [`itemref`](../global_attributes#attr-itemref)
    -   [`itemscope`](../global_attributes#attr-itemscope)
    -   [`itemtype`](../global_attributes#attr-itemtype)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/itemprop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/itemprop</a>
