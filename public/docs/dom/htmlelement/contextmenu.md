# HTMLElement.contextMenu

BCD tables only load in the browser

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `HTMLElement.contextMenu` property refers to the context menu assigned to an element using the [`contextmenu`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-contextmenu) attribute. The menu itself is created using the [`<menu>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/menu) element.

    var elementContextMenu = element.contextMenu;

    var contextMenu = document.getElementById("element").contextMenu;

    // Change the label of the first menu entry
    contextMenu.firstElementChild.label = "New label";

- [`contextmenu`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-contextmenu)
- [`<menu>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/menu)
- [`<menuitem>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/menuitem)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/contextMenu" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/contextMenu</a>
