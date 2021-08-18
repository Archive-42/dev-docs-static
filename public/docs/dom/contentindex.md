# ContentIndex

**Draft**

This page is not complete.

The `ContentIndex` interface of the [`Content Index API`](content_index_api) allows developers to register their offline enabled content with the browser.

## Properties

There are no properties of this interface.

## Methods

[`ContentIndex.add()`](contentindex/add)  
Registers an item with the [`content index`](content_index_api).

[`ContentIndex.delete()`](contentindex/delete)  
Unregisters an item from the currently indexed content.

[`ContentIndex.getAll()`](contentindex/getall)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an iterable list of content index entries.

## Examples

### Feature Detection and Interface Access

Here we get a reference to the [`ServiceWorkerRegistration`](serviceworkerregistration), then check for the `index` property, which gives us access to the content index interface.

    // reference registration
    const registration = await navigator.serviceWorker.ready;

    // feature detection
    if ('index' in registration) {

      // Content Index API functionality
      const contentIndex = registration.index;

    }

### Adding to the Content Index

Here we're declaring an item in the correct format and creating an asynchronous function which uses the [`add()`](contentindex/add) method to register it with the [`content index`](content_index_api).

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

### Retrieving Items Within The Current Index

The below example shows an asynchronous function that retrieves items within the [`content index`](content_index_api) and iterates over each entry, building a list for the interface.

    async function createReadingList() {
      // access our service worker registration
      const registration = await navigator.serviceWorker.ready;

      // get our index entries
      const entries = await registration.index.getAll();

      // create a containing element
      const readingListElem = document.createElement('div');

      // test for entries
      if (!Array.length) {

        // if there are no entries, display a message
        const message = document.createElement('p');
        message.innerText = 'You currently have no articles saved for offline reading.'

        readingListElem.append(message);

      } else {

        // if entries are present, display in a list of links to the content
        const listElem = document.createElement('ul');

        for (const entry of entries) {
          const listItem = document.createElement('li');

          const anchorElem = document.createElement('a');
          anchorElem.innerText = entry.title;
          anchorElem.setAttribute('href', entry.url);

          listElem.append(listItem);

        }

        readingListElem.append(listElem);
      }

    }

### Unregistering Indexed Content

Below is an asynchronous function, that removes an item from the [`content index`](content_index_api).

    async function unregisterContent(article) {

      // reference registration
      const registration = await navigator.serviceWorker.ready;

      // feature detect Content Index
      if (!registration.index)
        return;

      // unregister content from index
      await registration.index.delete(article.id);
    }

All the above methods are available within the scope of the [`service worker`](serviceworker). They are accessible from the [`WorkerGlobalScope.self`](workerglobalscope/self) property:

    // service worker script

    self.registration.index.add(item);

    self.registration.index.delete(item.id);

    const contentIndexItems = self.registration.index.getAll();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/content-index/spec/#content-index">Content Index API<br />
<span class="small">The definition of 'ContentIndex' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ContentIndex`

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

`delete`

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

`getAll`

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
- [Service Worker API, along with information about Cache and CacheStorage](service_worker_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ContentIndex" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ContentIndex</a>
