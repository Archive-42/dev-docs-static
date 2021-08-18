# ContentIndex.add()

**Draft**

This page is not complete.

The `add()` method of the [`ContentIndex`](../contentindex) interface registers an item with the <span class="page-not-created">`content index`</span>.

## Syntax

    ContentIndex.add(ContentDescription).then(...);

### Parameters

_ContentDescription_  
An [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) containing the following data:

- `id`: A unique [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) identifier.
- `title`: A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) title for the item. Used in user-visible lists of content.
- `title`: A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) title of the item. Used in user-visible lists of content.
- `description`: A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) description of the item. Used in user-visible lists of content.
- `url`: A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) containing the url of the corresponding HTML document. Needs to be under the scope of the current [`service worker`](../serviceworker).
- `category`: <span class="badge inline optional">Optional</span> A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) defining the category of content. Can be:
  - `''` An empty [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String), this is the default.
  - `homepage`
  - `article`
  - `video`
  - `audio`
- `icons`: <span class="badge inline optional">Optional</span> An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of image resources, defined as an [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) with the following data:
  - `src:` A url [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) of the source image.
  - `sizes:` <span class="badge inline optional">Optional</span> A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) representation of the image size.
  - `type:` <span class="badge inline optional">Optional</span> The [MIME type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) of the image.

### Return value

Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with `undefined`

### Exceptions

`TypeError`  
If the service worker's registration is not present or the service worker does not contain a [`FetchEvent`](../fetchevent).

If the `id`, `title`, `description` or `url` are missing, not of type [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String), or an empty [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String).

If `icons` images are not of image type.

## Examples

Here we're declaring an item in the correct format and creating an asynchronous function which uses the `add` method to register it with the [`content index`](../content_index_api).

    // our content
    const item = {
      id: 'post-1',
      url: '/posts/amet.html',
      title: 'Amet consectetur adipisicing',
      description: 'Repellat et quia iste possimus ducimus aliquid a aut eaque nostrum.',
      icons: [{
        src: '/media/dark.png',
        sizes: '128x128',
        type: 'image/png',
      }],
      category: 'article'
    };

    // our asynchronous function to add indexed content
    async function registerContent(data) {
      const registration = await navigator.serviceWorker.ready;

      // feature detect Content Index
        if (!registration.index) {
            return;
        }

      // register content
      try {
            await registration.index.add(data);
      } catch (e) {
        console.log('Failed to register content: ', e.message);
      }
    }

The `add` method can also be used within the [`service worker`](../serviceworker) scope.

    // our content
    const item = {
      id: 'post-1',
      url: '/posts/amet.html',
      title: 'Amet consectetur adipisicing',
      description: 'Repellat et quia iste possimus ducimus aliquid a aut eaque nostrum.',
      icons: [{
        src: '/media/dark.png',
        sizes: '128x128',
        type: 'image/png',
      }],
      category: 'article'
    };

    self.registration.index.add(item);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/content-index/spec/#content-index-add">Content Index API<br />
<span class="small">The definition of 'add' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`add`

No

No

No

No

No

No

84

84

No

60

No

14.0

## See also

- [An introductory article on the Content Index API](https://web.dev/content-indexing-api/)
- [An app which uses the Content Index API to list and remove 'save for later' content](https://contentindex.dev/)
- [Service Worker API, along with information about Cache and CacheStorage](../service_worker_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ContentIndex/add" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ContentIndex/add</a>
