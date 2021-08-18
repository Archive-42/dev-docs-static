# Privacy and the :visited selector

Before about 2010, the [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [`:visited`](:visited) selector allowed websites to uncover a user's browsing history and figure out what sites the user had visited. This was done through [`window.getComputedStyle`](https://developer.mozilla.org/en-US/docs/Web/API/Window/getComputedStyle) and other techniques. This process was quick to execute, and made it possible not only to determine where the user had been on the web, but could also be used to guess a lot of information about the user's identity.

To mitigate this problem, browsers have limited the amount of information that can be obtained from visited links.

## Little white lies

To preserve users' privacy, Firefox and other browsers will lie to web applications under certain circumstances:

- The `window.getComputedStyle` method, and similar functions such as [`element.querySelector`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelector), will always return values indicating that a user has never visited any of the links on a page.
- If you use a sibling selector such as `:visited + span`, the adjacent element (`span` in this example) will be styled as if the link were unvisited.
- In rare scenarios, if you're using nested link elements and the element being matched is different from the link whose presence in history is being tested, the element will be rendered as if the link were unvisited, as well.

## Limits to visited link styles

You can style visited links, but there are limits to which styles you can use. Only the following styles can be applied to visited links:

- [`color`](color)
- [`background-color`](background-color)
- [`border-color`](border-color) (and its sub-properties)
- [`column-rule-color`](column-rule-color)
- [`outline-color`](outline-color)
- The color parts of the `fill` and `stroke` attributes

In addition, even for the above styles, you won't be able to change the transparency between unvisited and visited links, as you otherwise would be able to using `rgba()`, `hsla()`, or the `transparent` keyword.

Here is an example of how to use styles with the aforementioned restrictions:

    :link {
      outline: 1px dotted blue;
      background-color: white;
      /* The default value of background-color is `transparent`. You need to
         specify a different value, otherwise changes on :visited won't apply. */
    }

    :visited {
      outline-color: orange;    /* Visited links have an orange outline */
      background-color: green;  /* Visited links have a green background */
      color: yellow;            /* Visited links have yellow colored text */
    }

## Impact on web developers

Overall, these restrictions shouldn't affect web developers too significantly. They may, however, require the following changes to existing sites:

- Using background images to style links based on whether they've been visited will no longer work, since only colors can be used to style visited links.
- Colors that are otherwise transparent will fail to appear if styled in a `:visited` selector.

## See also

- [privacy-related changes coming to CSS :visited](https://hacks.mozilla.org/2010/03/privacy-related-changes-coming-to-css-vistited/) on Mozilla Hacks
- [Plugging the CSS History Leak](https://blog.mozilla.com/security/2010/03/31/plugging-the-css-history-leak/) on the Mozilla Security Blog
- [Preventing attacks on a user's history through CSS :visited selectors](https://dbaron.org/mozilla/visited-privacy)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Privacy_and_the_:visited_selector" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Privacy*and_the*:visited_selector</a>
