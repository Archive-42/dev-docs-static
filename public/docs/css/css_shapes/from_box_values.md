# Shapes from box values

A straightforward way to create a shape is to use a value from the CSS Box Model. This article explains how to do this.

The [box values](https://drafts.csswg.org/css-shapes-1/#shapes-from-box-values) allowable as a shape value are:

- `content-box`
- `padding-box`
- `border-box`
- `margin-box`

The `border-radius` values are also supported, this means that you can have something in your page with a curved border, and your shape can follow the created shape.

## CSS box model

The values listed above correspond to the various parts of the CSS Box Model. A box in CSS has content, padding, border, and margin.

<img src="data:image/png;base64,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" alt="The Box Model consists of the margin, border, padding and content boxes." width="447" height="267" />

By using Box Values for Shapes we can wrap our content around the edges defined by these values. In all of the examples below I am using an element which has padding, a border, and a margin defined in order that you can see the different ways in which content will flow.

### margin-box

The `margin-box` is the shape defined by the outside margin edge and includes the corner radius of the shape, should [`border-radius`](../border-radius) have been used in defining the element.

In the example below, we have a circular purple item which is a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) with a height, width, and background color. The `border-radius` property has been used to create a circle by setting `border-radius: 50%`. As the element has a margin, you can see that the content is flowing around the circular shape and the margin applied to it.

### border-box

The `border-box` value is the shape defined by the outside border edge. This shape follows all of the normal border radius shaping rules for the outside of the border. You still have a border, even if you have not used the CSS [`border`](../border) property. In this case it will be the same as `padding-box`, the shape defined by the outside padding edge.

In the example below you can see how the text now follows the line created by the border. Change the border size and the content follows it.

### padding-box

The `padding-box` value defines the shape enclosed by the outside padding edge. This shape follows all of the normal border radius shaping rules for the inside of the border. If you have no padding then `padding-box` is the same as `content-box`.

### content-box

The `content-box` value defines the shape enclosed by the outside content edge. Each corner radius of this box is the larger of 0 or border-radius − border-width − padding. This Means that it is impossible to have a negative value here.

## When to use the box values

Using box values is a simple way to create shapes, however this is by nature only going to work with very simple shapes that can be defined using the well-supported `border-radius` property. The examples shown above show one such use case. You can create a circular shape using border-radius and then curve text around it.

You can create some interesting effects however with just this simple technique. In my final example of this section, I have floated two elements left and right, giving each a border-radius of 100% in the direction closest to the text.

For more complex shapes you will need to use one of the [basic shapes](basic_shapes) as a value, or define your Shape from an image as covered in other guides in this section.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Shapes/From_box_values" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Shapes/From_box_values</a>
