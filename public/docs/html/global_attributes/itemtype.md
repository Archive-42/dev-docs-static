itemtype
========

The [global attribute](../global_attributes)`itemtype` specifies the URL of the vocabulary that will be used to define `itemprop`'s (item properties) in the data structure. [`itemscope`](../global_attributes#attr-itemscope) is used to set the scope of where in the data structure the vocabulary set by `itemtype` will be active.

Google and other major search engines support the [schema.org](https://schema.org/) vocabulary for structured data. This vocabulary defines a standard set of type names and property names. For example, `MusicEvent `indicates a concert performance, with `startDate` and `location` properties specifying the concert's key details. In this case, [`MusicEvent`](https://schema.org/MusicEvent) would be the URL used by `itemtype`, with `startDate` and location as `itemprop`'s which `MusicEvent` defines.

**Note:** More about `itemtype` attributes can be found at [http://schema.org/Thing](https://schema.org/Thing)

-   The **itemtype** attribute must have a value that is an unordered set of unique tokens which are case-sensitive, each is a valid and absolute URL, and all defined to use the same vocabulary. The attribute's value must have at least one token.
-   The item types must all be types defined in applicable specifications (such as [schema.org](https://schema.org/)), and must all be defined to use the same vocabulary.
-   The itemtype attribute can only be specified on elements which have an itemscope attribute specified.
-   The itemid attribute can only be specified on elements which have both an itemscope attribute and an itemtype attribute specified. They must only be specified on elements with an itemscope attribute, whose itemtype attribute specifies a vocabulary not supporting global identifiers for items, as defined by that vocabulary's specification.
-   The exact meaning of a global identifier is determined by the vocabulary's specification. It is left to such specifications to define whether multiple items of the same global identifier (whether on the same page or different pages) are allowed to exist, and what processing rules for that vocabulary are, with respect to handling the case of multiple items with the same ID.

### Simple example

#### HTML

    <div itemscope itemtype="http://schema.org/Product">
      <span itemprop="brand">ACME</span>
      <span itemprop="name">Executive Anvil</span>
    </div>

#### Structured data

itemscope

itemtype

schema.org Product

itemprop

name

Executive Anvil

itemprop

brand \[Thing\]

itemprop

name

ACME

Example
-------

### HTML

    <div itemscope itemtype="http://schema.org/Product">
      <span itemprop="brand">ACME<br></span>
      <span itemprop="name">Executive Anvil<br></span>
      <img itemprop="image" src="https://pixabay.com/static/uploads/photo/2015/09/05/18/15/suitcase-924605_960_720.png" width="50" height="50" alt="Executive Anvil logo" /><br>

    <span itemprop="description">Sleeker than ACME's Classic Anvil, the
        Executive Anvil is perfect for the business traveler
        looking for something to drop from a height.
      <br>
    </span>

      Product #: <span itemprop="mpn">925872<br></span>
      <span itemprop="aggregateRating" itemscope itemtype="http://schema.org/AggregateRating">
        Rating: <span itemprop="ratingValue">4.4</span> stars, based on <span itemprop="reviewCount">89
          </span> reviews
      </span><p>

    <span itemprop="offers" itemscope itemtype="http://schema.org/Offer">
        Regular price: $179.99<br>
        <meta itemprop="priceCurrency" content="USD" />
        <span itemprop="price">Sale price: $119.99<br></span>
        (Sale ends <time itemprop="priceValidUntil" datetime="2020-11-05">
          5 November!</time>)<br>
        Available from: <span itemprop="seller" itemscope itemtype="http://schema.org/Organization">
                          <span itemprop="name">Executive Objects<br></span>
                        </span>
        Condition: <link itemprop="itemCondition" href="http://schema.org/UsedCondition"/>Previously owned,
          in excellent condition<br>
        <link itemprop="availability" href="http://schema.org/InStock"/>In stock! Order now!
    </span>

    </div>

### Result

#### HTML

#### Structured data

itemscope

itemtype

Product (http://schema.org/Product)

itemprop

name

Executive Anvil

itemprop

image

https://pixabay.com/static/uploads/photo/2015/09/05/18/15/suitcase-924605\_960\_720.png

itemprop

description

Sleeker than ACME's Classic Anvil, the Executive Anvil is perfect for the business traveler looking for something to drop from a height.

itemprop

mpn

925872

itemprop

brand \[Thing\]

itemprop

name

ACME

itemscope

itemprop\[itemtype\]

aggregateRating\[AggregateRating\]

itemprop

ratingValue

4.4

itemprop

reviewCount

89

itemprop

offers \[Offer\]

http://schema.org/Offer

itemprop

priceCurrency

USD

itemprop

price

119.99

itemprop

priceValidUntil

2020-11-05

itemprop

itemCondition

http://schema.org/UsedCondition

itemprop

availability

http://schema.org/InStock

itemscope

itemprop\[itemtype\]

seller \[Organization\]

http://schema.org/Organization

itemprop

name

Executive Objects

**Note**: A handy tool for extracting microdata structures from HTML is Google's [Structured Data Testing Tool](https://developers.google.com/structured-data/testing-tool/). Try it on the HTML shown above

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/microdata.html#attr-itemtype">HTML Living Standard<br />
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

`itemtype`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/itemtype" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/itemtype</a>
