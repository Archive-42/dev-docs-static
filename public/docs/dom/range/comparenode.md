Range.compareNode()
===================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `Range.compareNode()` returns a constant indicating the position of the [`Node`](../node).

The possible values are:

 `NODE_BEFORE` (`0`)  
Node starts before the Range

 `NODE_AFTER` (`1`)  
Node ends after the Range

 `NODE_BEFORE_AND_AFTER` (`2`)  
Node starts before and ends after the Range

 `NODE_INSIDE` (`3`)  
Node starts after and ends before the Range, i.e. the Node is completely selected by the Range.

**Warning:** This method [has been removed](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Releases/3/Site_compatibility) from [Gecko 1.9](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Releases/3) and will not exist in future versions of Firefox, which was the only browser implementing it; you should switch to [`Range.compareBoundaryPoints()`](compareboundarypoints) as soon as possible.

The following function can be used as replacement:

    function rangeCompareNode(range, node) {
      var nodeRange = node.ownerDocument.createRange();
      try {
        nodeRange.selectNode(node);
      }
      catch (e) {
        nodeRange.selectNodeContents(node);
      }
      var nodeIsBefore = range.compareBoundaryPoints(Range.START_TO_START, nodeRange) == 1;
      var nodeIsAfter = range.compareBoundaryPoints(Range.END_TO_END, nodeRange) == -1;

      if (nodeIsBefore && !nodeIsAfter)
        return 0;
      if (!nodeIsBefore && nodeIsAfter)
        return 1;
      if (nodeIsBefore && nodeIsAfter)
        return 2;

      return 3;
    }

Syntax
------

    returnValue = range.compareNode( referenceNode );

### Parameters

*referenceNode*  
The [`Node`](../node) to compare with the `Range`.

Example
-------

    range = document.createRange();
    range.selectNode(document.getElementsByTagName("div").item(0));
    returnValue = range.compareNode(document.getElementsByTagName("p").item(0));

Notes
-----

This method is obsolete; you should use the W3C DOM [`Range.compareBoundaryPoints()`](compareboundarypoints) method.

Specifications
--------------

This method is not standard and therefore not part of any specification.

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

`compareNode`

1-45

No

1-3

No

15-32

3

1-45

18-45

No

14-32

1

1.0-5.0

See also
--------

-   [The DOM interfaces index](../document_object_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/compareNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/compareNode</a>
