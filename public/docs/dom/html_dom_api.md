# The HTML DOM API

The **HTML DOM API** is made up of the interfaces that define the functionality of each of the [elements](https://developer.mozilla.org/en-US/docs/Glossary/Element) in [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML), as well as any supporting types and interfaces they rely upon.

The functional areas included in the HTML DOM API include:

- Access to and control of HTML elements via the [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM).
- Access to and manipulation of form data.
- Interacting with the contents of 2D images and the context of an HTML [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas), for example to draw on top of them.
- Management of media connected to the HTML media elements ([`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) and [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)).
- Dragging and dropping of content on webpages.
- Access to the browser navigation history
- Supporting and connective interfaces for other APIs such as [Web Components](https://developer.mozilla.org/en-US/docs/Web/Web_Components), [Web Storage](web_storage_api), [Web Workers](web_workers_api), [WebSocket](websockets_api), and [Server-sent events](server-sent_events).

## HTML DOM concepts and usage

In this article, we'll focus on the parts of the HTML DOM that involve engaging with HTML elements. Discussion of other areas, such as [Drag and Drop](html_drag_and_drop_api), [WebSockets](websockets_api), [Web Storage](web_storage_api), etc. can be found in the documentation for those APIs.

### Structure of an HTML document

The Document Object Model ([DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM)) is an architecture that describes the structure of a [`document`](document); each document is represented by an instance of the interface [`Document`](document). A document, in turn, consists of a hierarchical tree of **nodes**, in which a node is a fundamental record representing a single object within the document (such as an element or text node).

Nodes may be strictly organizational, providing a means for grouping other nodes together or for providing a point at which a hierarchy can be constructed; other nodes may represent visible components of a document. Each node is based on the [`Node`](node) interface, which provides properties for getting information about the node as well as methods for creating, deleting, and organizing nodes within the DOM.

Nodes don't have any concept of including the content that is actually displayed in the document. They're empty vessels. The fundamental notion of a node that can represent visual content is introduced by the [`Element`](element) interface. An `Element` object instance represents a single element in a document created using either HTML or an [XML](https://developer.mozilla.org/en-US/docs/Glossary/XML) vocabulary such as [SVG](https://developer.mozilla.org/en-US/docs/Glossary/SVG).

For example, consider a document with two elements, one of which has two more elements nested inside it:

<img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjExOS41IDI4MS41IDI5MSAzNzkiIHdpZHRoPSIyOTEiIGhlaWdodD0iMzc5Ij48ZyBmaWxsPSJub25lIj48cGF0aCBmaWxsPSIjZWRlZGZmIiBkPSJNMTIwIDI4MmgyOTB2Mzc4SDEyMHoiLz48cGF0aCBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZD0iTTEyMCAyODJoMjkwdjM3OEgxMjB6Ii8+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTI1IDI4NykiIGZpbGw9IiMwMDAiPjx0c3BhbiBmb250LWZhbWlseT0iQ291cmllciBOZXciIGZvbnQtc2l6ZT0iMTQiIGZvbnQtd2VpZ2h0PSI0MDAiIHg9IjAiIHk9IjEyIj5XaW5kb3c8L3RzcGFuPjwvdGV4dD48cGF0aCBmaWxsPSIjZmZjMGMwIiBkPSJNMTMwIDMxMmgyNjYuOTg0djMzOEgxMzB6Ii8+PHBhdGggc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIGQ9Ik0xMzAgMzEyaDI2Ni45ODR2MzM4SDEzMHoiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxMzUgMzE3KSIgZmlsbD0iIzAwMCI+PHRzcGFuIGZvbnQtZmFtaWx5PSJDb3VyaWVyIE5ldyIgZm9udC1zaXplPSIxNCIgZm9udC13ZWlnaHQ9IjQwMCIgeD0iMCIgeT0iMTIiPkRvY3VtZW50PC90c3Bhbj48L3RleHQ+PHBhdGggZmlsbD0iI2ZmZmZjMCIgZD0iTTE0My4wMTYgMzQwSDM5MHY4MEgxNDMuMDE2eiIvPjxwYXRoIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIiBkPSJNMTQzLjAxNiAzNDBIMzkwdjgwSDE0My4wMTZ6Ii8+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTQ4LjAxNiAzNDUpIiBmaWxsPSIjMDAwIj48dHNwYW4gZm9udC1mYW1pbHk9IkNvdXJpZXIgTmV3IiBmb250LXNpemU9IjE0IiBmb250LXdlaWdodD0iNDAwIiB4PSIwIiB5PSIxMiI+RWxlbWVudDwvdHNwYW4+PC90ZXh0PjxwYXRoIGZpbGw9IiNmZmZmYzAiIGQ9Ik0xNDMuMDE2IDQzMEgzOTB2MTMwSDE0My4wMTZ6Ii8+PHBhdGggc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIGQ9Ik0xNDMuMDE2IDQzMEgzOTB2MTMwSDE0My4wMTZ6Ii8+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTQ4LjAxNiA0MzUpIiBmaWxsPSIjMDAwIj48dHNwYW4gZm9udC1mYW1pbHk9IkNvdXJpZXIgTmV3IiBmb250LXNpemU9IjE0IiBmb250LXdlaWdodD0iNDAwIiB4PSIwIiB5PSIxMiI+RWxlbWVudDwvdHNwYW4+PC90ZXh0PjxwYXRoIGZpbGw9IiNjMGZmZmYiIGQ9Ik0xNTAgNDYwaDIzMHYzMEgxNTB6Ii8+PHBhdGggc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIGQ9Ik0xNTAgNDYwaDIzMHYzMEgxNTB6Ii8+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTU1IDQ2NSkiIGZpbGw9IiMwMDAiPjx0c3BhbiBmb250LWZhbWlseT0iQ291cmllciBOZXciIGZvbnQtc2l6ZT0iMTQiIGZvbnQtd2VpZ2h0PSI0MDAiIHg9IjAiIHk9IjEyIj5FbGVtZW50PC90c3Bhbj48L3RleHQ+PHBhdGggZmlsbD0iI2MwZmZmZiIgZD0iTTE1MCA1MDBoMjMwdjMwSDE1MHoiLz48cGF0aCBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZD0iTTE1MCA1MDBoMjMwdjMwSDE1MHoiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNTUgNTA1KSIgZmlsbD0iIzAwMCI+PHRzcGFuIGZvbnQtZmFtaWx5PSJDb3VyaWVyIE5ldyIgZm9udC1zaXplPSIxNCIgZm9udC13ZWlnaHQ9IjQwMCIgeD0iMCIgeT0iMTIiPkVsZW1lbnQ8L3RzcGFuPjwvdGV4dD48L2c+PC9zdmc+" alt="Structure of a document with elements inside a document in a window" width="291" height="379" />

While the [`Document`](document) interface is defined as part of the [DOM](document_object_model) specification, the HTML specification significantly enhances it to add information specific to using the DOM in the context of a web browser, as well as to using it to represent HTML documents specifically.

Among the things added to `Document` by the HTML standard are:

- Support for accessing various information provided by the [HTTP](https://developer.mozilla.org/en-US/docs/Glossary/HTTP) headers when loading the page, such as the [location](document/location) from which the document was loaded, [cookies](document/cookie), [modification date](document/lastmodified), [referring site](document/referrer), and so forth.
- Access to lists of elements in the document's [`<head>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head) block and [body](document/body), as well as lists of the [images](document/images), [links](document/links), [scripts](document/scripts), etc. contained in the document.
- Support for interacting with the user by examining [focus](document/hasfocus) and by executing commands on [editable content](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/contenteditable).
- Event handlers for document [events defined by the HTML standard](globaleventhandlers) to allow access to [mouse](mouseevent) and [keyboard](keyboardevent) events, [drag and drop](html_drag_and_drop_api), [media control](htmlmediaelement), and more.
- Event handlers for events that can be delivered to both elements and documents; these presently include only [copy](htmlelement/oncopy), [cut](htmlelement/oncut), and [paste](htmlelement/onpaste) actions.

### HTML element interfaces

The `Element` interface has been further adapted to represent HTML elements specifically by introducing the [`HTMLElement`](htmlelement) interface, which all more specific HTML element classes inherit from. This expands the `Element` class to add HTML-specific general features to the element nodes. Properties added by `HTMLElement` include for example [`hidden`](htmlelement/hidden) and [`innerText`](htmlelement/innertext). `HTMLElement` also adds all the [global event handlers](globaleventhandlers).

An [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML) document is a DOM tree in which each of the nodes is an HTML element, represented by the [`HTMLElement`](htmlelement) interface. The `HTMLElement` class, in turn, implements `Node`, so every element is also a node (but not the other way around). This way, the structural features implemented by the [`Node`](node) interface are also available to HTML elements, allowing them to be nested within each other, created and deleted, moved around, and so forth.

The `HTMLElement` interface is generic, however, providing only the functionality common to all HTML elements such as the element's ID, its coordinates, the HTML making up the element, information about scroll position, and so forth.

In order to expand upon the functionality of the core `HTMLElement` interface to provide the features needed by a specific element, the `HTMLElement` class is subclassed to add the needed properties and methods. For example, the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element is represented by an object of type [`HTMLCanvasElement`](htmlcanvaselement). `HTMLCanvasElement` augments the `HTMLElement` type by adding properties such as [`height`](htmlcanvaselement/height) and methods like [`getContext()`](htmlcanvaselement/getcontext) to provide canvas-specific features.

The overall inheritance for HTML element classes looks like this:

<img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHhtbG5zOnhsPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hsaW5rIiB2aWV3Qm94PSIxOTEuNSAyNjMuNSA2NjEuMzg3IDU2NSIgd2lkdGg9IjY2MS4zODciIGhlaWdodD0iNTY1Ij48ZGVmcz48bWFya2VyIG9yaWVudD0iYXV0byIgb3ZlcmZsb3c9InZpc2libGUiIG1hcmtlclVuaXRzPSJzdHJva2VXaWR0aCIgaWQ9ImEiIHN0cm9rZS1saW5lam9pbj0ibWl0ZXIiIHN0cm9rZS1taXRlcmxpbWl0PSIxMCIgdmlld0JveD0iLTkgLTQgMTAgOCIgbWFya2VyV2lkdGg9IjEwIiBtYXJrZXJIZWlnaHQ9IjgiIGNvbG9yPSIjMDAwIj48cGF0aCBkPSJNLTggMGw4IDN2LTZ6IiBmaWxsPSJub25lIiBzdHJva2U9ImN1cnJlbnRDb2xvciIvPjwvbWFya2VyPjxtYXJrZXIgb3JpZW50PSJhdXRvIiBvdmVyZmxvdz0idmlzaWJsZSIgbWFya2VyVW5pdHM9InN0cm9rZVdpZHRoIiBpZD0iYiIgc3Ryb2tlLWxpbmVqb2luPSJtaXRlciIgc3Ryb2tlLW1pdGVybGltaXQ9IjEwIiB2aWV3Qm94PSItMSAtNCAxMCA4IiBtYXJrZXJXaWR0aD0iMTAiIG1hcmtlckhlaWdodD0iOCIgY29sb3I9IiMwMDAiPjxwYXRoIGQ9Ik04IDBMMC0zdjZ6IiBmaWxsPSJub25lIiBzdHJva2U9ImN1cnJlbnRDb2xvciIvPjwvbWFya2VyPjwvZGVmcz48ZyBmaWxsPSJub25lIj48YSB4bDpocmVmPSJodHRwczovL2RldmVsb3Blci5tb3ppbGxhLm9yZy9lbi1VUy9kb2NzL1dlYi9BUEkvRXZlbnRUYXJnZXQiPjxwYXRoIGZpbGw9IiNlZGVkZmYiIGQ9Ik0xOTIgNTE2aDExNC45Njh2NDhIMTkyeiIvPjxwYXRoIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIiBkPSJNMTkyIDUxNmgxMTQuOTY4djQ4SDE5MnoiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxOTcgNTMxLjUpIiBmaWxsPSIjMDAwIj48dHNwYW4gZm9udC1mYW1pbHk9IkNvdXJpZXIgTmV3IiBmb250LXNpemU9IjE0IiBmb250LXdlaWdodD0iNDAwIiB4PSI2LjI3NiIgeT0iMTIiPkV2ZW50VGFyZ2V0PC90c3Bhbj48L3RleHQ+PC9hPjxhIHhsOmhyZWY9Imh0dHBzOi8vZGV2ZWxvcGVyLm1vemlsbGEub3JnL2VuLVVTL2RvY3MvV2ViL0FQSS9Ob2RlIj48cGF0aCBmaWxsPSIjZWRlZGZmIiBkPSJNMzI3Ljg3MSA1MTZoNjIuNzF2NDhoLTYyLjcxeiIvPjxwYXRoIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIiBkPSJNMzI3Ljg3MSA1MTZoNjIuNzF2NDhoLTYyLjcxeiIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDMzMi44NzEgNTMxLjUpIiBmaWxsPSIjMDAwIj48dHNwYW4gZm9udC1mYW1pbHk9IkNvdXJpZXIgTmV3IiBmb250LXNpemU9IjE0IiBmb250LXdlaWdodD0iNDAwIiB4PSI5LjU1MiIgeT0iMTIiPk5vZGU8L3RzcGFuPjwvdGV4dD48L2E+PGEgeGw6aHJlZj0iaHR0cHM6Ly9kZXZlbG9wZXIubW96aWxsYS5vcmcvZW4tVVMvZG9jcy9XZWIvQVBJL0VsZW1lbnQiPjxwYXRoIGZpbGw9IiNlZGVkZmYiIGQ9Ik00MTEuNDg0IDUxNmg5NC4wNjV2NDhoLTk0LjA2NXoiLz48cGF0aCBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZD0iTTQxMS40ODQgNTE2aDk0LjA2NXY0OGgtOTQuMDY1eiIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDQxNi40ODQgNTMxLjUpIiBmaWxsPSIjMDAwIj48dHNwYW4gZm9udC1mYW1pbHk9IkNvdXJpZXIgTmV3IiBmb250LXNpemU9IjE0IiBmb250LXdlaWdodD0iNDAwIiB4PSIxMi42MjciIHk9IjEyIj5FbGVtZW50PC90c3Bhbj48L3RleHQ+PC9hPjxhIHhsOmhyZWY9Imh0dHBzOi8vZGV2ZWxvcGVyLm1vemlsbGEub3JnL2VuLVVTL2RvY3MvV2ViL0FQSS9IVE1MRWxlbWVudCI+PHBhdGggZmlsbD0iI2VkZWRmZiIgZD0iTTUyNi40NTIgNTE2SDY0MS40MnY0OEg1MjYuNDUyeiIvPjxwYXRoIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIiBkPSJNNTI2LjQ1MiA1MTZINjQxLjQydjQ4SDUyNi40NTJ6Ii8+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoNTMxLjQ1MiA1MzEuNSkiIGZpbGw9IiMwMDAiPjx0c3BhbiBmb250LWZhbWlseT0iQ291cmllciBOZXciIGZvbnQtc2l6ZT0iMTQiIGZvbnQtd2VpZ2h0PSI0MDAiIHg9IjYuMjc2IiB5PSIxMiI+SFRNTEVsZW1lbnQ8L3RzcGFuPjwvdGV4dD48L2E+PGEgeGw6aHJlZj0iaHR0cHM6Ly9kZXZlbG9wZXIubW96aWxsYS5vcmcvZW4tVVMvZG9jcy9XZWIvQVBJL0hUTUxBbmNob3JFbGVtZW50Ij48cGF0aCBmaWxsPSIjZWRlZGZmIiBkPSJNNjg1LjE2MSAyNjRoMTY3LjIyNnY0OEg2ODUuMTYxeiIvPjxwYXRoIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIiBkPSJNNjg1LjE2MSAyNjRoMTY3LjIyNnY0OEg2ODUuMTYxeiIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDY5MC4xNjEgMjc5LjUpIiBmaWxsPSIjMDAwIj48dHNwYW4gZm9udC1mYW1pbHk9IkNvdXJpZXIgTmV3IiBmb250LXNpemU9IjE0IiBmb250LXdlaWdodD0iNDAwIiB4PSI3LjIwMSIgeT0iMTIiPkhUTUxBbmNob3JFbGVtZW50PC90c3Bhbj48L3RleHQ+PC9hPjxhIHhsOmhyZWY9Imh0dHBzOi8vZGV2ZWxvcGVyLm1vemlsbGEub3JnL2VuLVVTL2RvY3MvV2ViL0FQSS9IVE1MQXJlYUVsZW1lbnQiPjxwYXRoIGZpbGw9IiNlZGVkZmYiIGQ9Ik02ODUuMTYxIDMyNGgxNjcuMjI2djQ4SDY4NS4xNjF6Ii8+PHBhdGggc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIGQ9Ik02ODUuMTYxIDMyNGgxNjcuMjI2djQ4SDY4NS4xNjF6Ii8+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoNjkwLjE2MSAzMzkuNSkiIGZpbGw9IiMwMDAiPjx0c3BhbiBmb250LWZhbWlseT0iQ291cmllciBOZXciIGZvbnQtc2l6ZT0iMTQiIGZvbnQtd2VpZ2h0PSI0MDAiIHg9IjE1LjYwMyIgeT0iMTIiPkhUTUxBcmVhRWxlbWVudDwvdHNwYW4+PC90ZXh0PjwvYT48YSB4bDpocmVmPSJodHRwczovL2RldmVsb3Blci5tb3ppbGxhLm9yZy9lbi1VUy9kb2NzL1dlYi9BUEkvSFRNTEFuY2hvckVsZW1lbnQiPjxwYXRoIGZpbGw9IiNlZGVkZmYiIGQ9Ik02ODUuMTYxIDM4NGgxNjcuMjI2djQ4SDY4NS4xNjF6Ii8+PHBhdGggc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIGQ9Ik02ODUuMTYxIDM4NGgxNjcuMjI2djQ4SDY4NS4xNjF6Ii8+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoNjkwLjE2MSAzOTkuNSkiIGZpbGw9IiMwMDAiPjx0c3BhbiBmb250LWZhbWlseT0iQ291cmllciBOZXciIGZvbnQtc2l6ZT0iMTQiIGZvbnQtd2VpZ2h0PSI0MDAiIHg9IjcuMjAxIiB5PSIxMiI+SFRNTEFuY2hvckVsZW1lbnQ8L3RzcGFuPjwvdGV4dD48L2E+PGEgeGw6aHJlZj0iaHR0cHM6Ly9kZXZlbG9wZXIubW96aWxsYS5vcmcvZW4tVVMvZG9jcy9XZWIvQVBJLyI+PHBhdGggZmlsbD0iI2VkZWRmZiIgZD0iTTY4NS4xNjEgNDQ0aDE2Ny4yMjZ2NDhINjg1LjE2MXoiLz48cGF0aCBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZD0iTTY4NS4xNjEgNDQ0aDE2Ny4yMjZ2NDhINjg1LjE2MXoiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSg2OTAuMTYxIDQ1OS41KSIgZmlsbD0iIzAwMCI+PHRzcGFuIGZvbnQtZmFtaWx5PSJDb3VyaWVyIE5ldyIgZm9udC1zaXplPSIxNCIgZm9udC13ZWlnaHQ9IjQwMCIgeD0iMjQuMDA0IiB5PSIxMiI+SFRNTEJSRWxlbWVudDwvdHNwYW4+PC90ZXh0PjwvYT48YSB4bDpocmVmPSJodHRwczovL2RldmVsb3Blci5tb3ppbGxhLm9yZy9lbi1VUy9kb2NzL1dlYi9BUEkvSFRNTFRyYWNrRWxlbWVudCI+PHBhdGggZmlsbD0iI2VkZWRmZiIgZD0iTTY4NS4xNjEgNjAwaDE2Ny4yMjZ2NDhINjg1LjE2MXoiLz48cGF0aCBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZD0iTTY4NS4xNjEgNjAwaDE2Ny4yMjZ2NDhINjg1LjE2MXoiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSg2OTAuMTYxIDYxNS41KSIgZmlsbD0iIzAwMCI+PHRzcGFuIGZvbnQtZmFtaWx5PSJDb3VyaWVyIE5ldyIgZm9udC1zaXplPSIxNCIgZm9udC13ZWlnaHQ9IjQwMCIgeD0iMTEuNDAyIiB5PSIxMiI+SFRNTFRyYWNrRWxlbWVudDwvdHNwYW4+PC90ZXh0PjwvYT48YSB4bDpocmVmPSJodHRwczovL2RldmVsb3Blci5tb3ppbGxhLm9yZy9lbi1VUy9kb2NzL1dlYi9BUEkvSFRNTFVMaXN0RWxlbWVudCI+PHBhdGggZmlsbD0iI2VkZWRmZiIgZD0iTTY4NS4xNjEgNjYwaDE2Ny4yMjZ2NDhINjg1LjE2MXoiLz48cGF0aCBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZD0iTTY4NS4xNjEgNjYwaDE2Ny4yMjZ2NDhINjg1LjE2MXoiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSg2OTAuMTYxIDY3NS41KSIgZmlsbD0iIzAwMCI+PHRzcGFuIGZvbnQtZmFtaWx5PSJDb3VyaWVyIE5ldyIgZm9udC1zaXplPSIxNCIgZm9udC13ZWlnaHQ9IjQwMCIgeD0iMTEuNDAyIiB5PSIxMiI+SFRNTFVMaXN0RWxlbWVudDwvdHNwYW4+PC90ZXh0PjwvYT48YSB4bDpocmVmPSJodHRwczovL2RldmVsb3Blci5tb3ppbGxhLm9yZy9lbi1VUy9kb2NzL1dlYi9BUEkvSFRNTFVua25vd25FbGVtZW50Ij48cGF0aCBmaWxsPSIjZWRlZGZmIiBkPSJNNjg1LjE2MSA3MjBoMTY3LjIyNnY0OEg2ODUuMTYxeiIvPjxwYXRoIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIiBkPSJNNjg1LjE2MSA3MjBoMTY3LjIyNnY0OEg2ODUuMTYxeiIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDY5MC4xNjEgNzM1LjUpIiBmaWxsPSIjMDAwIj48dHNwYW4gZm9udC1mYW1pbHk9IkNvdXJpZXIgTmV3IiBmb250LXNpemU9IjE0IiBmb250LXdlaWdodD0iNDAwIiB4PSIzLjAwMSIgeT0iMTIiPkhUTUxVbmtub3duRWxlbWVudDwvdHNwYW4+PC90ZXh0PjwvYT48YSB4bDpocmVmPSJodHRwczovL2RldmVsb3Blci5tb3ppbGxhLm9yZy9lbi1VUy9kb2NzL1dlYi9BUEkvSFRNTFZpZGVvRWxlbWVudCI+PHBhdGggZmlsbD0iI2VkZWRmZiIgZD0iTTY4NS4xNjEgNzgwaDE2Ny4yMjZ2NDhINjg1LjE2MXoiLz48cGF0aCBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZD0iTTY4NS4xNjEgNzgwaDE2Ny4yMjZ2NDhINjg1LjE2MXoiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSg2OTAuMTYxIDc5NS41KSIgZmlsbD0iIzAwMCI+PHRzcGFuIGZvbnQtZmFtaWx5PSJDb3VyaWVyIE5ldyIgZm9udC1zaXplPSIxNCIgZm9udC13ZWlnaHQ9IjQwMCIgeD0iMTEuNDAyIiB5PSIxMiI+SFRNTFZpZGVvRWxlbWVudDwvdHNwYW4+PC90ZXh0PjwvYT48ZWxsaXBzZSBjeD0iNzYzLjU0OCIgY3k9IjUxMCIgcng9IjUuMjI2IiByeT0iNiIgZmlsbD0iIzY2NiIvPjxlbGxpcHNlIGN4PSI3NjMuNTQ4IiBjeT0iNTEwIiByeD0iNS4yMjYiIHJ5PSI2IiBzdHJva2U9IiM5OTkiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIvPjxlbGxpcHNlIGN4PSI3NjMuNTQ4IiBjeT0iNTM0IiByeD0iNS4yMjYiIHJ5PSI2IiBmaWxsPSIjNjY2Ii8+PGVsbGlwc2UgY3g9Ijc2My41NDgiIGN5PSI1MzQiIHJ4PSI1LjIyNiIgcnk9IjYiIHN0cm9rZT0iIzk5OSIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIi8+PGVsbGlwc2UgY3g9Ijc2My41NDgiIGN5PSI1NTgiIHJ4PSI1LjIyNiIgcnk9IjYiIGZpbGw9IiM2NjYiLz48ZWxsaXBzZSBjeD0iNzYzLjU0OCIgY3k9IjU1OCIgcng9IjUuMjI2IiByeT0iNiIgc3Ryb2tlPSIjOTk5IiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiLz48ZWxsaXBzZSBjeD0iNzYzLjU0OCIgY3k9IjU4MiIgcng9IjUuMjI2IiByeT0iNiIgZmlsbD0iIzY2NiIvPjxlbGxpcHNlIGN4PSI3NjMuNTQ4IiBjeT0iNTgyIiByeD0iNS4yMjYiIHJ5PSI2IiBzdHJva2U9IiM5OTkiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIvPjxwYXRoIG1hcmtlci1zdGFydD0idXJsKCNhKSIgc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIGQ9Ik0zMTYuODY4IDU0MGgxMS4wMDNtNzIuNjEgMGgxMS4wMDNtMTAzLjk2NCAwaDExLjAwNCIvPjxwYXRoIGQ9Ik02ODUuMTYxIDI4OGgtMjR2MjUyaC05Ljg0MiIgbWFya2VyLWVuZD0idXJsKCNiKSIgc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiLz48cGF0aCBkPSJNNjUxLjMyIDU0MGg5Ljg0MXYyNjRoMjQiIG1hcmtlci1zdGFydD0idXJsKCNhKSIgc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiLz48cGF0aCBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZD0iTTY2MS4xNjEgMzQ4aDI0bS0yNCA1OS41aDI0bS0yNCA1OS41aDI0bS0yNCAxNTdoMjRtLTI0IDYwaDI0bS0yNCA2MGgyNCIvPjwvZz48L3N2Zz4=" alt="Hierarchy of interfaces for HTML elements" width="661" height="565" />

As such, an element inherits the properties and methods of all of its ancestors. For example, consider a [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) element, which is represented in the DOM by an object of type [`HTMLAnchorElement`](htmlanchorelement). The element, then, includes the anchor-specific properties and methods described in that class's documentation, but also those defined by [`HTMLElement`](htmlelement) and [`Element`](element), as well as from [`Node`](node) and, finally, [`EventTarget`](eventtarget).

Each level defines a key aspect of the utility of the element. From `Node`, the element inherits concepts surrounding the ability for the element to be contained by another element, and to contain other elements itself. Of special importance is what is gained by inheriting from `EventTarget`: the ability to receive and handle events such as mouse clicks, play and pause events, and so forth.

There are elements that share commonalities and thus have an additional intermediary type. For example, the [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) and [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) elements both present audiovisual media. The corresponding types, [`HTMLAudioElement`](htmlaudioelement) and [`HTMLVideoElement`](htmlvideoelement), are both based upon the common type [`HTMLMediaElement`](htmlmediaelement), which in turn is based upon [`HTMLElement`](htmlelement) and so forth. `HTMLMediaElement` defines the methods and properties held in common between audio and video elements.

These element-specific interfaces make up the majority of the HTML DOM API, and are the focus of this article. To learn more about the actual structure of the [DOM](document_object_model), see [Introduction to the DOM](document_object_model/introduction).

## HTML DOM target audience

The features exposed by the HTML DOM are among the most commonly-used APIs in the web developer's arsenal. All but the most simple web applications will use some features of the HTML DOM.

## HTML DOM API interfaces

The majority of the interfaces that comprise the HTML DOM API map almost one-to-one to individual HTML elements, or to a small group of elements with similar functionality. In addition, the HTML DOM API includes a few interfaces and types to support the HTML element interfaces.

### HTML element interfaces

These interfaces represent specific HTML elements (or sets of related elements which have the same properties and methods associated with them).

- <span class="indexListRow"><span class="indexListTerm">[`HTMLAnchorElement`](htmlanchorelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLAreaElement`](htmlareaelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLAudioElement`](htmlaudioelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLBRElement`](htmlbrelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLBaseElement`](htmlbaseelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLBodyElement`](htmlbodyelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLButtonElement`](htmlbuttonelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLCanvasElement`](htmlcanvaselement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLDListElement`](htmldlistelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLDataElement`](htmldataelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLDataListElement`](htmldatalistelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLDetailsElement`](htmldetailselement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLDialogElement`](htmldialogelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm"><span class="page-not-created">`HTMLDirectoryElement`</span></span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLDivElement`](htmldivelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLElement`](htmlelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLEmbedElement`](htmlembedelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLFieldSetElement`](htmlfieldsetelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLFormElement`](htmlformelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLHRElement`](htmlhrelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLHeadElement`](htmlheadelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLHeadingElement`](htmlheadingelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLHtmlElement`](htmlhtmlelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLIFrameElement`](htmliframeelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLImageElement`](htmlimageelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLInputElement`](htmlinputelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLLIElement`](htmllielement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLLabelElement`](htmllabelelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLLegendElement`](htmllegendelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLLinkElement`](htmllinkelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLMapElement`](htmlmapelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLMediaElement`](htmlmediaelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLMenuElement`](htmlmenuelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLMetaElement`](htmlmetaelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLMeterElement`](htmlmeterelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLModElement`](htmlmodelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLOListElement`](htmlolistelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLObjectElement`](htmlobjectelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLOptGroupElement`](htmloptgroupelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLOptionElement`](htmloptionelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLOutputElement`](htmloutputelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLParagraphElement`](htmlparagraphelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLParamElement`](htmlparamelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLPictureElement`](htmlpictureelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLPreElement`](htmlpreelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLProgressElement`](htmlprogresselement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLQuoteElement`](htmlquoteelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLScriptElement`](htmlscriptelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLSelectElement`](htmlselectelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLSlotElement`](htmlslotelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLSourceElement`](htmlsourceelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLSpanElement`](htmlspanelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLStyleElement`](htmlstyleelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLTableCaptionElement`](htmltablecaptionelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLTableCellElement`](htmltablecellelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLTableColElement`](htmltablecolelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLTableElement`](htmltableelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLTableRowElement`](htmltablerowelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLTableSectionElement`](htmltablesectionelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLTemplateElement`](htmltemplateelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLTextAreaElement`](htmltextareaelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLTimeElement`](htmltimeelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLTitleElement`](htmltitleelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLTrackElement`](htmltrackelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLUListElement`](htmlulistelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLUnknownElement`](htmlunknownelement)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLVideoElement`](htmlvideoelement)</span></span>

#### Deprecated HTML Element Interfaces

- <span class="indexListRow"><span class="indexListTerm">[`HTMLMarqueeElement`](htmlmarqueeelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span></span></span>

#### Obsolete HTML Element Interfaces

- <span class="indexListRow"><span class="indexListTerm">[`HTMLBaseFontElement`](htmlbasefontelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span></span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLFontElement`](htmlfontelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span></span></span>
- <span class="indexListRow"><span class="indexListTerm"><span class="page-not-created">`HTMLFrameElement`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span></span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLFrameSetElement`](htmlframesetelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span></span></span>
- <span class="indexListRow"><span class="indexListTerm"><span class="page-not-created">`HTMLIsIndexElement`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span></span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLMenuItemElement`](htmlmenuitemelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span></span></span>

### Web app and browser integration interfaces

These interfaces offer access to the browser window and document that contain the HTML, as well as to the browser's state, available plugins (if any), and various configuration options.

- <span class="indexListRow"><span class="indexListTerm"><span class="page-not-created">`BarProp`</span></span></span>
- <span class="indexListRow"><span class="indexListTerm">[`Navigator`](navigator)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`Window`](window)</span></span>

#### Deprecated web app and browser integration interfaces

- <span class="indexListRow"><span class="indexListTerm"><span class="page-not-created">`External`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span></span></span>

#### Obsolete web app and browser integration interfaces

- <span class="indexListRow"><span class="indexListTerm"><span class="page-not-created">`ApplicationCache`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span></span></span>
- <span class="indexListRow"><span class="indexListTerm">[`Plugin`](plugin) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span></span></span>
- <span class="indexListRow"><span class="indexListTerm">[`PluginArray`](pluginarray) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span></span></span>

### Form support interfaces

These interfaces provide structure and functionality required by the elements used to create and manage forms, including the [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) and [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) elements.

- <span class="indexListRow"><span class="indexListTerm">[`FormDataEvent`](formdataevent)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLFormControlsCollection`](htmlformcontrolscollection)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HTMLOptionsCollection`](htmloptionscollection)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`RadioNodeList`](radionodelist)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`ValidityState`](validitystate)</span></span>

### Canvas and image interfaces

These interfaces represent objects used by the Canvas API as well as the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element and [`<picture>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture) elements.

- <span class="indexListRow"><span class="indexListTerm">[`CanvasGradient`](canvasgradient)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`CanvasPattern`](canvaspattern)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`CanvasRenderingContext2D`](canvasrenderingcontext2d)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`ImageBitmap`](imagebitmap)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`ImageBitmapRenderingContext`](imagebitmaprenderingcontext)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`ImageData`](imagedata)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`OffscreenCanvas`](offscreencanvas)</span></span>
- <span class="indexListRow"><span class="indexListTerm"><span class="page-not-created">`OffscreenCanvasRenderingContext2D`</span></span></span>
- <span class="indexListRow"><span class="indexListTerm">[`Path2D`](path2d)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`TextMetrics`](textmetrics)</span></span>

### Media interfaces

The media interfaces provide HTML access to the contents of the media elements: [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) and [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video).

- <span class="indexListRow"><span class="indexListTerm">[`AudioTrack`](audiotrack)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`AudioTrackList`](audiotracklist)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`MediaError`](mediaerror)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`TextTrack`](texttrack)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`TextTrackCue`](texttrackcue)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`TextTrackCueList`](texttrackcuelist)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`TextTrackList`](texttracklist)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`TimeRanges`](timeranges)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`TrackEvent`](trackevent)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`VideoTrack`](videotrack)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`VideoTrackList`](videotracklist)</span></span>

### Drag and drop interfaces

These interfaces are used by the [HTML_Drag_and_Drop_API](html_drag_and_drop_api) to represent individual draggable (or dragged) items, groups of dragged or draggable items, and to handle the drag and drop process.

- <span class="indexListRow"><span class="indexListTerm">[`DataTransfer`](datatransfer)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`DataTransferItem`](datatransferitem)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`DataTransferItemList`](datatransferitemlist)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`DragEvent`](dragevent)</span></span>

### Page history interfaces

The History API interfaces let you access information about the browser's history, as well as to shift the browser's current tab forward and backward through that history.

- <span class="indexListRow"><span class="indexListTerm">[`BeforeUnloadEvent`](beforeunloadevent)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`HashChangeEvent`](hashchangeevent)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`History`](history)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`Location`](location)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`PageTransitionEvent`](pagetransitionevent)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`PopStateEvent`](popstateevent)</span></span>

### Web Components interfaces

These interfaces are used by the [Web Components API](https://developer.mozilla.org/en-US/docs/Web/Web_Components) to create and manage the available [custom elements](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements).

- <span class="indexListRow"><span class="indexListTerm">[`CustomElementRegistry`](customelementregistry)</span></span>

### Miscellaneous and supporting interfaces

These supporting object types are used in a variety of ways in the HTML DOM API. In addition, [`PromiseRejectionEvent`](promiserejectionevent) represents the event delivered when a [JavaScript](https://developer.mozilla.org/en-US/docs/Glossary/JavaScript) [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) is rejected.

- <span class="indexListRow"><span class="indexListTerm">[`DOMStringList`](domstringlist)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`DOMStringMap`](domstringmap)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`ErrorEvent`](errorevent)</span></span>
- <span class="indexListRow"><span class="indexListTerm"><span class="page-not-created">`HTMLAllCollection`</span></span></span>
- <span class="indexListRow"><span class="indexListTerm">[`MimeType`](mimetype)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`MimeTypeArray`](mimetypearray)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`PromiseRejectionEvent`](promiserejectionevent)</span></span>

### Interfaces belonging to other APIs

Several interfaces are technically defined in the HTML specification while actually being part of other APIs.

#### Web storage interfaces

The [Web_Storage_API](web_storage_api) provides the ability for web sites to store data either temporarily or permanently on the user's device for later re-use.

- <span class="indexListRow"><span class="indexListTerm">[`Storage`](storage)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`StorageEvent`](storageevent)</span></span>

#### Web Workers interfaces

These interfaces are used by the [Web_Workers_API](web_workers_api) both to establish the ability for workers to interact with an app and its content, but also to support messaging between windows or apps.

- <span class="indexListRow"><span class="indexListTerm">[`BroadcastChannel`](broadcastchannel)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`DedicatedWorkerGlobalScope`](dedicatedworkerglobalscope)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`MessageChannel`](messagechannel)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`MessageEvent`](messageevent)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`MessagePort`](messageport)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`SharedWorker`](sharedworker)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`SharedWorkerGlobalScope`](sharedworkerglobalscope)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`Worker`](worker)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`WorkerGlobalScope`](workerglobalscope)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`WorkerLocation`](workerlocation)</span></span>
- <span class="indexListRow"><span class="indexListTerm"><span class="page-not-created">`WorkerNavigator `</span></span></span>

#### WebSocket interfaces

These interfaces, defined by the HTML specification, are used by the [WebSockets_API](websockets_api).

- <span class="indexListRow"><span class="indexListTerm">[`CloseEvent`](closeevent)</span></span>
- <span class="indexListRow"><span class="indexListTerm">[`WebSocket`](websocket)</span></span>

#### Server-sent events interfaces

The [`EventSource`](eventsource) interface represents the source which sent or is sending [server-sent events](server-sent_events).

- <span class="indexListRow"><span class="indexListTerm">[`EventSource`](eventsource)</span></span>

## Examples

In this example, an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element's <span class="page-not-created">`input`</span> event is monitored in order to update the state of a form's "submit" button based on whether or not a given field currently has a value.

#### JavaScript

    const nameField = document.getElementById("userName");
    const sendButton = document.getElementById("sendButton")

    sendButton.disabled = true;
    // [note: this is disabled since it causes this article to always load with this example focused and scrolled into view]
    //nameField.focus();

    nameField.addEventListener("input", event => {
      const elem = event.target;
      const valid = elem.value.length != 0;

      if (valid && sendButton.disabled) {
        sendButton.disabled = false;
      } else if (!valid && !sendButton.disabled) {
        sendButton.disabled = true;
      }
    });

This code uses the [`Document`](document) interface's [`getElementById()`](document/getelementbyid) method to get the DOM object representing the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) elements whose IDs are `userName` and `sendButton`. With these, we can access the properties and methods that provide information about and grant control over these elements.

The [`HTMLInputElement`](htmlinputelement) object for the "Send" button's <span class="page-not-created">`disabled`</span> property is set to `true`, which disables the "Send" button so it can't be clicked. In addition, the user name input field is made the active focus by calling the [`focus()`](htmlorforeignelement/focus) method it inherits from [`HTMLElement`](htmlelement).

Then [`addEventListener()`](eventtarget/addeventlistener) is called to add a handler for the `input` event to the user name input. This code looks at the length of the current value of the input; if it's zero, then the "Send" button is disabled if it's not already disabled. Otherwise, the code ensures that the button is enabled.

With this in place, the "Send" button is always enabled whenever the user name input field has a value, and disabled when it's empty.

#### HTML

The HTML for the form looks like this:

    <p>Please provide the information below. Items marked with "*" are required.</p>
    <form action="" method="get">
      <p>
        <label for="userName" required>Your name:</label>
        <input type="text" id="userName"> (*)
      </p>
      <p>
        <label for="email">Email:</label>
        <input type="email" id="userEmail">
      </p>
      <input type="submit" value="Send" id="sendButton">
    </form>

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG HTML Specification</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/">HTML5</a></td><td><span class="spec-rec">Recommendation</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-HTML/">Document Object Model (DOM) Level 2 HTML Specification</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/">Document Object Model (DOM) Level 2 HTML Specification</a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTML_DOM_API`

1

12

1

5.5

8

1.3

1

18

4

10.1

1

1.0

`accessKey`

17

12

5

5.5

≤12.1

6

4.4

18

5

≤12.1

6

1.0

`accessKeyLabel`

No

No

8

No

No

14

No

No

8

No

14

No

`animationcancel_event`

No

No

54

No

No

13.1

12

No

No

54

No

13.4

12

No

`animationend_event`

43

12

Yes

10

30

9

43

43

Yes

30

9

4.0

`animationiteration_event`

43

12

51

10

30

9

43

43

51

30

9

4.0

`animationstart_event`

43

12

51

10

30

9

43

43

51

30

9

4.0

`attachInternals`

77

79

No

No

64

No

77

77

No

55

No

12.0

`autocapitalize`

66

79

83

No

53

No

66

66

83

47

10.3

9.0

`beforeinput_event`

Yes

79

87

74-87

No

Yes

Yes

Yes

Yes

87

79-87

Yes

Yes

Yes

`blur`

1

12

1.5

5.5

8

3

4.4

18

4

10.1

1

1.0

`click`

9

Before Chrome 19, `click()` is only defined on buttons and inputs.

12

3

\["Before Firefox 5, `click()` is only defined on buttons and inputs, and has no effect on text and file inputs.", "Starting in Firefox 75, the `click()` function works even when the element is not attached to a DOM tree."\]

5.5

10.5

6

≤37

Before Android WebView 4.4, `click()` is only defined on buttons and inputs.

18

Before Chrome 19, `click()` is only defined on buttons and inputs.

4

\["Before Firefox 5, `click()` is only defined on buttons and inputs, and has no effect on text and file inputs.", "Starting in Firefox for Android 79, the `click()` function works even when the element is not attached to a DOM tree."\]

11

6

1.0

Before Samsung Internet 1.5, `click()` is only defined on buttons and inputs.

`contentEditable`

1

12

3

5.5

9

3

4.4

18

4

10.1

1

1.0

`contextMenu`

45-61

≤18-79

8

No

No

No

45-61

45-61

8

No

No

5.0-8.0

`dataset`

8

12

6

11

11

5.1

4.4

18

6

11

5

1.0

`dir`

1

12

1

5.5

≤12.1

3

4.4

18

4

≤12.1

1

1.0

`draggable`

3

12

2

10

12

5

4.4

18

4

12

4

1.0

`enterKeyHint`

77

79

79

No

64

13.1

77

77

79

55

13.4

12.0

`focus`

1

12

1.5

5.5

8

3

4.4

18

4

10.1

1

1.0

`forceSpellCheck`

No

No

No

No

No

No

No

No

No

No

No

No

`gotpointercapture_event`

57

≤79

59

?

44

13

57

57

79

43

13

7.0

`hidden`

6

12

1

11

11.6

5.1

≤37

18

4

12

5

1.0

`inert`

60

79

81

No

47

No

No

60

81

44

No

No

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

`input_event`

1

79

12-79

Not supported on `select`, `checkbox`, or `radio` inputs.

6

9

Only supports `input` of type `text` and `password`.

11.6

3.1

1

18

6

12

2

1.0

`inputMode`

66

79

77

No

53

12.1

66

66

79

47

12.2

9.0

`isContentEditable`

1

12

4

5.5

≤12.1

3

4.4

18

4

≤12.1

1

1.0

`itemId`

17-28

No

16-49

No

11-15

No

No

18-28

16-49

11-14

No

1.0-1.5

`itemProp`

17-28

No

16-49

No

11-15

No

No

18-28

16-49

11-14

No

1.0-1.5

`itemRef`

17-28

No

16-49

No

11-15

No

No

18-28

16-49

11-14

No

1.0-1.5

`itemScope`

17-28

No

16-49

No

11-15

No

No

18-28

16-49

11-14

No

1.0-1.5

`itemType`

17-28

No

16-49

No

11-15

No

No

18-28

16-49

11-14

No

1.0-1.5

`itemValue`

17-28

No

16-49

No

11-15

No

No

18-28

16-49

11-14

No

1.0-1.5

`lang`

1

12

1

5.5

≤12.1

3

4.4

18

4

≤12.1

1

1.0

`lostpointercapture_event`

57

≤79

59

?

44

13

57

57

79

43

13

7.0

`nonce`

61

79

75

No

48

10

The property is defined only for its useful elements: `<link>`, `<script>`, and `<style>`; it is undefined for all other elements.

61

61

79

45

10

The property is defined only for its useful elements: `<link>`, `<script>`, and `<style>`; it is undefined for all other elements.

8.0

`offsetHeight`

1

12

1

5.5

8

3

1

18

4

10.1

1

1.0

`offsetLeft`

1

12

1

5.5

8

3

1

18

4

10.1

1

1.0

`offsetParent`

1

12

1

5.5

8

3

1

18

4

10.1

1

1.0

`offsetTop`

1

12

1

5.5

8

3

1

18

4

10.1

1

1.0

`offsetWidth`

1

12

1

5.5

8

3

1

18

4

10.1

1

1.0

`oncopy`

1

12

3

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`oncut`

1

12

9

5.5

≤12.1

3

1

18

9

≤12.1

1

1.0

`onpaste`

1

12

9

5.5

≤12.1

3

1

18

9

≤12.1

1

1.0

`outerText`

43

12

No

5.5

≤12.1

1.3

43

43

No

≤12.1

1

4.0

`pointercancel_event`

55

12

12-79

59

29

11

10

42

No

55

55

79

29

42

No

6.0

`pointerdown_event`

55

12

12-79

59

29

11

10

42

No

55

55

79

29

42

No

6.0

`pointerenter_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

`pointerleave_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

`pointermove_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

`pointerout_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

`pointerover_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

`pointerup_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

`spellcheck`

9

12

2

10

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`style`

1

12

1

5.5

8

3

1

18

4

10.1

1

1.0

`tabIndex`

1

18

12

Returns incorrect value for elements without an explicit tabindex attribute. See [issue 4365703](https://developer.microsoft.com/microsoft-edge/platform/issues/4365703/) for details.

1

5.5

Returns incorrect value for elements without an explicit tabindex attribute. See [issue 4365703](https://developer.microsoft.com/microsoft-edge/platform/issues/4365703/) for details.

≤12.1

3.1

4.4

18

4

≤12.1

2

1.0

`title`

1

12

1

5.5

≤12.1

3

4.4

18

4

≤12.1

1

1.0

`transitioncancel_event`

74

≤79

53

?

62

13.1

12

74

74

53

53

13.4

12

11.0

`transitionend_event`

26

1

≤79

≤79

51

10

12.1

15

11.6-15

6.1

4

≤37

1

26

18

51

12.1

14

12-14

7

3.2

1.5

1.0

`transitionrun_event`

74

≤79

53

?

62

13.1

12

74

74

53

53

13.4

12

11.0

`transitionstart_event`

74

≤79

53

?

62

13.1

12

74

74

53

53

13.4

12

11.0

`translate`

19

79

No

No

15

6

4.4

25

No

14

6

1.5

## See also

References

- [HTML elements reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
- [HTML attribute reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes)
- [Document Object Model (DOM)](document_object_model) reference

Guides

- [Manipulating documents](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Manipulating_documents): A beginner's guide to manipulating the DOM.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTML_DOM_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTML_DOM_API</a>
