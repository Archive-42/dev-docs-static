itemscope
=========

`itemscope` is a boolean [global attribute](../global_attributes) that defines the scope of associated metadata. Specifying the `itemscope` attribute for an element creates a new item, which results in a number of name-value pairs that are associated with the element. A related attribute, [`itemtype`](../global_attributes#attr-itemtype), is used to specify the valid URL of a vocabulary (such as [schema.org](https://schema.org/)) that describes the item and its properties context. In each of the following examples, the vocabulary is from [schema.org](https://schema.org/).

Every HTML element may have an `itemscope` attribute specified. An `itemscope` element that does not have an associated `itemtype` must have an associated `itemref`.

**Note:** Find more about `itemtype` attributes at [http://schema.org/Thing](https://schema.org/Thing)

### Simple example

#### HTML

The following example specifies the `itemscope` attribute. The example specifies the `itemtype` as "http://schema.org/Movie", and specifies three related `itemprop` attributes.

    <div itemscope itemtype="http://schema.org/Movie">
      <h1 itemprop="name">Avatar</h1>
      <span>Director: <span itemprop="director">James Cameron</span> (born August 16, 1954)</span>
      <span itemprop="genre">Science fiction</span>
      <a href="https://youtu.be/0AY1XIkX7bY" itemprop="trailer">Trailer</a>
    </div>

#### Structured data

The following table shows the structured data from the preceding example.

itemscope

Itemtype

Movie

itemprop

(itemprop name)

(itemprop value)

itemprop

director

James Cameron

itemprop

genre

Science Fiction

itemprop

name

Avatar

itemprop

https://youtu.be/0AY1XIkX7bY

Trailer

### itemscope id attributes

When you specify the `itemscope` attribute for an element, a new item is created. The item consists of a group of name-value pairs. For elements with an `itemscope` attribute and an `itemtype` attribute, you may also specify an [`id`](../global_attributes#attr-id) attribute. You can use the `id` attribute to set a global identifier for the new item. A global identifier allows the item to relate to other items found on pages across the Web.

### Example

There are four `itemscope` attributes in the following example. Each `itemscope` attribute sets the scope of its corresponding `itemtype` attribute. The `itemtype`s, `Recipe`, `AggregateRating`, and `NutritionInformation` in the following example are part of the [schema.org](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/www.schema.org) structured data for a recipe, as specified by the first `itemtype`, http://schema.org/Recipe.

    <div itemscope itemtype="http://schema.org/Recipe">
      <h2 itemprop="name">Grandma's Holiday Apple Pie</h2>
      <img itemprop="image" src="https://c1.staticflickr.com/1/30/42759561_8631e2f905_n.jpg" width="50" height="50" />
      <p>
        By <span itemprop="author" itemscope itemtype="http://schema.org/Person">
          <span itemprop="name">Carol Smith</span>
        </span>
      </p>
      <p>
        Published: <time datetime="2009-11-05" itemprop="datePublished">November 5, 2009</time>
      </p>
      <span itemprop="description">This is my grandmother's apple pie recipe. I like to add a dash of nutmeg.</span>
      <br>
      <span itemprop="aggregateRating" itemscope itemtype="http://schema.org/AggregateRating">
        <span itemprop="ratingValue">4.0</span> stars based on <span itemprop="reviewCount">35</span> reviews
      </span>
      <br>
      Prep time: <time datetime="PT30M" itemprop="prepTime">30 min</time><br>
      Cook time: <time datetime="PT1H" itemprop="cookTime">1 hou</time>r<br>
      Total time: <time datetime="PT1H30M" itemprop="totalTime">1 hour 30 min</time><br>
      Yield: <span itemprop="recipeYield">1 9" pie (8 servings)</span><br>
      <span itemprop="nutrition" itemscope itemtype="http://schema.org/NutritionInformation">
        Serving size: <span itemprop="servingSize">1 medium slice</span><br>
        Calories per serving: <span itemprop="calories">250 cal</span><br>
        Fat per serving: <span itemprop="fatContent">12 g</span><br>
      </span>
      <p>
        Ingredients:<br>
        <span itemprop="recipeIngredient">Thinly-sliced apples: 6 cups<br></span>
        <span itemprop="recipeIngredient">White sugar: 3/4 cup<br></span>
        ...
      </p>
      Directions: <br>
      <div itemprop="recipeInstructions">
        1. Cut and peel apples<br>
        2. Mix sugar and cinnamon. Use additional sugar for tart apples. <br>
        ...
      </div>
    </div>

### Results

#### HTML

The following is an example rendering of the preceding code example.

#### Structured data

itemscope

itemtype

Recipe

itemprop

name

Grandma's Holiday Apple Pie

itemprop

image

https://c1.staticflickr.com/1/30/42759561\_8631e2f905\_n.jpg

itemprop

datePublished

2009-11-05

itemprop

description

This is my grandmother's apple pie recipe. I like to add a dash of nutmeg.

itemprop

prepTime

PT30M

itemprop

cookTime

PT1H

itemprop

totalTime

PT1H30M

itemprop

recipeYield

1 9" pie (8 servings)

itemprop

recipeIngredient

Thinly-sliced apples: 6 cups

itemprop

recipeIngredient

White sugar: 3/4 cup

itemprop

recipeInstructions

1. Cut and peel apples 2. Mix sugar and cinnamon. Use additional sugar for tart apples .

itemprop

author \[Person\]

itemprop

name

Carol Smith

itemscope

itemprop\[itemtype\]

aggregateRating \[AggregateRating\]

itemprop

ratingValue

4.0

itemprop

reviewCount

35

itemscope

itemprop\[itemtype\]

nutrition \[NutritionInformation\]

itemprop

servingSize

1 medium slice

itemprop

calories

250 cal

itemprop

fatContent

12 g

**Note**: A handy tool for extracting microdata structures from HTML is Google's [Rich Results Testing Tool](https://search.google.com/test/rich-results). Try it on the HTML shown above.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/microdata.html#attr-itemscope">HTML Living Standard<br />
<span class="small">The definition of 'itemscope' in that specification.</span></a></td></tr></tbody></table>

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

`itemscope`

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
    -   [`itemtype`](../global_attributes#attr-itemtype)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/itemscope" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/itemscope</a>
