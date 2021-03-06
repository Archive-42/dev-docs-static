Using Web Workers
=================

Web Workers are a simple means for web content to run scripts in background threads. The worker thread can perform tasks without interfering with the user interface. In addition, they can perform I/O using `XMLHttpRequest` (although the `responseXML` and `channel` attributes are always null) or `fetch` (with no such restrictions). Once created, a worker can send messages to the JavaScript code that created it by posting messages to an event handler specified by that code (and vice versa). This article provides a detailed introduction to using web workers.

Web Workers API
---------------

A worker is an object created using a constructor (e.g. [`Worker()`](../worker/worker)) that runs a named JavaScript file — this file contains the code that will run in the worker thread; workers run in another global context that is different from the current [`window`](../window). Thus, using the [`window`](../window) shortcut to get the current global scope (instead of [`self`](../window/self)) within a [`Worker`](../worker) will return an error.

The worker context is represented by a [`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope) object in the case of dedicated workers (standard workers that are utilized by a single script; shared workers use [`SharedWorkerGlobalScope`](../sharedworkerglobalscope)). A dedicated worker is only accessible from the script that first spawned it, whereas shared workers can be accessed from multiple scripts.

**Note**: See [The Web Workers API landing page](../web_workers_api) for reference documentation on workers and additional guides.

You can run whatever code you like inside the worker thread, with some exceptions. For example, you can't directly manipulate the DOM from inside a worker, or use some default methods and properties of the [`window`](../window) object. But you can use a large number of items available under `window`, including [WebSockets](../websockets_api), and data storage mechanisms like [IndexedDB](../indexeddb_api). See [Functions and classes available to workers](functions_and_classes_available_to_workers) for more details.

Data is sent between workers and the main thread via a system of messages — both sides send their messages using the `postMessage()` method, and respond to messages via the `onmessage` event handler (the message is contained within the `Message` event's data attribute.) The data is copied rather than shared.

Workers may, in turn, spawn new workers, as long as those workers are hosted within the same origin as the parent page. In addition, workers may use <a href="../xmlhttprequest" class="internal"><code>XMLHttpRequest</code></a> for network I/O, with the exception that the `responseXML` and `channel` attributes on `XMLHttpRequest` always return `null`.

Dedicated workers
-----------------

As mentioned above, a dedicated worker is only accessible by the script that called it. In this section we'll discuss the JavaScript found in our [Basic dedicated worker example](https://github.com/mdn/simple-web-worker) ([run dedicated worker](https://mdn.github.io/simple-web-worker/)): This allows you to enter two numbers to be multiplied together. The numbers are sent to a dedicated worker, multiplied together, and the result is returned to the page and displayed.

This example is rather trivial, but we decided to keep it simple while introducing you to basic worker concepts. More advanced details are covered later on in the article.

### Worker feature detection

For slightly more controlled error handling and backwards compatibility, it is a good idea to wrap your worker accessing code in the following ([main.js](https://github.com/mdn/simple-web-worker/blob/gh-pages/main.js)):

    if (window.Worker) {

      ...

    }

### Spawning a dedicated worker

Creating a new worker is simple. All you need to do is call the [`Worker()`](../worker/worker) constructor, specifying the URI of a script to execute in the worker thread ([main.js](https://github.com/mdn/simple-web-worker/blob/gh-pages/main.js)):

    var myWorker = new Worker('worker.js');

### Sending messages to and from a dedicated worker

The magic of workers happens via the [`postMessage()`](../worker/postmessage) method and the [`onmessage`](../worker/onmessage) event handler. When you want to send a message to the worker, you post messages to it like this ([main.js](https://github.com/mdn/simple-web-worker/blob/gh-pages/main.js)):

    first.onchange = function() {
      myWorker.postMessage([first.value, second.value]);
      console.log('Message posted to worker');
    }

    second.onchange = function() {
      myWorker.postMessage([first.value, second.value]);
      console.log('Message posted to worker');
    }

So here we have two [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) elements represented by the variables `first` and `second`; when the value of either is changed, `myWorker.postMessage([first.value,second.value])` is used to send the value inside both to the worker, as an array. You can send pretty much anything you like in the message.

In the worker, we can respond when the message is received by writing an event handler block like this ([worker.js](https://github.com/mdn/simple-web-worker/blob/gh-pages/worker.js)):

    onmessage = function(e) {
      console.log('Message received from main script');
      var workerResult = 'Result: ' + (e.data[0] * e.data[1]);
      console.log('Posting message back to main script');
      postMessage(workerResult);
    }

The `onmessage` handler allows us to run some code whenever a message is received, with the message itself being available in the `message` event's `data` attribute. Here we multiply together the two numbers then use `postMessage()` again, to post the result back to the main thread.

Back in the main thread, we use `onmessage` again, to respond to the message sent back from the worker:

    myWorker.onmessage = function(e) {
      result.textContent = e.data;
      console.log('Message received from worker');
    }

Here we grab the message event data and set it as the `textContent` of the result paragraph, so the user can see the result of the calculation.

**Note**: Notice that `onmessage` and `postMessage()` need to be hung off the `Worker` object when used in the main script thread, but not when used in the worker. This is because, inside the worker, the worker is effectively the global scope.

**Note**: When a message is passed between the main thread and worker, it is copied or "transferred" (moved), not shared. Read [Transferring data to and from workers: further details](#transferring_data_to_and_from_workers_further_details) for a much more thorough explanation.

### Terminating a worker

If you need to immediately terminate a running worker from the main thread, you can do so by calling the worker's [`terminate`](../worker) method:

    myWorker.terminate();

The worker thread is killed immediately.

### Handling errors

When a runtime error occurs in the worker, its `onerror` event handler is called. It receives an event named `error` which implements the `ErrorEvent` interface.

The event doesn't bubble and is cancelable; to prevent the default action from taking place, the worker can call the error event's <a href="../event/preventdefault" class="internal"><code>preventDefault()</code></a> method.

The error event has the following three fields that are of interest:

`message`  
A human-readable error message.

`filename`  
The name of the script file in which the error occurred.

`lineno`  
The line number of the script file on which the error occurred.

### Spawning subworkers

Workers may spawn more workers if they wish. So-called sub-workers must be hosted within the same origin as the parent page. Also, the URIs for subworkers are resolved relative to the parent worker's location rather than that of the owning page. This makes it easier for workers to keep track of where their dependencies are.

### Importing scripts and libraries

Worker threads have access to a global function, `importScripts()`, which lets them import scripts. It accepts zero or more URIs as parameters to resources to import; all of the following examples are valid:

    importScripts();                         /* imports nothing */
    importScripts('foo.js');                 /* imports just "foo.js" */
    importScripts('foo.js', 'bar.js');       /* imports two scripts */
    importScripts('//example.com/hello.js'); /* You can import scripts from other origins */

The browser loads each listed script and executes it. Any global objects from each script may then be used by the worker. If the script can't be loaded, `NETWORK_ERROR` is thrown, and subsequent code will not be executed. Previously executed code (including code deferred using [`WindowOrWorkerGlobalScope.setTimeout`](../windoworworkerglobalscope/settimeout)) will still be functional though. Function declarations **after** the `importScripts()` method are also kept, since these are always evaluated before the rest of the code.

**Note**: Scripts may be downloaded in any order, but will be executed in the order in which you pass the filenames into `importScripts()` . This is done synchronously; `importScripts()` does not return until all the scripts have been loaded and executed.

Shared workers
--------------

A shared worker is accessible by multiple scripts — even if they are being accessed by different windows, iframes or even workers. In this section we'll discuss the JavaScript found in our [Basic shared worker example](https://github.com/mdn/simple-shared-worker) ([run shared worker](https://mdn.github.io/simple-shared-worker/)): This is very similar to the basic dedicated worker example, except that it has two functions available handled by different script files: *multiplying two numbers*, or *squaring a number*. Both scripts use the same worker to do the actual calculation required.

Here we'll concentrate on the differences between dedicated and shared workers. Note that in this example we have two HTML pages, each with JavaScript applied that uses the same single worker file.

**Note**: If SharedWorker can be accessed from several browsing contexts, all those browsing contexts must share the exact same origin (same protocol, host, and port).

**Note**: In Firefox, shared workers cannot be shared between documents loaded in private and non-private windows ([bug 1177621](https://bugzilla.mozilla.org/show_bug.cgi?id=1177621)).

### Spawning a shared worker

Spawning a new shared worker is pretty much the same as with a dedicated worker, but with a different constructor name (see [index.html](https://github.com/mdn/simple-shared-worker/blob/gh-pages/index.html) and [index2.html](https://github.com/mdn/simple-shared-worker/blob/gh-pages/index2.html)) — each one has to spin up the worker using code like the following:

    var myWorker = new SharedWorker('worker.js');

One big difference is that with a shared worker you have to communicate via a `port` object — an explicit port is opened that the scripts can use to communicate with the worker (this is done implicitly in the case of dedicated workers).

The port connection needs to be started either implicitly by use of the `onmessage` event handler or explicitly with the `start()` method before any messages can be posted. Calling `start()` is only needed if the `message` event is wired up via the `addEventListener()` method.

**Note**: When using the `start()` method to open the port connection, it needs to be called from both the parent thread and the worker thread if two-way communication is needed.

### Sending messages to and from a shared worker

Now messages can be sent to the worker as before, but the `postMessage()` method has to be invoked through the port object (again, you'll see similar constructs in both [multiply.js](https://github.com/mdn/simple-shared-worker/blob/gh-pages/multiply.js) and [square.js](https://github.com/mdn/simple-shared-worker/blob/gh-pages/square.js)):

    squareNumber.onchange = function() {
      myWorker.port.postMessage([squareNumber.value,squareNumber.value]);
      console.log('Message posted to worker');
    }

Now, on to the worker. There is a bit more complexity here as well ([worker.js](https://github.com/mdn/simple-shared-worker/blob/gh-pages/worker.js)):

    onconnect = function(e) {
      var port = e.ports[0];

      port.onmessage = function(e) {
        var workerResult = 'Result: ' + (e.data[0] * e.data[1]);
        port.postMessage(workerResult);
      }
    }

First, we use an `onconnect` handler to fire code when a connection to the port happens (i.e. when the `onmessage` event handler in the parent thread is setup, or when the `start()` method is explicitly called in the parent thread).

We use the `ports` attribute of this event object to grab the port and store it in a variable.

Next, we add a `message` handler on the port to do the calculation and return the result to the main thread. Setting up this `message` handler in the worker thread also implicitly opens the port connection back to the parent thread, so the call to `port.start()` is not actually needed, as noted above.

Finally, back in the main script, we deal with the message (again, you'll see similar constructs in both [multiply.js](https://github.com/mdn/simple-shared-worker/blob/gh-pages/multiply.js) and [square.js](https://github.com/mdn/simple-shared-worker/blob/gh-pages/square.js)):

    myWorker.port.onmessage = function(e) {
      result2.textContent = e.data;
      console.log('Message received from worker');
    }

When a message comes back through the port from the worker, we insert the calculation result inside the appropriate result paragraph.

About thread safety
-------------------

The [`Worker`](../worker) interface spawns real OS-level threads, and mindful programmers may be concerned that concurrency can cause “interesting” effects in your code if you aren't careful.

However, since web workers have carefully controlled communication points with other threads, it's actually very hard to cause concurrency problems. There's no access to non-threadsafe components or the DOM. And you have to pass specific data in and out of a thread through serialized objects. So you have to work really hard to cause problems in your code.

Content security policy
-----------------------

Workers are considered to have their own execution context, distinct from the document that created them. For this reason they are, in general, not governed by the [content security policy](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/Content_Security_Policy) of the document (or parent worker) that created them. So for example, suppose a document is served with the following header:

    Content-Security-Policy: script-src 'self'

Among other things, this will prevent any scripts it includes from using `eval()`. However, if the script constructs a worker, code running in the worker's context *will* be allowed to use `eval()`.

To specify a content security policy for the worker, set a [Content-Security-Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy) response header for the request which delivered the worker script itself.

The exception to this is if the worker script's origin is a globally unique identifier (for example, if its URL has a scheme of data or blob). In this case, the worker does inherit the CSP of the document or worker that created it.

Transferring data to and from workers: further details
------------------------------------------------------

Data passed between the main page and workers is **copied**, not shared. Objects are serialized as they're handed to the worker, and subsequently, de-serialized on the other end. The page and worker **do not share the same instance**, so the end result is that **a duplicate** is created on each end. Most browsers implement this feature as [structured cloning](structured_clone_algorithm).

To illustrate this, let's create for didactical purpose a function named `emulateMessage()`, which will simulate the behavior of a value that is *cloned and not shared* during the passage from a `worker` to the main page or vice versa:

    function emulateMessage(vVal) {
        return eval('(' + JSON.stringify(vVal) + ')');
    }

    // Tests

    // test #1
    var example1 = new Number(3);
    console.log(typeof example1); // object
    console.log(typeof emulateMessage(example1)); // number

    // test #2
    var example2 = true;
    console.log(typeof example2); // boolean
    console.log(typeof emulateMessage(example2)); // boolean

    // test #3
    var example3 = new String('Hello World');
    console.log(typeof example3); // object
    console.log(typeof emulateMessage(example3)); // string

    // test #4
    var example4 = {
        'name': 'John Smith',
        "age": 43
    };
    console.log(typeof example4); // object
    console.log(typeof emulateMessage(example4)); // object

    // test #5
    function Animal(sType, nAge) {
        this.type = sType;
        this.age = nAge;
    }
    var example5 = new Animal('Cat', 3);
    alert(example5.constructor); // Animal
    alert(emulateMessage(example5).constructor); // Object

A value that is cloned and not shared is called *message*. As you will probably know by now, *messages* can be sent to and from the main thread by using `postMessage()`, and the `message` event's [`data`](../messageevent/data) attribute contains data passed back from the worker.

**example.html**: (the main page):

    var myWorker = new Worker('my_task.js');

    myWorker.onmessage = function(oEvent) {
      console.log('Worker said : ' + oEvent.data);
    };

    myWorker.postMessage('ali');

**my\_task.js** (the worker):

    postMessage("I\'m working before postMessage(\'ali\').");

    onmessage = function(oEvent) {
      postMessage('Hi ' + oEvent.data);
    };

The [structured cloning](structured_clone_algorithm) algorithm can accept JSON and a few things that JSON can't — like circular references.

### Passing data examples

#### Example \#1: Advanced passing JSON Data and creating a switching system

If you have to pass some complex data and have to call many different functions both on the main page and in the Worker, you can create a system which groups everything together.

First, we create a `QueryableWorker` class that takes the URL of the worker, a default listener, and an error handler, and this class is going to keep track of a list of listeners and help us communicate with the worker:

    function QueryableWorker(url, defaultListener, onError) {
        var instance = this,
            worker = new Worker(url),
            listeners = {};

        this.defaultListener = defaultListener || function() {};

        if (onError) {worker.onerror = onError;}

        this.postMessage = function(message) {
            worker.postMessage(message);
        }

        this.terminate = function() {
            worker.terminate();
        }
    }

Then we add the methods of adding/removing listeners:

    this.addListeners = function(name, listener) {
        listeners[name] = listener;
    }

    this.removeListeners = function(name) {
        delete listeners[name];
    }

Here we let the worker handle two simple operations for illustration: getting the difference of two numbers and making an alert after three seconds. In order to achieve that we first implement a `sendQuery` method which queries if the worker actually has the corresponding methods to do what we want.

    /*
      This functions takes at least one argument, the method name we want to query.
      Then we can pass in the arguments that the method needs.
     */
    this.sendQuery = function() {
        if (arguments.length < 1) {
             throw new TypeError('QueryableWorker.sendQuery takes at least one argument');
             return;
        }
        worker.postMessage({
            'queryMethod': arguments[0],
            'queryArguments': Array.prototype.slice.call(arguments, 1)
        });
    }

We finish QueryableWorker with the `onmessage` method. If the worker has the corresponding methods we queried, it should return the name of the corresponding listener and the arguments it needs, we just need to find it in `listeners`.:

    worker.onmessage = function(event) {
        if (event.data instanceof Object &&
            event.data.hasOwnProperty('queryMethodListener') &&
            event.data.hasOwnProperty('queryMethodArguments')) {
            listeners[event.data.queryMethodListener].apply(instance, event.data.queryMethodArguments);
        } else {
            this.defaultListener.call(instance, event.data);
        }
    }

Now onto the worker. First we need to have the methods to handle the two simple operations:

    var queryableFunctions = {
        getDifference: function(a, b) {
            reply('printStuff', a - b);
        },
        waitSomeTime: function() {
            setTimeout(function() {
                reply('doAlert', 3, 'seconds');
            }, 3000);
        }
    }

    function reply() {
        if (arguments.length < 1) {
            throw new TypeError('reply - takes at least one argument');
            return;
        }
        postMessage({
            queryMethodListener: arguments[0],
            queryMethodArguments: Array.prototype.slice.call(arguments, 1)
        });
    }

    /* This method is called when main page calls QueryWorker's postMessage method directly*/
    function defaultReply(message) {
        // do something
    }

And the `onmessage` method is now trivial:

    onmessage = function(event) {
        if (event.data instanceof Object &&
            event.data.hasOwnProperty('queryMethod') &&
            event.data.hasOwnProperty('queryMethodArguments')) {
            queryableFunctions[event.data.queryMethod]
                .apply(self, event.data.queryMethodArguments);
        } else {
            defaultReply(event.data);
        }
    }

Here are the full implementation:

**example.html** (the main page):

    <!doctype html>
      <html>
        <head>
          <meta charset="UTF-8"  />
          <title>MDN Example - Queryable worker</title>
        <script type="text/javascript">
        /*
          QueryableWorker instances methods:
            * sendQuery(queryable function name, argument to pass 1, argument to pass 2, etc. etc): calls a Worker's queryable function
            * postMessage(string or JSON Data): see Worker.prototype.postMessage()
            * terminate(): terminates the Worker
            * addListener(name, function): adds a listener
            * removeListener(name): removes a listener
          QueryableWorker instances properties:
            * defaultListener: the default listener executed only when the Worker calls the postMessage() function directly
         */
        function QueryableWorker(url, defaultListener, onError) {
          var instance = this,
          worker = new Worker(url),
          listeners = {};

          this.defaultListener = defaultListener || function() {};

          if (onError) {worker.onerror = onError;}

          this.postMessage = function(message) {
            worker.postMessage(message);
          }

          this.terminate = function() {
            worker.terminate();
          }

          this.addListener = function(name, listener) {
            listeners[name] = listener;
          }

          this.removeListener = function(name) {
            delete listeners[name];
          }

          /*
            This functions takes at least one argument, the method name we want to query.
            Then we can pass in the arguments that the method needs.
          */
          this.sendQuery = function() {
            if (arguments.length < 1) {
              throw new TypeError('QueryableWorker.sendQuery takes at least one argument');
              return;
            }
            worker.postMessage({
              'queryMethod': arguments[0],
              'queryMethodArguments': Array.prototype.slice.call(arguments, 1)
            });
          }

          worker.onmessage = function(event) {
            if (event.data instanceof Object &&
              event.data.hasOwnProperty('queryMethodListener') &&
              event.data.hasOwnProperty('queryMethodArguments')) {
              listeners[event.data.queryMethodListener].apply(instance, event.data.queryMethodArguments);
            } else {
              this.defaultListener.call(instance, event.data);
            }
          }
        }

        // your custom "queryable" worker
        var myTask = new QueryableWorker('my_task.js');

        // your custom "listeners"
        myTask.addListener('printStuff', function (result) {
          document.getElementById('firstLink').parentNode.appendChild(document.createTextNode('The difference is ' + result + '!'));
        });

        myTask.addListener('doAlert', function (time, unit) {
          alert('Worker waited for ' + time + ' ' + unit + ' :-)');
        });
    </script>
    </head>
    <body>
      <ul>
        <li><a id="firstLink" href="javascript:myTask.sendQuery('getDifference', 5, 3);">What is the difference between 5 and 3?</a></li>
        <li><a href="javascript:myTask.sendQuery('waitSomeTime');">Wait 3 seconds</a></li>
        <li><a href="javascript:myTask.terminate();">terminate() the Worker</a></li>
      </ul>
    </body>
    </html>

**my\_task.js** (the worker):

    var queryableFunctions = {
      // example #1: get the difference between two numbers:
      getDifference: function(nMinuend, nSubtrahend) {
          reply('printStuff', nMinuend - nSubtrahend);
      },
      // example #2: wait three seconds
      waitSomeTime: function() {
          setTimeout(function() { reply('doAlert', 3, 'seconds'); }, 3000);
      }
    };

    // system functions

    function defaultReply(message) {
      // your default PUBLIC function executed only when main page calls the queryableWorker.postMessage() method directly
      // do something
    }

    function reply() {
      if (arguments.length < 1) { throw new TypeError('reply - not enough arguments'); return; }
      postMessage({ 'queryMethodListener': arguments[0], 'queryMethodArguments': Array.prototype.slice.call(arguments, 1) });
    }

    onmessage = function(oEvent) {
      if (oEvent.data instanceof Object && oEvent.data.hasOwnProperty('queryMethod') && oEvent.data.hasOwnProperty('queryMethodArguments')) {
        queryableFunctions[oEvent.data.queryMethod].apply(self, oEvent.data.queryMethodArguments);
      } else {
        defaultReply(oEvent.data);
      }
    };

It is possible to switch the content of each mainpage -&gt; worker and worker -&gt; mainpage message. And the property names "queryMethod", "queryMethodListeners", "queryMethodArguments" can be anything as long as they are consistent in `QueryableWorker` and the `worker`.

### Passing data by transferring ownership (transferable objects)

Google Chrome 17+ and Firefox 18+ contain an additional way to pass certain types of objects (transferable objects, that is objects implementing the [`Transferable`](../transferable) interface) to or from a worker with high performance. Transferable objects are transferred from one context to another with a zero-copy operation, which results in a vast performance improvement when sending large data sets. Think of it as pass-by-reference if you're from the C/C++ world. However, unlike pass-by-reference, the 'version' from the calling context is no longer available once transferred. Its ownership is transferred to the new context. For example, when transferring an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) from your main app to a worker script, the original [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) is cleared and no longer usable. Its content is (quite literally) transferred to the worker context.

    // Create a 32MB "file" and fill it.
    var uInt8Array = new Uint8Array(1024 * 1024 * 32); // 32MB
    for (var i = 0; i < uInt8Array.length; ++i) {
      uInt8Array[i] = i;
    }

    worker.postMessage(uInt8Array.buffer, [uInt8Array.buffer]);

**Note**: For more information on transferable objects, performance, and feature-detection for this method, read [Transferable Objects: Lightning Fast!](https://updates.html5rocks.com/2011/12/Transferable-Objects-Lightning-Fast) on HTML5 Rocks.

Embedded workers
----------------

There is not an "official" way to embed the code of a worker within a web page, like [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) elements do for normal scripts. But a [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) element that does not have a `src` attribute and has a `type` attribute that does not identify an executable MIME type can be considered a data block element that JavaScript could use. "Data blocks" is a more general feature of HTML5 that can carry almost any textual data. So, a worker could be embedded in this way:

    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="UTF-8" />
    <title>MDN Example - Embedded worker</title>
    <script type="text/js-worker">
      // This script WON'T be parsed by JS engines because its MIME type is text/js-worker.
      var myVar = 'Hello World!';
      // Rest of your worker code goes here.
    </script>
    <script type="text/javascript">
      // This script WILL be parsed by JS engines because its MIME type is text/javascript.
      function pageLog(sMsg) {
        // Use a fragment: browser will only render/reflow once.
        var oFragm = document.createDocumentFragment();
        oFragm.appendChild(document.createTextNode(sMsg));
        oFragm.appendChild(document.createElement('br'));
        document.querySelector('#logDisplay').appendChild(oFragm);
      }
    </script>
    <script type="text/js-worker">
      // This script WON'T be parsed by JS engines because its MIME type is text/js-worker.
      onmessage = function(oEvent) {
        postMessage(myVar);
      };
      // Rest of your worker code goes here.
    </script>
    <script type="text/javascript">
      // This script WILL be parsed by JS engines because its MIME type is text/javascript.

      // In the past...:
      // blob builder existed
      // ...but now we use Blob...:
      var blob = new Blob(Array.prototype.map.call(document.querySelectorAll('script[type=\'text\/js-worker\']'), function (oScript) { return oScript.textContent; }),{type: 'text/javascript'});

      // Creating a new document.worker property containing all our "text/js-worker" scripts.
      document.worker = new Worker(window.URL.createObjectURL(blob));

      document.worker.onmessage = function(oEvent) {
        pageLog('Received: ' + oEvent.data);
      };

      // Start the worker.
      window.onload = function() { document.worker.postMessage(''); };
    </script>
    </head>
    <body><div id="logDisplay"></div></body>
    </html>

The embedded worker is now nested into a new custom `document.worker` property.

It is also worth noting that you can also convert a function into a Blob, then generate an object URL from that blob. For example:

    function fn2workerURL(fn) {
      var blob = new Blob(['('+fn.toString()+')()'], {type: 'text/javascript'})
      return URL.createObjectURL(blob)
    }

Further examples
----------------

This section provides further examples of how to use web workers.

### Performing computations in the background

Workers are mainly useful for allowing your code to perform processor-intensive calculations without blocking the user interface thread. In this example, a worker is used to calculate Fibonacci numbers.

#### The JavaScript code

The following JavaScript code is stored in the "fibonacci.js" file referenced by the HTML in the next section.

    var results = [];

    function resultReceiver(event) {
      results.push(parseInt(event.data));
      if (results.length == 2) {
        postMessage(results[0] + results[1]);
      }
    }

    function errorReceiver(event) {
      throw event.data;
    }

    onmessage = function(event) {
      var n = parseInt(event.data);

      if (n == 0 || n == 1) {
        postMessage(n);
        return;
      }

      for (var i = 1; i <= 2; i++) {
        var worker = new Worker('fibonacci.js');
        worker.onmessage = resultReceiver;
        worker.onerror = errorReceiver;
        worker.postMessage(n - i);
      }
     };

The worker sets the property `onmessage` to a function which will receive messages sent when the worker object's `postMessage()` is called (note that this differs from defining a global *variable* of that name, or defining a *function* with that name. `var onmessage` and `function onmessage` will define global properties with those names, but they will not register the function to receive messages sent by the web page that created the worker). This starts the recursion, spawning new copies of itself to handle each iteration of the calculation.

#### The HTML code

    <!DOCTYPE html>
    <html>
      <head>
        <meta charset="UTF-8"  />
        <title>Test threads fibonacci</title>
      </head>
      <body>

      <div id="result"></div>

      <script language="javascript">

        var worker = new Worker('fibonacci.js');

        worker.onmessage = function(event) {
          document.getElementById('result').textContent = event.data;
          dump('Got: ' + event.data + '\n');
        };

        worker.onerror = function(error) {
          dump('Worker error: ' + error.message + '\n');
          throw error;
        };

        worker.postMessage('5');

      </script>
      </body>
    </html>

The web page creates a `div` element with the ID `result` , which gets used to display the result, then spawns the worker. After spawning the worker, the `onmessage` handler is configured to display the results by setting the contents of the `div` element, and the `onerror` handler is set to [dump](https://developer.mozilla.org/en-US/docs/Debugging_JavaScript#dump.28.29) the error message.

Finally, a message is sent to the worker to start it.

[Try this example live](https://mdn.github.io/fibonacci-worker/).

### Performing web I/O in the background

You can find an example of this in the article <a href="https://developer.mozilla.org/en-US/docs/Using_workers_in_extensions" class="internal">Using workers in extensions</a> .

### Dividing tasks among multiple workers

As multi-core computers become increasingly common, it's often useful to divide computationally complex tasks among multiple workers, which may then perform those tasks on multiple-processor cores.

Other types of worker
---------------------

In addition to dedicated and shared web workers, there are other types of worker available:

-   [ServiceWorkers](../service_worker_api) essentially act as proxy servers that sit between web applications, and the browser and network (when available). They are intended to (amongst other things) enable the creation of effective offline experiences, intercepting network requests and taking appropriate action based on whether the network is available and updated assets reside on the server. They will also allow access to push notifications and background sync APIs.
-   Chrome Workers are a Firefox-only type of worker that you can use if you are developing add-ons and want to use workers in extensions and have access to [js-ctypes](https://developer.mozilla.org/en-US/js-ctypes) in your worker. See <span class="page-not-created">`ChromeWorker`</span> for more details.
-   [Audio Worklet](../web_audio_api#audio_processing_in_javascript) provide the ability for direct scripted audio processing to be done in a worklet (a lightweight version of worker) context.

Debugging worker threads
------------------------

Most browsers support debugging of worker threads in their JavaScript debuggers in *exactly the same way* as debugging the main thread! For example, both Firefox and Chrome list JavaScript source files for both the main thread and active worker threads, and all of these files can be opened to set breakpoints and logpoints.

The screenshot below shows this on Firefox. The *sources list* shows `worker.js` running in a separate worker thread. When selected this file is opened in the [source pane](https://developer.mozilla.org/en-US/docs/Tools/Debugger/UI_Tour#source_pane), just like code running in the main thread.

<img src="data:image/png;base64,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" width="900" height="323" />

**Note**: Worker scripts are loaded when needed, and hence may not be present in the sources list when a page is first loaded.

In the source pane you can [set a breakpoint](https://developer.mozilla.org/en-US/docs/Tools/Debugger/How_to/Set_a_breakpoint) (or [logpoint](https://developer.mozilla.org/en-US/docs/Tools/Debugger/Set_a_logpoint)) in a worker thread in the normal way. When execution is paused, the context of the debugger is updated to show correct [breakpoints](https://developer.mozilla.org/en-US/docs/Tools/Debugger/How_to/Set_a_breakpoint), [inline variable preview](https://developer.mozilla.org/en-US/docs/Tools/Debugger/How_to/Set_a_breakpoint#inline_variable_preview), [call stack](https://developer.mozilla.org/en-US/docs/Tools/Debugger/UI_Tour#call_stack), etc., just as you'd expect.

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABEwAAAFRCAMAAABZr8hqAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAJwUExURUdwTP74/+jo6v7///n5+gBy8Pv8+/////////////fm/+Li5Pj4+enp6uzs7fz0/+Xl5wBu8ff39/Hx8eDg4vT09f/7//i/M+Ly/6PN5/z8/QGC/wBq7/TZ/8jh8MLCwv/+/wE5se7v71Og9Wyu967T6eHh4/Pz8/39/uXl5sjIyf3w/7TW6gJ//67D6dvb3MPDxGlpavLR/wCNAfMEr9vt//L3/dPT04sA3z8/QgAwrUhIS/X6/i0tMDc3OnFxcvr8/whBtNvl9qurrf//+3p6fO3y+wgICLm5ukRyyBKA8pWw4RBJt5IF4lBQUlhYWiyO9Ofu+vno/wN18R6H85KSlLnb/JkT5LLL6b+/v6zT+/7o/eHq+Oz2/5mZmvTd/6Ut5yVavi9hwdHo/lKp+wFb6AZ688za8W6U1TdoxISEhWWL0p+foRtSu/Xi/dPg84mJi6SkpcTU77KytMzj/KAh5hUVFhiG/19fYtWi8ni4+fUYuFyDz0Gb9fe9LKzb/83NzpDF+/2m5oS/+rhX7LFI6jWW9sPh/Y2Nj3qc2LzO7OT5/+C29tCR86zL6crszlJ8zIKj24qp3e/W+/yM3WKm9Ks46ae+5g6ZEqLR/PYvwJ+75G8DrsN18dyr9qDI+f/e9+fC+MyC8r5l7h5z6+vM+v/O8q7fskih95fL+2Sz+IYhvOz57vph0Ym/7iSjKP687Y/SlCAgIbrjvaHYpDWsO+6eR/dDxk22UcWN4vlUzfty19/z4mbCbOyNAuh+Batf0n3Jgf3z5bZz2fjIT/GjD9jS/OzWrNTd6EKL7ZtEyf/78+h4APfKf/zmvuXZvNXymo4AAAAJdFJOUwD///////+tFf9Qr2QAACAASURBVHja7J3Pa+LcGscHEx4IRilRN+HlDmipUbhoFrcSwiSgR3GV4MJyFcnqDYII/WEXUnjBYRZT7uLuunZzFu/Kv+PK+0/dkxOtbcfEzNx53/ba51PGiSZOp3rOx+9zck76IZ8+SUbq5p+vwH9SJwjyLYnbLfKX8SGfg2SQX//+CnwmgCDfIOdT+CK8NQKZiIkgv7+OTEQE+QaFyQRfhTfGd8jky69/Pb9fYJNBUCbHJhORvAbYYhCUyfHJBEFQJgjKBEGZICgTBEGZoEwQ5B3JBKR31pcAZYKgTP6UrpWbpdR35RIZomWiSi/RsNkir4UmvESLlgkIws+0y64rCMmfk3L07DvqMVBoz7QomUC++pIaxhbktdrqovWEWUAjUiYgL6qQMBaAwD8n45o2pOvbLtCQE/cBdWC8J5sIntUVImQCRd0yDMsyjR1u5cdyGyE/tg9Btj2zZhrmDsMKmmNNjZCJULesq2ySFAFSsd6fTKaLghTmn32u0KabDmBaTjb5B6pUfUc2kT5anhRV5qgV577bMieZdGVDqmtUpR/6Rsth9Js5XHX2vT2P89MAZYOwtjowuvnalrN7czq7dxdalEymZt9wG4dHQEFsuZajz01r/lEFEZRGec9zoBx2gnTm3sx8RzrXmE0yR2wTkAQtRNRqpq1AtEzcfrVr3ksqA1SWA5lof0wmQKkctatD/Ruy5+HVOHyUDFcydiVE6hrMDQJrhgGS58yqnttQo2WSXbhGSz7Qk6F8ZdnVbKGc6c4tj1U8VXOxL8+AGiJ5yWQCmz523NkElI9e32P0vZSsm2lJjZNJPZAJvwO1XLxM4MUNwPZhtsllAk93wPa+eLcewe747Tcf+/Qr4S7xaQ9HahAmk4UGJ40C75pMJq16vExSUmZi2WkpPpdMrJkqcD0V+panaZP4MiahTCC7jVD5a8s+2ikw4BlOyET2jLowawgJZCJlJ0a7ECeT806QH8Kbc+aAzqgX6EFmJcyow2TCvvN5r8Nqlt7onPCDSK8XRo7gdnv8jhW3CVlSf4kuQbhMpKxutGvBqEYSmbA0MTOdbtzIqtS1WttSCATPqqZML/bjciMTiG+SAFePw4ym8ck70miiZp2rXDEboA6sqaTYZk06JBMW/lxTd2oxMvnjgg4JDOmKwC27kVf0F3rK9HBBv5T8O8KSCRmtmR16p/SXNbODvC6tKI8chCeTJTv+ofn0LSJ3Pv0bGTKX4JgJspFJw7EdZ1ZQk8mElfQ13fLKWnRM1/Wwzg/ml0F5bk+NRuTRORU2MlGVAsQHnvZ8e9qpb+2GiY9NJhn3WgqrzopjK6BW5k5NiJcJZPvGfDaNlQm58E9VUvLXIlmx7v/g0xL11x1WpPh0vWQy0UbUv4PO2l+zHStyTn1//cBlUvJv2XNoae0/H1gJHrxDlyDPZDKd2UY7D8lkwv4uTK15pB+EmtHlDRqK1ZQkSDPDtMUITbDucC0Al4lQmU+1AzKZbKalZOZuXhCPWCahlG0nzV4RIe8+tck+magT62pQ9WJlAh1KOx3q01vyQJtffdojcolJY+jTJgnGTJqBQsjSLxHSZJFEDizBNcFlsva/EnL62whe2MRneQf7EbKTiVcfeOaknFQmLHIsXOcsIhpoXaPGraAtTHNSzZ0ZVleKTDFX1kwKZCKl5mZDPSCTNv93WO9y85J45DIBoW/Vw5+35jq7l2ZvMmkb03o9XiaBE0Zj/zd/eU7X5DTIE+QrM8fQPyX8bE7gEpFJYzke35b8C5FS8vhEJiB/vey9PAfMZXKLMkE2MmlwmXQnRl9JLBNRqugbY+xJJi1zM9yqNDzHctumGz38CsqE5RjPzBZ1sxEviK1MhLTrpo/WJY8ykQaWF+YRragbdS02mdRYshxMD8hk6S8/+5e01GT6ePDHRIQmXYtD/47LxA+HU9d+yBCey6QZ7FjfvAwmdL05p4OgTEKZTFtzs59JXOao6sA0u1ExAtL1x5AilAcT89M0piRRC7ZRnTp526gfEMRGJurZEdc4O5lo6e0MEzVnG4P4MkfU5GvDbcfLBEb+w5pCid75N0wm/2LmuPXX6lYmtOTTEQTJ5ObmZjzunIcyAQhlQsTLFRPH0xHYwCVLeECbILsyp+bopl5XIOEArCjl7i07pj/Dk10gaSfVYtzAqlq0Td3RjcGhsBHKBLKue3bELtnIJBgwqfCz65rSfvba7D81DFJDt/Ri7DwTeU3pHcsnlI7CoRFmg1PyKBNW+qzP2c0XtuNi2dvI5LIDgUzk4ZA9XHo62AqBSwiIgU3w1DDCZSLkJo5XUZOeGmbNdm5MlcP9WdrMtoIDiwO1nP3JMroHC5etTKa1Y3YJk4njgRycUZdEWZah/NwlkZPWhHI9HT9pjYnCH5Im9UsA5+x2eefTy51MmGz8h2Ds9W7I/NBRApmw3FKSuUzWfuliRentbpFh0+dq4TbBSWsIL3MEKKYU3u8TTVpTWKBeJFk83GonPHurVXSjJSSYo28HZQ5ox30FAhAnxpUczDCp2bqu2y5zCUTLhE+n52eSD06n/+OCOSIoZJg94Jb6/EwM+fdWJjL5B/U/B3PQ2I4x4cmEfA7SSlDm3PCHP+/+J9B5CGMKiHcP59iVED5mokmbxSDS9OB0+mKqbU0yCaIBpMxPk0OCCH8TjKilq4+/Fibu6FbrPazvg6I3CAZM1GumElu3P8Ys9OPJ5Eosb5E/xq3NkS+DIY/mZSeIKZ3x8GbEbNC57AX7ms1gVOWyKZLezXLcI8HBQRMY83GUW0J64yU//knS2d7DK9IjIl/oN6vtuDK91iRWJi3HnKlJogGUbXN2cA0PRw1GWUDm28redsnSCENjpZiq8Y3jtokk605alZXw3osf9qlMsq7hOJYxdx9xzLg4yHv9dukNkOd3t9vB4yDuFur0VryMAfw1Fkh8gZ6em84O0zQdU09DlEy6nyy9lvCyiZDLi/FHqrOwA8yEwCsTvq3vPeGcClfkKCBXwuXNylG/K0Kf54v9We3ZxZEW/av7+/urHf36d3T4RGt9g1ltYT2DS4OR+C5fqz+lyv7kH3d+c3Gk8mxWSDz6CYdqEqiGHWChBvNNrsPOsG/FH7QtviCnJuR0vuVUjvkzUuta0+ha5dllGwVBfY7w0yfgAKuDMJEgidrKS1SIlAkL4D/1as5qWL1ou0pG3buAENINTgHkWrh1zMkExHtbgWQy+YuaCHYT5H/lzVxQOryQicr9s906YpuU4ybm4NXpEZQJ8lOiAMoEQZkgPwWUCYIyQVAmCMoEQZkgCMoEZYIgKBMEZYKgTJA/USYI8v+GzGSCvDE+5E9SychkUgjyVsinsxnklXlhiA/pbELOUlkEeSvkkdfmLPVcLScfUlJCKoqEIG8ELX+iKAX8es2vjPK4aEpV2W3uO2RSwCaMvBVUHIB9beRMYbsZXo0AZYKgTP7L3vm+Jo6tcRwbN3A6re5oGxbZodILo9UXqZC9JkjsBZEjAzGlWzd0ZdvALvtCpLSIoV1Z6BXd9UX7qt68CFj8QYe9C4XiG8H+c/c5ia3aTju73cLg3vPIJEfPc5IO5Hz4Ps+T5FB7NkxY58OSLYUJNQoTas+FCUuVCTUKE2pUmVCjRmFClQk1ahQmVJlQmFCjMKH2N1AmXDT6h32DLu7RvuXG+vT3XOSBDxNPqyU6V/8fYPL0QjgUVS+uTNh4Jv6JYeK6sSpD7mmfaP7WIW81H/VKJePTF2Q667/v40kkDk7oXJ11mIQdpycnw/ITr35m/T5KkxdWJvHcRuzwE8OkKlg3zeDTPk3h/ajVFoaPOYWy6Xu/8MnD+04nD3+iNnsw4UuZTGaHDz/uwy5vHDy62grLS4VJEgUClB1/VZmw6fTuxqeGyY2Q/6jPGCYo/2hIVJLvRzXu2NH9/1QkmaEzdeZhgg4wMaPwuL5gQ3L20V4mYsQm+MGmDlapUPmLyoTNLK49gInr2NTrHYSCZ72Lut6Loje1nt4702swi6NdU6/tgdNWS9fNY9AT3jNTN7tehC5rul4/HY3vdlsQl8yDU+vpdAh3ZVUEy7oKopsrApYrDlUH1wNr2Ca90LBuoqhp+1jAk/fDwbBqj2ta1uAa9jc3VfBxkWxIWlq0j/nVD5ub//nKbuZk/l7KhMJkBmHC3l8OGBXwYWQ9lcSHjJth7CV1WAYhW6iQBvkeShKYMNAkq2qPVt0hDXutHN4z/p1FMXkVjTopVJ5fzXn7ACZdsdzTFMBCTdRqpthCHUXTRcUUuyhqivWaou8jpi7WWqYJwGiJZquuvUGopwFzxAuEzsh4UfeifV2p1RTTe3cuX3G0juDiGCbNYUUYDm84ZFXg66ASBaVSGQwEkkWpCpWrgVBFzaElDIZDByZOmNMUrKuKcI1cllCBXpJHCakx1mbJ9utffnm9+R1pZ+T7ydaMvENn6ozBZGH51m6lBsCEpMciOIbcKztzqZwnvLCe2z0h1zwbyR2UVgMOTAI7h299pfhqqZEJgRQJ+zONYjzMsqulOOsrnaylGpll1l9K9HczvkAo08hFaGb2+dWcpfsw2SqX59GlUudQTzxD3nIZdcTjPaXm1WrAiS5CF7DZ10wAwT6DXKY2j9A+AOM8SsaanFfX9tGpCAxpOWi5uDuXP5awLTslF64qRLwELesOJjdB16DSRvkKbILv2zY7ru9yJkTBQFcevRcGHEdg0xbI2EXJSZn88PrfDPPTl/+1c0LJ3clThfnIUeIVnakzBpP14uHIUqNoZASTdVxAvqycxMbb5Rg2DKPhZn1pCH9wdjEMMFlARax6FvtHCcOABhvmE9AHXgxvpJFfTiQNjGMLvAxDEiGPCofABTelyYspkw4BBlcHRtQUEBy1sqsjnnJKl9NrqC72Wq2eYqKoph13iOQAidLtbDkDz1otTeMulRYEP2Xd6zIV8K6BtBnXav22hcIfhEnwFibvnSRJVWiOcybTMLkmXdygkif/ULBCYDLnwOS77c9+++0fm1/+bMNEyk2VclQ5QaOcGYMJ6wbBMPoUPXcw2d3J7MrSq7Avi7MRnm3g9Fs+izNova/yawd4F4WSKrDkaJWZ6+Mjnt/ABcat4sZSPItLyIEJTvPxBF5nX6lyfI7ZxY05PivzYcqRl1ImF+IxbGvKOaqBxICN14FJEGBiijqxHkLHZVHUiWNHV8Ryy0XiHU3XFY07BT0DgkV3bWmK7d0dJyw8ozc2sdMwsROwE8qkjRgCkzFBgvdhUhVI5uRKaAODXIizYeJJbJBzfP/j19vb25ubvzvp1qnajZtfySbm6EydLWXCrqYaOcf4wF0CFkQExoVQwJftLyEGVAZcVEtGDHl4aLzqbzAAk6Kh+sPsnCFDXB1KyqE49DMAEnUEE9nHoAxwh4nJHgTHLLpRKE7fmfxyysSGAaoDSO7DpI7qyhYKBu0yrve0qygkFctdnpXFU3Su1EFgmLfKRNe93rIZRMHJmq//SJKcJeU/AJPBWJm0b5VJ9UllgoZCmxvDxB1TQ7D74t32P++OnXpQ4CnKK3SmzliYc0eTW5YQZVKM7JQ2cMy3kEj6IX7py1kwLAErDtSshAEmUh/LHsYNMDlCMGQDr2XwIcmzSjLrwEQNuMNxnENsTJ4LhOMyTm5k3LRK/Gxl8qCa80YzOTSvmd4PwKQl2uUaL+LIPWQtsYM4Ukc5Bv50SDhzqWneaFmPokvR9AZryqXjfWsLqd0ifHaLng/AZAi7dmVSmZCcCIyPTsIkmCcwCbZJV75iuSZgghrJJdj+6+fXv5JoxyZKQVqjpeHZr+aE54qEJpG7eT7KmQRUHGcJTJh4X1bBjgrMTt+QVNUgMMEybiB2DJOlDE4RmCRktwOTI3YCJm6GT0sGVmmR+JnKJL6b2ygUU4EJmARrYu3CJPLkIUz2NK172i0fo3OzdXqmaVsoWu9dHOtAlXlNO4PYR/Oirmh2yyQBe6mUz8D74iOXzZVzn0lTGFYtYVKZQM+wWrWqthKxms084q6rTcGqVtvBoe3dRK4JmMSdmOabr9/99O3v774hUiiRDlOY/A3uMwmsFUmhxT0FEzaAYjgSJjAJzMmqPcrHxHAmgD63w5zEqwQuIYCJ5AsHwgnDf4ILiA2v9hOjMEcdw2SRcftY5ONVGEE58ixlspIuHBQKOfdkaXirpilal2RBzHmycV2WO2H9LFjvIXRehz79Es3DXtE7EOT0oFE+BgVxUVa0Xh0Y4u2WtZ5uwgE6JnjXzz9y2dxYdgI2PxCE4RDaTZAoTLUCMIneVATBsm9Xa1qVyjXihhXbqig/rAiVJnBkOITNYGCnZDZU+zW2327++Nm7ze+hVUo+eDiHTxYWF+hcnTGYuANLxXV2CibrIc9iyZA/t5UJG4jhlNtXSuaYI7wSCKWxnTNheLl/gub6OOfzFXEs4Jf6Owv+AuBjGiaBmLHChtNShAkc2OKFmvulnhqO7o1CE+ahV/R8a7Tfdx6X8b7ZczmNPYDCKEUS1er28K3zP/EIX/vhnbBcuz1+amf6r4m2o87ZxlmZuDRSHV/9+gXZhY4eCBO0kE5KKTpXZw0mbnZ56g7YApZluY/7KeSTZD8wgZexBHFNHJUMIyHLRowhd8CiDJaXPH1ZTpK+sB0DyVj1O6XhPoHJCYRCqIiNmK+EjayEJQ8Nc56bM/kQTP6UMQxz23D2l72L/7Fzfq9RK20cR1MWpm/VQ2t74Y0dL445FtJ3KcQaI92sNK8h2coWSvvCcmzmZpPGNGUPPVjIhRctNIses3vALSwKbRFvBBEVeuG5eP+z95mZbJutra0/Tq2cPMJuTOZnus8n32dmMo+22ZTQidvoOdQ9eXP14zR91++MZr76w8Gke/WH+NsDsPz6qJDrW1+4CtfEi5NTNydHxR7xzoObE9cn71/qn5zpy6H7d++c/z1/Dc6NCj09wsOJqbszA5dy5yZui4OTv+ZA8uTviLmr9+9ODoqX8zen1s9lA7DfVJl8nW1CbDO7NXR6f6eCmPnqjweTfS/ncBPZIQ+EkCiy14jhLPxDyQVIdPb3PJTHV9GzSzm2cj5JkEMCX0jPlt4nq+4z6zkl+5lMv9jszbwhs78TJge+2pc7SMT05H76zwO0dy53rCIyy3Zay+wfDJPDADGw/lsWuvyoyiSzzE4RTPpyKJufyZRJZhlMMsuUyZdZfy7zotNkPX0ZTDJlcnxlIgjfGiYjm5vJe8Qfmfj23cuXhwPj+gO+h6saFI+qpBwUTrETForlT1wtFvet39GDQP6q2vQvyaYenk2vVtj3v/OjGUwyZXI8ZTJweX1h4fb5bwuT57Ol0srB4Op/PTa28eqwjGJnk8XAdwuoEDkqc724dUBax6ocu0HV0AFfbYXNE/OEiuZ84qrhql13xbQ0rf0VtVUt84uyafuy6X907qmkefz3MTUpZDDJlMmxlMnl/MLMUn5p4BsrkxX24vFBKujJ2/djh8LkWmdbtEAjBSQYGnu8S8pBEPBw8dgNaim4hWSiuCfmCWXS+MRVl3TBpGwRqV7+itoC0vqibPa+bDVs7t6xkB/s3+8/g0mmTA6zi9f6kXg7f+1omIz0TrNlaBemp+ni+aERdKaXr5QfHlkc4SvURqaTtfMvSglMzvDUaZ7scJgIuVevOFXgIMcPF5I9XIXAAph0eGHiOih5XecOKKtIL4PO8LQiPUvfUJTLXK4XZFQol2n0o8ppbx2WFByCp2ADpVJDMZ0iy2UWZBT0ziUZTsh0ZZugl/fFH1CJWtbp4zr54kWymEvUy6xEUZZVeknmxbKSUtWKRhomBbmKo0Ih3bdOQQVZLkOXUvGcKKtwhaWhrRXStQmyUCjvD1x2O0kbILDUAr9JnWwi7RArUJ7Dpiyz2lo4gcnFzuZSPf19Jw+TzL6r9XzBbM71/H+Pgsn0Mwhd6IbSm/Ol0tMX8L289bQ0S5GxuFoqsa1MLmwl7wfuwWTzKU+dtgQmT95DwPMGfs0f4GDn9Q7T1PlcR5nY8Jtu4KrumMjBFVQ1NM2tsxAhbFrYrjKYFF23ggqmr2kedaK6bRoYe+C6nh+nR1Qk7PqyY/ugTNSGpVkR+JfuQGwB2ZHQhPw+lB24mmaFVOhLtmY7pEYjLEvb9/g2SYtgDbRSy9a0mKZWaQEGoC2ARpI5Gj8Q26ZqKiKUhpGdaqTuQS6Shonk+1jzfcgnG15Tw3YA1WqaLUFdNtFCA8dySoO4mutpkIZWZsW0/Jpv08SoaDtwrpHuuEw7yRrBuhtCA6q2GWMcFqCTPFsVuqr50Mm2b2HL95k4aXeUyaUHd/nfZGZqcvCEYfLLlcy+r539/Nmc2/mHR8BkaG18dWVr+U+2BcFWab4XPRovbT9eLt1Dw9vjz55vrd2j+1Cvrazx+GaTw+TF7PLjx7PLi13jIhwmr96P7fy1MfYS9e+M7fxvY+w9fQreWkrUSyV2RMoAqa5YcmzJuq01mpZFvcLGvtcwJIBJuWhb4PANxWg5OGTpNdLwQnBUQ7FTPiVIimm17YgATBwlbHtKQ4BsodQ0qoAg7LbaBjiTRBqtCBsqqmq26WHlD6QTLWq7eC7d/ghbRiN24Nntmg3NkGmRhtkEiBR9q2naWgBxixkpHgsWwDN131U7jRQgsWdCvLUHE6FoQqWmCX2Tfdo3t15wcQQF1VBTCQ3FiHEtFYiQEFsOdtAciVoNzYX6K02P1oMCjGPTxtVUY5tKLJm0k4UY+h2RgHZXI5EDfCrybEId0GISqC2AToemyfLXjE5oOXnjCv++dXfgZGHy87/OZvZd7aez/Z+rTEYn1vuPgMnm+Cp89u5uEb0CMFmleyKt0A2laWwzhC7Mzp9BF5Znz+wqk6Ht0ubQ8P7xEw6Tl2OgRd7Cx5Ox9yJ6x2Ayemume9IDm5GGA8MVWkpEXTNiMIHHqaACTCTbp45rubooxtSHJYX6lgpYCS2jS5koUmhZNYBJFceqqBJLRgaLoQrU4aj0gHBJpS/txCCDPAV0SqzMIVNpIjHQjPQYZEOJRRrAEL8iChGkhOsFFtE4uCWAa7KRyzL70n3IOgeFsEYWoJGyRQSAVfcAbBHzARaACevbHLACsOGhpqa3lHqRnt2FSUvVPEQM2lokRJwzAeYwgdoknB5UjXHAOznH4EYjnjomZX6T4GbQtHWarcraW8MfDwOv3+DzOUs38ldPWJmcy6bmv7N99jqTcwuTF4+azXnMNlhDdGfYRYqKZwCTlWTr6dXxp882hxD6s7TdSZAok5F5ugfs8vj2x8pEfAeiBH3YeN3/cuwvhPo3ACbCfpjolmOEfpN4iDmNzsY8bF9IBmAt9jyuYsslxKdEkJTOqKdeSY8dgDKZkxSi2i4yse8S14LHd1MhzpzKPMj32nT4UzQNl1jAGMOC3CbAxFNsKBvbepcyYUIlsCxCXB+a0FKSOMjFBEwxOB883sgAxVplt5FSgAGIKukegA04TATZd0XOK4AZbW3Tklu4XknN9NSwNGxFyIBKWrFLfN4YToWAAiPQ0iO/pmI7kswkSj05VactSI+31un4tm5TItaxeShMBs9fETKY/LNM+Nwxk4GliYdHrjPZKm3ygzXKCoqNR1SiMJgsbi+Pjz8dAYDQXei32U6NXJn0zs5uU3t+gDJ5M/YOYp3XG6/eUJjkNrgyWepeB0GIbYau3wAZAk9YXWMwIclsjmJbPjBgDrsONapM8CHzq6BM9LBdAPeMFIMmjipIjQjGLlUnEMgodMwkUlzPIbgounYCkxiHNLXZ0wWTIIk3WLU1SJj4KdHYGTMFk7rSkP1Y2G1ksYbBcwX3QJiAMjH4rLcCoYZAbAFgIuFaJTWDCzBBHCYmBDyOoaRhQgVNN0zUBnSSjpk0dkOlFDA6MIFPmRD5YJhM3jj/vWZzMpicAph8jjIZnJnY3YvsUJhAqJIAYXV8kTNkDyagQF6sgU65V1pltOllMKEXLszP092n6d5FffeX7icuyaaGh98BTARQJrknFCYfGEwGpvKXuvoSYqtqYngwR3RCp4xjChO3MzUcSDTiCBRnb5w10QhCUK+KXcqEXqDP+jbeG06VA4/nLRSb2EWq35lBiumUdBP81NE+nn6ONAaTYrIQg5Iq8UDXSq0z4TCBB35baVPREHVGlqFG2T4YJnoCk6Yi8f98AiYiocRrHgET3kmPo/EwmNDaWUB2EEzEzgDsL9eu92QwyZTJp1jya/5O/+Bgz//Zu/6fNo4sLrOANCGJaxJWEVAVk6gxIHB8BhN/N0RreYFACQdNfA6HHcDYYCBAVJ/jSFACnFFPGJLmi1CTXNIWYlEFRCLRFqTmx+r+qXtv12u8NsaENpQQvwXvtzdvZu2dz37mzczbNMzkh8tTV+CzgjxH+MCo0jEwoTGUGvpFJLe+HCSfouOE4Cu6pHRJCedhoe8NIk4YmwsEZrK2cpwsqd+skNcAJAAocytbnM+ECK/33PZP+AqvyutG+Cb/PFdrY2ACrYc+aNdYfc56HLFpiAOTBAcs2QYTR5MHu1TcFoKjP93YZ9HqQE7gBDBxGsiQD8BkQbdgcTih+lXpQmCmfmgHMDGwdUAfDG4raW1ygoV6BySbpwhVXx8HJqRP7kT6JBQyFzKxYufSrsxkRA5tjkXAn13BBOw6nPLdwQQvcggx2F3H4qZVBBiCzwSLxMGqu64vMdJLrGv438YDfkVIBkw+NGZiU5m9Xi8zmgZMKHxj6NTle6Si6+LdKYwVjT4TCsGkouvWi7uXv7yHiHILWjwchaFeXOx68A051nVx6sWDy0/iwUQxp1a/2ihUbMCn+tEcIW9hX82DSWKs50YdC9UfUEPDdWpwvguf0MyBWm91AWN5KG8KBn0+q4AZyKTEYFLCuzUMmLRR7gRt4CCsD9ZIeBbqwv1O9Bv06zxBXx2a9cg9viaop5YgtHxYeT9JbuaQkaa6cNCFyNIo9wXDYEwJOQAAIABJREFUTVchmY4F7UaiCIVZnS8cdGN95ftYo4XUwCW5gk26BGYS5S3WJjbKyHRsUO6rJ/N1moe6WUccXxgB0iIPEQ8LjTIXlBYQT9EHuTnDYSvH0Ya2XSIIqpgrBzh9Omc/iw7r2SiRMvRzyYLWWTl8JXU+xECDR86y4p7w2KC1YWPziQyYZJjJLuq13DsXB9IOWqP/NcW/nXzwxYMH30FL5t7d/+LHN4T6z1RXF+4Q6slU19STaFzY53fx1eeD3z3omnoOpCa/nWmPsmRqaWNjS0FW3r55tbGO+2sbG6+5Zg7JVvnz43N1B+HO7sOBI619Hk8/98zviz55F4PwxHeHAQRmwy5XeJFCdaFbdCEcimcm7jCesGBSqgq1qyjyENYsNygk6HGxjRYciuHxhDizrSE2tIBAY1hgXZ5+t8j/EmwVCofpDLxJTx/yj3nWxfbVA5iw4WA4HB7BPMO8s0IopKKRdc2HQqLpSY5gVbR+R/tjDSHWhddS1W9wB+utwe2u4Xo43F9F5heIJgSlrQoOAZjwubW2Bhe3bUULixfJoYNlEa5kHko7FORdPIYgJmODrbPyUNAVLWU9AJPI71TQYubdrpTZyBRmwCTDTPaadhcwKSkh0mgcRjopwLNUIuxKk1NKE4NSU3wEaIUidwW3qZVcvo8YZbwl5eBtapd5fRaDuEBJpRf7dS0JqRTCoDALtb3f38T7SzRU+mxjJolmD4Xc0wRFS+KXvIMKNKpK0trZ5kCGnS3N6haJIVXyC8IPUqY/6HH1GTD50JjJXsHkPcrWq42NR+o5fudQhCDQsOFQWNy4OcIitHt2lFgIAqWq84Bn/GXA5Kgyk/cor9Fj8vowfYeGPpfPFdJ8JHeM23N1L2oHHoM7AyYZZvLucnxz87CFRDJYDR/PHWOgDmW5MmByGJnJ6bE9SA3JhG08GJEc+zQje5EMmBxCZlLVswf5/qw1AyYHgiWDqSrPsYyIJB2YKPILeMn/y6lV/vEjCyYJzOSqrLdSlnJpg0VW2Svr+d2QAZMD+H3+mbLySGlJRmJCS9OASWm5TZDy2HzmTy6B2MoO+EfNNquyjyqYJDCTq5VFlUWppBIEP4sqe85l5R+Zr6GstlZ0R52qrVW+PxfiJwm5nYfcUgzKkP4tNZj8ZfWWPowwlgZM8i/Ulp04iUtW3ni5UJdtRq1eb9LbDu5OYzoBTLzm/KMKJonMJDWUFBV9NT09/RWnIOtp/F8qq8/u37+/+mcUzzIZiQT+qHNz8+1c2p9Yq+cmDVIOB8eBbXrtfsNx7CE3r0nvjTpuufEhn+m1+tKdVSt2AxN+idWmfSz7SSupGXOIDgC2JFt8x4IgPkn/2LI7mHw+XlCo4KQw93x5FMspm8l2omy8hRv5n52d1C4SmISIVsQeMvFtFUVi4lja2FOC19Az6CxWiA1Q0dS5xz94MElmJil5yXQNoagzAW6n+PuxVFZ/vH27+peEY6s//ePdi2eY7s1pu85tzpyb2ec1vlaviWr7VnLHsko/ngcrR7iJj0ZWWmvW7xNMuBgJu+fG6MsxN02jxzXL8yCzaRcwGdz5T6i4GqsGKqLVup+nuZUT6e48JGHf3iA7Kzpmfxy3o7Gmt7kDs7kRcOyo+acxE2Ve/I4QQ9/GDa27ZhwleV6/fxgs3MSR1+VMGcm+pPIzOEFe6fWrLgkIgjud0Ly/NnzN7GcEMwWdKkysNF8iJI+xYWRTP4PDxLOGQR1w5WZnOaeeZdbqVTbS2QkQYzP7zaMALJ0DoN1+Hm66dpXfm/fxMJPlmYnAy+uWZVSp7Pk91eDMkopnSWDya/WzfRTPoLkTBZOJ4pf7vMQlMZjMRYfPisCkGQmJhdX198n5OEnD+wSTknUxmOyUG8PNO6r36eTC7KBh7c5gQqVmJoNS7vEvoSO939L004Y79DuzErqjoRekwRFHCxJYhcQRGBNzBnq6zW4VHZr+Io7iTIM9sNowk5pqSAOPoyclwop+WmxPLr9k7u3m3hlLGjCJP5t3OsZMEC7GjZfO+7UMYzJnE3ML1P1Ro5IMmMzeZq2SnNbrvSpjZ9SKXus1G5njZMDYDPrR2RzZZhPDaP0F+SrQZ+C/3ahi9NpxUtqC6l4FMl8zo23OKvVqmwFlVKpcyKPF6zdeIrkqUwtk0E4KGS3j1foLPhZmwntNIiTCqfT2BFLarRDA5Nnq1z8iV1n9pfrr1dWKeJ2aGcOMveMMcERY1XClmbHbOwA7zsQ+CFnmwKSmIyI718Fr7SJjHfYEujS3tL6GYLKyvrS0no/rNfWb9XVoiuTOrS+tbwpggkQTw55RTj5QmTcJTJTmREcdFPuG+NuE3DhmwuWWy+e2kZQb04y2R5yN87oqMZgU1NYW7NDMASZy7EpFxRUORSoqRD4Term4ocZyp/gLmvNm0FGvBreRuBZvAJgUT3d3d0eswjFJzISgSMZkE0TED+jpv1vENGMiIImZlAa6u3t7wWYNb4Lm2UW8TVqTc4fE5wVr8lRmp5O8MWRNvV4SX246oZTvwkziz5Z9Hs9MTppNyhOdsNFuKiNmBIhRk5L4/aDXroQbIQ9Dl2dFm8NARgaMF8hNfDHCQHTKwAUTMJLPTKOkTG8eNdmIUssUEqW/ndxEBdRijDdRrZ2QZmzgqlTUyWbVKZJv1mdRKr2SKOBpdhJbQOOdJz8aZsL5XiejYFIk67GnA5P7t6urq3+lS36qRrktcqR0t30rkxWfI9fPynJkDWDK0i3LySnuJuSl7DEhARlnnWcmATiT0yaLQ6+CT/jAk3F1XjHZJpO1TcY3ZdfUavUjBJMN2FC/2YRWCCdvsPWD55aobTDBcB8Lcj5oSQKYnDpPyuFHL42r6pZIDuYW18+Yu6XGKc1bGLEWZGMlllsuwVPqV3PbYFJiwDnBCWBSrjWNJzKTQR47nvz22xNAkys//PzzPYGZcA/15RzZY0dbG4CJxd599jHW9Jnu5cgMrGsiy912eGjPRJYjHfiMf7oc6Jh0SGjrxHJkjAYweUmwXnYEWuHkxFM4MbkcuUFLWv9P3vn+tJGccVwbY6SJEswaMkLUFU5sFQKKjGVs5Bobci6WbxX5B7usFAeoribOKUdbkC2d8Z11OJbWVt+4pwTJXJFIpWtsCJVjYXTcCaSge9X7q/o8s/6xTgi5nu5NlXmB1zuzM5Os57Pf5zu7s5lCrpo3cM7Mql7JQK5WmUgujXjhYvl8DAczHFnNB3CYSxIb8alMKlfNuKL5OBTKYTi0WrV+BOWsopTJQPcMsdVVPNSwU83kESY3RoL9nFaX4Hq/57dwq1Q/OR8FocJxjQYcUjo7qRu5X6xMWjABZZK22z3eFR3R2e77ERVtmBS9s8F+iELC4WAyue6bZL+5MDoefe4VsuGGK8u0V33iddHnTyb9PsBE0O2bHyN+H8Y/owNk1pNMJtcAJPMeXMMS+KQLzTOYwLFJZgBv4ReowmPssfseT976cDwTSKv7hbn4580ipm+dl8Pk1dQ3r16AJiHP8e+LF13KZJUXMzt5QBN/UNgRhCHyFR8pFHI5gAmGNF0wQWVy0KVM/D43Jl+xsyvGZ2VZ4WVtkFGrNBhMzs4rpXMIOZgyqVRgVDfOGqVGWX3FlwqTT28++ujex3e/vAAm8+HxrZAtGNIsFJkzWWQ5oi9o7ZLjSr2MMDmrH5XOcKPZmo6cQ/t1XJSlrUwIeRsmI17v+MUG7Ovdly93v5+4OrG5u/vPhS5lklCqGUECmGzzgsAfUBoTRSkhuahT0EtCIkqXxISUEPOUy/MJQa+PUWeEh1BENsumfHRpKUpjpjylBf222RnRCxiiyCLk8xmMg/QQtqQ6MoC6pIjWD6GrCb0CO1xVaFzMYUGJ0Ybu8YKY0McK/B6lWYGj0LgkbtOlCKtyn85YsLsZ1quECL2i/fP2SY3gOCqXHeVy7ZSjDbggOByVhuOIcrUyR+uw33Fy7ddQJvb5+SKA4ord5wmHtDAZXQv5fI8Hhj3uMKYRLN7Hzv81zzrZQM922jfeNNRZEfgl9oZBtYAWUZ2PMbt6rB/OOAZEs+EOTLa89/Hi4R1XYbLiuUFuFz0+98rwh6NM7oBk0OXb3x7+Z/lSmPx76snz56/Y9lueiW7VdIAfcUGQUymLKQYMsai+wz6/T3RdMCFjuE+bplfWWBrXuLV8LpXKmzTy5QxXezxHmOjIaQkGuxFCEXQxzLjnsFQ6dpx2YPLl3b9+/Mmje2xB6DdgMjjvsXvSnnVNpBNJfJVKAeK0rVVQAjHPhLXGcHbGnuTV6Q5LR7Vy6VKY6Gyz3e/XbHkmDzZ3f1xY+Gn3XwttmHSUSSIvSBYlYpb5bZerKqZoVSzMRAsGmuPzM66CiwvsBGaGgAHRRGRoKMLHzFY+NhMXIpzMizCOpcCQkJ2BnSm6jRkJxSyLEWcUFIZhWdbnlwOGlgjgojErb+0yVVxD6JkgilyulBOyaAsmpkg8UHDKeoQJiJWIEJ1ZSoGEcYpZqJLu8FbXskWMB6BXTolHmMwiTDreymHdUTkEYQIwqZVulU7rDCY1rlQ+vm6Es9rtp/wyZdIUghvejYEeVBTz6Jmo0sJoe+z1k7C9x2jsUSdljOlZdFzcaypMtpowWXEPYhH4CfndHruR6Q1CfncbTvQoZvSqi1kOh+0dmNgwNCJJ73QHJhjl2n3jH5Ay+VypFlphziXSRIUJ/Y5FN1PfXGjArmIwQ4gM8Yso6oEBQxIvZfdcGOa8qUxACEDwfnlaFrAi0ZSd0wzvUnM2p1LDi1vtsGOJnp7gHi1MPrv76d2/Ld39+4WeSdDndWtDkKFma9VOlHNcZq2dkd4Ga60NE/w8Zq1dDhNi1ukumBr+y9WJH3d/ev365e7mwtWnm5t/7PZMEimB31MiJG+KKIpkyoHUs8hOM0d3TEosjlbDUiarCFI0pgcBkoNhK4mKoiREl2yy7O3nYga6rXe6IhFXVMAMUQjIWFIR4NCUPqcRC3RHNClOrV1hoIYswgQuCbmCOvvShskehXinDZMsCNCoGTICYhU7ZeFZd2W51SvOOD3d12XHMHowmDSwqiZMkC3Hx8eOM/rreCaMByAR+uwY3QBebsNGz+y6EWixBjHMCDGu2VXPpOi7Pzy6Dgd1KZNpH5QdT6NZsjjuWyFXPPa+3nFPEVjhH+tNptEzWR/tAWABTMKjCJOxG+mwjQymwwNjTZj02OwbOuJnguVD8Ux+c+eOMic3t/mHO+Q9MHn2BNKLi5WJiCGCTuarMUyApXhGanomAJODFkxcTZh0K5Pxx+ssdW44Wk5IO1gRWrC9xmswLMfaMCmVy/VGvQww0TVhooNfY6OiVSbmr2/e/Iw8Ym95eMsz2Qh53J5wsu2Z6JyCEGu1xl5fp+uttWBScpTrFbaC0x+aMDmsQWuN4/fB5F2zOSBKXmMCTbLQNGA7ykQMbEcABdTKR7KQZBrNCryQB9GQEXjR6qIFIRHJAkxwxFK0OoUEFrQYZCCP6sSCpuOtxJkQMGM7oBIAYMKpMGnrkKgMyqT7vhIGE2CHpOezDF3tMId5qm2YxBXRJO2hu8JgYrbwCjYWb/eK4wjpEhstmHANR4W22NKGyXG9adn+LGUyqH1+dbAlMJPe5vVh2uO2h8IAk2k3bIR8Nt2iN2x3hwZJX9pnD3sfq8+Wwpd0yLs4Rtbc/TgLxIIfMlyEsr7wlYFwqI+sA5aSPk/aF7IR46w3nfbOGsm8JxROe+0DbAW6IJvNGYeGPO77pDfNPBO3EQvbffYPaDYH74BV5grql8RD67sN2O/w44cpdnOJ+WJlIrKZl4KoaBzTgiAskxh6JqtNmOidFyoTUJQsrbT3uCRhqPXPWkmzuZczxxGubF8nbHr4VKtMTss1gstVa5TJP37/SQD+fH0BTB67/ZOhrTV3p7U5SerkpkHc4ptMj7DJMzWwKjWVCWuNTRj31t4Hk77Fou0iz2Ti9e7TiYUFxMjT7zd/261MRPRHI6BMeJky65PS6J4kLsFnIKbwe/A/maKcIkRlPkMpWp1Cc+qnBRPOJWW3xTiN4gQzy2jB5A1l8rZnYmjChDMbClaTtcsz6cAkImG1zpwguFowoRZ9FLtL23qJuzF+v/8dyqQNE8pg0qDqtI5hH2euf44yua65o3nY1kL34Mb1dtRcDA76b6kbNn8fGRtZXPdj7oC/uDjSOnggWVxBL3baD4P++kYLSpNQ9hbpXwM09a1NYiXrG/1orwSLxeA1tNxsa0U/nvXR5OI0CQahPtizBid7LBhk9fWQG8liMfn//IjK/6ZM7hzkq0pWJvk7TcfknYt4cF988eLBBHky9cNz8oApk2dTzx5MmLuVCYPJXJbfd80V8k6S2nESkMsuIpu2lwuSCpMD00HcCSpDhuvekObGlp4BNWluTM6brEMknpPhDM172ftbGo7j01KNweTk8PSEweSwXC6dGokRPnrrXWHO0r0/Ly39SV1i/g2Y2AbJ1n/ZO/ufNNI8gGc6YjLtney0OiFdGqmSLZVc0JOX6VrBlMN47KKjUIjTak1w+aHXsNtdzSmG3AEC7Z7E5BAj7Sq+VPH6Etto0+7aJmv2l/uz7nmeGXB4UXG9pe32+baxw8wz8wzCfPp9fzp0BalP4MaGyLEQDA73dV65hGZ7+3QWRnNewNleIpgAZm2D2WaB1Q/M/AKY3Pz6/uf//rpfAhONrrOzp1w0Z2Dyh58HtElg4Ggnf3iS95mgPBMIE0LOcSqeVl9lFHw34R5jgEJ3jRlzM8BYDFHNdJziZa6b3XbO4LWDxzYFnaJjPIBJwOD1GoAOEHA6oRu1mU4zTJyXwOQaPdpVkIZSHM1hiGAMIKGfN1JxqLQUaSaEwdcMbCAAE7dXRXA+CBMfN8RAZQTc7k2+u98H7CsO+UxsFqnPBEJkD8FRhEm2fU+VbRd8JkxDdhZcyq4M5O7ucJjU6M40iOtrX6rXVdvLaestX4xDlmx8RBmwIbSQnVuI5igfeQ++cFivn9qlmF391IMpfRgmnEzppwpDw5u0EAkZcyldHC3zUiGlnUPhXwWndPl8SgQTg0vpdAGIDMVonz1y6JsxBsEFfFCr0VgEmABlYWGhHcDk6Uu0AWECo7QLr9E/W/s+E0FTuPjllxeFxqqlSWumtvqCz1wRRLcLY0e9nWY4GkyytbCAWuijDaj6aNBstbXgRrbaF3IwQV+tv168+PlFoUPbPVEzMV0pspkLojlPnkgcsHnNJCiDMHG5GEJNuzi7z8BwTo6jN+XQ7uFkrn6Gd/o4n89uYEIwjiJLMzc5eCQGYOKESWvXAEBoJdBAGC8nEw9kBJ8J0R0EF92P5sihI1WSmMq4wXhwDh+HczvdSDOxiz6TNBoXozlgdQHG+DgXdN4S4D7tXIiRN6Pb9TIB2gVMpDRywDYWqEFNW+1bW2+gswTChLgEXi60C9Gcl1vQAQtgEmEq0kyomnpTTs5Uvczudt/vshjnZD6Tv48+DgRGPxWLczKHZYJuhMMQHc/nns2FUUR4ORwOSy0dMp4WQ0GKTKo55O6iFGn1ppqHGqUhkErH0wrBOZHO8PAhNvKZzOEZ9WQXH9gM8OCqpOm7QbQ65dmd13vZnVlK8+bF673ZbLYWxlWyOztZeOjt2+3tHfQpt5lhJjRFfX//Puoj1mLrKKmWqW0q+v/MmFY3R3hYOdTY04Ns6qcvXr+YBbORs3tgI7uNdGo4Wy08tJed3RFCw51wNtX3Xzx8+PCLbwFCLL1mIVfpTmdf3QEZsJO//PzjTEmeCfjhzsB0ejfM2OAD4IbkRDyUSmW6gVIAf6/QXepWq/k4bwSPfoiPyNzQDEqlQmNEfwYJTGjlM/2QAPkDBnAWyh+BY/qlmkkzHYzkdRUwBxKvEcwdQLksBM8jzl2D14CqSSSV5sGl3JFmddqInnvwScK8Wni7bpiqkoq44eCGf7Z8Uph/+2ZnZ6eJYOp33qBLze693c5mwT1s773egwfGnM54ZZoJ+m2qSI3qnegA9TrNRwKT42XAfirWFP/pq78dWpakKvnYVKpj/kZV/4f3l9/QQIzs3wp8ReaH3LVZ7hZ4dy22e7/y/xJNbhqV6i/o8iSajRK3kbtHnE1ccQzAxHYb2cpAobKWRnP8YuLrAEqBHSjKgBXq7HKJoaLPJJ9aKsk9BdvA7unmXP2SlFLpUEKaa8rkdxUkm0J8qINqpqCGOHdG/oTCwpqSAftptkRJgm5h7giRH1hY2JN7owFlvkxI/l43RyJVHwlMjhfN2U8x+e/HoLpVVWqtww3lojn+ksIcpJkUV/4eVAKXfw6BHenzZZgDhhQU/QqBmvwe6WSMvFzh8f44yYnSCxSOKHO78tJi4+L9JW+o2VthNAfLO9JMKhHlI+8p3BzpNxfiQp4eB/UzkQRpyz2NcsmT2O/OoMSTMp0ISkv8JDw4jFjlziCKgbJ/I5JD8uLTS69evL/4WoyKIT4IzeSjgUmRZlJR28avHrlx28ZqiNafazlQ/EcrP76gp+53Khgm74VmAkFy9mzNeQEm36YqkIABN5SuEk0u/BlLJYJh8n7A5Pw5XUuL6TLUUeBSF9Afpjr0LwM9hxgmVfmEDuzogeUY6fRYquUzaWoZbASi+xAW4cKCpZzgdXPeD5j8wQRZ0traePl8VWBSb/1VcSDddxWf1gWkaFfLoBgYNvWUphpoWq8PX8LfBgwTLCeEyfm61kYBJqZKNJNzpjMVwOT5rtjydXnu2U8bBYdq2iaEDBXV5Coh2Z9c90MfwcpAfs/AehKYU0wyKZzWVmkWtHGUi40WpfpbcwWig2WqvK3mXlsT/jZgmGA5KUxODYowaakAJpo7bcNHw4Tc1QsEYV7pHzwo7FTfah4UNlTzHrlk/7QjCl7OsJP5PQmHZ52i/OPzDIRAZ8WtHq4+jjmFoj/SzYm9ks72WoScudqJEiiRbR2nSPxlwDDBciI5NkxaLZbrFWgmN8R+rzemnhUfsvTmzJXkCiPZH2XZJYpaYhP7MGHZaYq65RkHw2otx6pviIkVxOl8H+o7Zl1ODSmh0sSEBn8VPnCYfHbmFJZ3LMeESZ3tuu1omIR35+YgTDZ2f9K/2t0tMHNOXfkmZ+QkllCW8YXFtbWEFsDEAVQQCBNiBuxZgjCBqokAk8u5Bo18wBtIwXUvDAG1WqgFBK8DXoqKw4A1+kGRHIIJrw7SQbUaFSSazGLGvM78TSlMavHj+KFrJp+cw/Ju5bgwuWvTVQCTZ1N6ZOY8fwBrhafC0mONYpW9KjrOjkAzJznuGBl3TFJRxxo7g2CywnpGPOwimWCnHWsiTHrMYnF+SuaincpRyutS2p2yEEUNcbTdDnsqhZTApAmgYmMRJmofbDjqQ8hp6LAIF7jUV7I640Tbefw4YjMHS1XNHJOl5VwFMNHeEHwmjPa5fld7gylwduZ8H1p/FMFklU0w2pUkgMmKJ4pgcmvJz2in2VsJNrHm8PsRTIZFByr5WOlye918V8yZHjJwPgWwZDaH/hV3izCJ0BKYDBkidERhENYE7OvL2VmF7QVqmnpKdRUsGCZYflMHbMPt67V1tkp8JnOiA3ZDP1d0xNppyrtcRZgsnmaQz2RglV2ZQT6T5MzSNLsCYLLOrp5GMLlnFldOSgleEK/THoqEODoEYBIzoGYGpTCR+kyoiV7RyYra++7LcIfZhr+IGCZYqgoT0mrRkX+0XdeQR8FEdRhMcv5PRtBM/OOsYz4hBzABSsg00kyirMPjYGcS7CoV9ayImonoP02hfkRkGvVzdjoD0MyR2dWK8jDJ7MPkIM2kZbjtSiv+KmCYYKkmTGrutdlsNovltu4EmslgvjOhCBNKuzTtgdhg/dSaYxHAZJpN+P2rAkxm2OnxQp8J6kNN8fSmAspV2DZp1KXc7BJ9JgfBJO8zaeibKPKZ6K5YcGQYwwRLVTWTVqvVesdis9adQDPJRXOgYTOSS1pLOqIIJkmPB8Bk3ANtIAEmxLzDAWFyJhfNEWFicHLolgQKGOx2gwCTYK6pvbBOKJ+HySHRHA2O5mCYYKmyzwS2jGo62mei3Vje1Yc3lsvCJJdnok0m58fXk6epxGrSn2CnEUyoRRbAJAo0k4Ro5lBLLCvmmTRIYQLMndExbyA4RKVH/6EIOTkjUFZiYyGnjBf8J8H/uLsoKq6MpYVFiw/PM8HRHAwTLFWGCco0OQomz4W1t14xZWHSiBZuVU2yDgfrYBcBP8DGSBLBhExCzWTdwzo8UQeASQIYQ/PsCPTP9ogMEGFCKjZpp5N2GakQLXPS9jRFdW3SMh8nwEQRpGkXsHSMj2UypKuc7ctnwJaSo60DV+ZgmGCpOkw0deeO1EyWBQGbxLK2xPMi1OYAzQTKaUqenFlaAaP8ScgMfxJu/o+98/tJY9vieOwYk1VPJVGrjcmNTl9KMYHyICIw/LI4TBg03MSDbbh2mPMgFFGLB4IJURshpxJNUBPMiaE3SnzwlQcfNTGe9MHW8y/dtWcGQb3eo5bb3FxnYWY2M3sDM7g/fNeaPWuvrc1otjT9pIwVZ6RmaXl4yD+UK72U85eDj78hL2wDv6+8lSIktre/D1R32wYGnhF6UAMDAya4dG/O9WjrNDP6vkP9b1BhotqPhcmF/YeYSZ8WTQ5naK+n0u0kt/9W0zmT1aXpdGp5nuurkFiHt13ZcSvrq+Zxlle63ou7hq+7NM3eyUkVJipMVPsfhIlqqqkwUWGiwkQ1FSaqqTBRTYXJ3a3Vs3zjvg7HpHpu7w+TPw9vY+cqTFT7P4GJjr0ZGIOsXR3PeH+YfDm6hR0ff7kbTM6+HUqP8x97eM9+leyZmq5Ehcm9YNLzZlA9t9+hTBYXuxe7b/rDh7Q4Oj6/0yRch1+PiX09Pnz9Aw8vdLAi289O9bt+yDBpNaC+aDO0oN9iaAd4OqiTco++7ATDq/ZlCSYGQzNW0elI+s7hEbNVAAAgAElEQVR2Q3OHTrqxlHpJnjcv9xrUU3wvmHTfbIuSkcLRoeEumc8Oj+Smf3z99gMP79eV35ekx8pvNbHaMzksPaFMI5cVrCkQCDRKwjht/211bLLd6gtWDlI7/OEhw8TBPAHKWEGVMce8BK89xaYcHWTCemOKNUgwmUvN9VAfmFSKTPfcW3Ew7HspZsJ4AJaHUqmUUR070GCYfDlH+yJh5evhXWBydKS8Akqav67d91ga6ra2vovdYGH93f1hsiTbwcdQTdXa5+XeWIiSjSbf5uamPoCljXhYnG3QifVx8huOBG7mTcj2PbQqRG6DK5t8kEBdDNp7kDD5wPbC8wpCgxqyawdTzPS8kXVoIc1WxodfEJjMscZ2mGet3mF7ahm8LGscls5XR8oIP9krH9442HEVFw2FyekZvH4NJ6ekfDeNcViFSffx4dlf1u5PZsmqaC42wa6fpIb9Tpgsrfyzmq1eaxyTR62Zwi43rtw87aJpXg8w5ePoqQad2FXptQG48I3EmHX5vuMNbGHuNjAxibTMx/ZRxwOGSWfqPXhTzCi0Vt6Dh32F9cdYAxiRMSRmMj3Oelqg2cq8QHcn5UCYeJSGHRUjtKWsWOpVgycNhcni6dl59+np6R00xjVlsrh4CwhpgjkZJv4tKJvvDROqBpOllZ+rI2CVu4cpk6jAhAuFfHSYSAhfw2DiHJEdJo6/scu76c3vg8mtnCHRpYit8aHWhwuTZqsVHEPjlRde1gtWhtyXMc2+gXSlTYLJEJvGdRtjnxwfH0d0eNlhpeFzhEnPKGud1KmwaLgyOSc4uNAYJ/dQJt1/SBDazy1khdw+lprWi0KWFLoWioJQ6od3uaI/WCyWAFd7TUKSwKR/TxDK5B6dmbIgFBdA3iLsdaEzlBOE7K7Sfq9UwtJWFndp6pXJ0sHKL4rirWZ6q8EElxk6gctNBSaJghj1oaSYjYki5yPB29kMlvLEb1mNijF37cDyBbmzbsQo2MlMZcSonjg5hdgIvkOM410cl0FRZNqIipl6HyrPRekwx+24uYT0fDszAgkO37Y+VDxVmIiJpIK7oCeLPPhihehOTPQRmGyI0R1K+WwbJql6flUUfRSEyOfWX4aJjpG9u5cez+CDgwnMMZ1DDkPlzVyljWLsZMs8AiPNkEbLLJuyY6E1lWKIpREm83XKBJ54mBRrVZVJo5XJ2cn5l1OlxuLXw7srEyl2e0LmxzEXy/7kO5J1QMgGg/vkPuJiKRvcRV5k/clydg+KwbKw699DmPTnzLmsX3gMmqI5WxJyfaRZsZRL/h0gl8yWg36kyYI5mQ2SfAX7QX82Zy531cNk6ePBiHTEnlElaaOJC4dqMLHkazDJu+IxzrJKQcRViETpDYBAmI5FwhHSiOYyrnAtAjNh2ZH+l+NRrE7H41w8hjApxAmoTJEM78pkIiawFWguxvN1EEpkOFrMZLZDrlVFwjgTLj4jWurlip7mowU6bIKEBWslaB/ELFGeDsf5gFOk+UwYt0CC5/HTZihSPc5zIuc0RelMRJSUi42LK2/aOSQnhBlkmPmHB5Pe1GTFq7V7RscARhlyHXKc1Skw0bGeD+xYOzxHN6ilhYKeK8qEOImDHlZNU9FoZXJ2QmImSpU7hE3qlAmB0BnCROjH7r8HW8FiP8mnRmbh2gJ4TJKv9StuTnAtiDIEYSIlI/hMaptxT9cMBV3BJNacaUKN00WSK2VBk0zOwGd/sqsvR9BSNu9fgsnSylvyo9+THqsmQrJJV1wQJoGqmyPDxCRiB9RytBvcuNEpxm2QJ53Zhs82Ldh9ty0bFwcW4iMQSsCsCzetWqIBMLkvxUx4KWYitUjQsUsxE0IpfPkoNZK32eIFKNB5GBH5QD1MOBus4uaE3B5h4gpE6NkJOqEVcbM7LpqcHI/aI0aUld4Sn6KcbsptKZD4bt1BEhE/6qFkN8/+AGHSgYrjOaDCmEaVwuKizV55dAGTaXCw76FlLLWM0PUMKzDp9LZLyqTTgyesnRn6SeVFI2HSfXrafXoC3xYvLs3c1tGpUyZyszUz+iOPERpSBmlNUtCg1iitSdkGtBcw6U+a19cQJjl/tlTKmnN9j4PB9V3Cm76ceU+eSbRrba9c9ueQM2V8kkziq/pL5RLuvwyTgxXSTVvG0ldCFzzNuyxxySmQYTLlCkciEdFCYrKbkVg8HiKbdqZIFISzxCKRGB2tncGoSGVcbr1lAqhVWl+9q1mBCaXAJEYXpGbOazCBjMu0SU/MIih4ERts0Pk6mCC6+iYs2zWYZOK2TXokQeupcNhJvDN3wBWPxCIcgZzeIqsc3LQzdTXw26FMafhUp2t7eDCBNJum4BXLorPyyM4aPQy5HjxWkWEyCU9HkSjLlYoHd8zLMKHGcElg8oRhHZ+s7Lg6FLaxMCG64hucV4u3uTLzb5XJa3ka0CZBQL2xQNLBJh/D34p+c7B8SZk07SW3CEySfoFYqQ8+J81mYQHdnH2sndzrAk3WnBQEhMkuycsGQhL2/UGp9sIVZSKNXNMar8wM6ObDPt+E/DMuw2SCjkfRuDz2bF6M8ggT7WacpqMJcEZpsisaqbWPuEJhy84mcWEirouoyBVlEqVF0ixmuw6TbTqBLtU2nbdJ/tYOvVMPE6RT/hJMwjYfbUKYgHQ1J2aZdaMrRExPhIzcltrBTyvqL38Dj6yehxuABZgn40farGni4bQamcrQMKLVM/pccvxwV6vV+hKWRysVq5fEl97gWfxkX5ZjJoY0U7FPqsKk8TDpPq3CZPEOEdj6mAlBUN8a6fr9yZxMFY0gkJElWwtFaarhC5hoKA3S5jMU0aeR85NQmrWSP0imMu/aXyexWZQ4TdBfVSaAyuRdMKtkM6mHSfXi8Kehzisw4aCa+kSGSYKWf+AhwIsoZgr8v9g7/5800jSAx44xeevVbvBkG5Omw95lixhFwhRQRAQqCyfoeXceenJtoZso6tRaD11Pr3E93a0Gg9+iVCPrlyi9RGMtujVVs7G5S3+w9W+6951hmAFq0Qq9Xvs+Tcvw8s48w6Tvh+d53ud9XkSauoY2iUsFLQ1z7BcjGwwtbuu41SNFMDHGwYSzTMZtCfkmZAQmHZI2d7+7jTZX2jzMLTS8FSbwlkZjYeKWIovH6JT0817RbOTIPNoioWNVqnXtzKv0em7mZwiTWLMi6/oJXUTXYxvQRDFqxtvapz5m8u+HD788Bq8ennluOGE2x4eCH0vQ11lCDJiyD5Mkqi6NWhBkZkgWJgAwMFnQ+NC8TyEQo2psK5olwPRG+2IE2R2KhyGBIJCW7F4y447jIrpIRuxszg32Tiy6a/Ewif5Hm0cBTWCm3YgAqkqjZBwRBVomlYyLI6kDLWVorJerhOcbrA8MTDhEAJMJgzNimTBdJ8vQMCdiQGSUMPaN2WXwdNgg0aRuRC0UqkmESTO6/kiZECZoLqrcTZtVLibcgxJiOZhIKxnPqjnup5md3fy6prTzM4TJ+0ljaTQUiyXFszmvjo6PX4IjNgB7pqw13jJhTyN9ds1K0GtfhR6OZiF4BxJBvDIU7B1mkkrIIc3KWFAAkymHY9m37B0DU94F37LDew9IZ1aCvXfsS2BV4+0ds0OYkGOamWVmNicIHaHgAjRfeJg8juaZ5GhbY2Fi4GFiNNAjk3Wgusw6O9vvcqpckpFZjwSO8VHXZPGIwVoOnLRtonjSxbsiRLmnbFJFo1EPWlgQEObqeatkohphZ6LMWj1fCerchpHiSfeIULGZNoxUP0ATSf2EFVkes1BtCzMtI4QJiWACiVM9YStjYiYIJrDJVeaZ7UenzUvc87NtKHeXg0mza6J4wuCOtaG4/eLlpbpbGCanlFuljzIxJdIDkzcvj46OjlmWPDzTmr2oZcLFWXz2Ia/di3yai0MOu3dMDMhlhx0llqBPp4a80NMZmkEw8Xl9KC3FYXfMLIGLM+wr5A3sjc4Xj8GWhRlo3mQsex0LaJMdMuiFbcOFwgzYx9FwRVz2ltPdxg/fBg/tMoLKatpgoNtUYNRtsI23eepAh9tmsFlRRKTDCo88wh/9FroDtLgQRibdrDnSTNO0i6ZRCETV4qI9cFQb0Wnuhphn0mylbRAG1XQDmKQhVSonaYOtX+icjNKj0OuCn4Ni2uCacM2CEWvlvEvV7BoFVqvVYGuBdo901mWA50Eloy5WgdMTf49og4+IPaKuqCjBMMHyEcRMUP7rQz5b5OyWSWQCiPRpguLbDDgIovAeu39Oxu2rl0+8AltdmqkvzUY4Ll9lzweXb2dEe0VyZ8E95kqCtTn8GL1U8+hEJVw1WqnTyMCn0sn9vNd1cFcwG83v86hVxrpkWkH5yZdWORMXPnM3RziNqthPzPHKpPdrIwvV2nWKTAwTLB9DAJafFX51lnVqwlXDzNhh4q7cXRDxB6e7+bjTllaCviEu955p41YN/+uffxOc90X2/2SS74MqTXiS2dxYq9JeAxgmWD4MTL48jUAonKWeSf6b169/eQ3llzeRn2GfI5jqL+Pz2h0RN4kzJ36K1DP5Edcz4STnAsAwwfKBYPKf08jrn29+cZbiSFnHrxg5BpGKIZenLqf82/xhdfVinHNwpQ7KFTPON/rUBcPkY4TJK7Ym2jvl9c9vjs5UtpG8KSZZ+bS9CywYJhgmPEwKXp5GbhJnLChN4oeNBcPkM4PJBTTw3/WH4wKuTo8FwwRLEpicTk6GSWbO+fcBl+bm4JLyWDBMPmmYSKVJYdJYWlN/QoFYcvHp07WMU5CqSqvF/zuwYJh8wjC5UGKxyDKTwCS3RK87qczdBkX1rSW/sVu6ehlOZMbyscLkknpALrScRQMDalHatBVAbTEDTD2gzvy/h0mBySKTXbueBCYoZ9t0omWyQZ0CJtxKEixYUgOT8ht3WbmRNNky/3A7WZf6bt13qCYB4TSiFCZCrnume7+6jtL1w3DS0dCtU7Cd65ibb4TaCtL7PDNzCgoSNvfIzZUyHyHJOy9M8i0WCJJ8IilMoitBoiJuamLT4cE0B5MmrqmwqSl+skdfi+0SLCmEyY9PeopY6XlyN8m11gObMYPk4DChS2t3I7JM6sZtBmbJlkjd+s3A+915WBlz+fWDrYRsBsUzZkuw8lkru8Q0V63vTm958Px2vUJRZREaX0SOqbUV0UFdVaXX67vOC5MLXXKQRSSNmQBpPEzEiy+gezMohEnhHkVRc+hwsI+iXiximGBJH0yu/FDUw0nRk78mg8lOzPtYtjByvxupI6ySthGJm1kY1ZkamBD7yp2EUapgqtaarWUSrkTwozTDJLO+s8vUqhgQjmlIEP3X8KhEX28ymQbOCxN5l7rRYpEnt0yyK2LX+TfNUXuDc9RTAUwGqReD088H0cHzwWnqeaGwf1ZNLU42w5I6mPwlypIf4N8/R9vv+YJLsT39oZAfwWQ9HNoOrcPXUCgQgG0EyPLDFj8HE+RmPECFqZj6nmjrjPjhlaeId3yu+oKrCdq2EUx4bVuBnQRtCh3yOIyeyXlue5T7EZhkqgfSUoSTQFEGuaITjsJ8uZxRIbuvbtcjrTL9QCpiJmpTl0xtMRUkhUl+q/a+SfAtp6lpUrxGvUBZKixMyD0GLWJQ2Ne3KBZvsKCJMKtTr8U1abCkECbfczD5VvVtT9HjSCsZ9Nrt9hXB7CKxFVAqA8g42FVC2dkHfiUjm+sghF4D2wKYjECOVEvYyrtxlsn1HJBbKgMiwV2RvQ6obVnYawtdEcHkgNHhh2YKq03KHgW2kKNBsjApV4HReJgUPOtuT9szZWGSW6VgXJq8LNCpYGFiufS2vI0zw0RGgK+6ZEQymICSmopaQQB6g+qbm5uj5gp5y2SamtsYhO/XoLMzN9dHTfO9TdoKRTYeH1jSAJMbxj/xMFm131m6uiJYvw49nMB2aAfB5OAw7D9UHmSJwuHAZjjsl4LQQcgPrZR1HiYtZc1Om9XG1LOKs0w6taYcrUxWq+c3yFiyD69OrQi3lPMjm4eByeFhyL+l3CXWw1uBzVAYWiThg21/aDOwz1smAJUnjoPJr79J17alBV2dVVVoCEOYcL/sEZgooL9z69K53RwTvDpxzZKfDCa5Wq1cxDsq4ufUiw0o0+KoZQIypueYWeKnECpIBFM8WSKLTo/HB5aUw6To+/x/FPEwWdD03p5acgyLo/22lQfoHyZssc+hI7AZWeG17vfvKMM8TPolzeN0M22tTLRMvqrXKkoV2io5PwogR25PBTVDQsNkC2k75LRB8wfsB3YjC8ry/P5dpZ+3TN4Gk5zvaixpeZ6ETKFQdKJdYUTtj0piYKJut1jqFbcyzwmTgi4IE2ljcpjIK2ILEG1QiwKXh/VoyMK1PWoPWiZ77FvhhA5RG93dBguWlMDk9096in5D/PTHnihMyCGN3eFw2L28n3OAhjcTM4FWAfIz4PCWRgKw+7uoRRniYdImaTEU17FFhBNiJmqtLmaHIvEM0mbXzIgFMPFHArBhRtvmPlK+myXQ5n+3ZZI+EV3Iblcw0zn5WdIYmKB3eY/0BeeEya8sjSJIlIFkMZP42RxykNqDj3ARWR/EIDWdIQbkYhNycTZAxnNkqRSuxQRg8WwOlhTDpOjv4Lc9d52/KxLAZNje6/MFfSgomikSSdEsMILJPoQJ9EC2QtubCCYEC5OsHeVBCLpAIaGbI+kHHYa2t8RM8rpqa0praur5wKH4v+ydj1MTZxrHJ6w4s/SUW9Q044WRqFOX7JQYWRIFhACT8rMImzSWADIWJyjUiEB7kBytJHfEenRQCQPEVEN7JCWQIShOTMAZmNxMZ7x/6t733c1PfgQQaLH7hMlu3vfdfXc3vJ/9Ps++ed9vrj8HlcXVhq9BmQNhAmpb8yxNxsPkTf4bjyelMtlXO9WpTmzj92PRh9510eUdd1qT9VZJe3vPpoLJuk5rghAd8AVYDeIy046QC/eZQz4zbcGBnwN8IEdSTzZ1PQ8T3vZUmWhtCh12Dro7UTfnl8tj8LerUBN3ltTLIm6OB7g5i1AvrEzGKZMs5PwkwKQWzicywT6uTVImFSU3coukVUVx7vo/4aQJrAD/oqRIhpTJEqxtjVUn8wgmK+xz6fmFSUSURGWyLgB7qru0at+u6ZFu9QWoICqUUZjkxrgie1+Y4J9IpQ+4OUQ2h8nZi+qriYMW5wjsAUeAjYvkuHwhnwu3hByOgAVKPrfP4QjZE3+w88XVr/nu9LztJUw+/U8LDp2cOJiMXP5XNs4MwIfD1yq/VaJeHguj828ANgBQVubfIjcHW5j0rMzjWZOTr7IW490c7LO6u/ca77BTryXBJE2GX7gixY/FNbnnl38x4hkDcNKW0ko4Eyk2CmpbeY1gAmp7A90cLIut7ehCvufoYn6CMmnsqJXc7ihPiJm8rNyXudVOVslOpFWhwEgkAEuelN0olcpO4BeVx49LSztPvDdM4gMom8JEWlTfmdQbHgA56sdEgiPCaIpQgCcNm3RSXlR/nG8ivO0RTGaBIjE0vNCiOOyn+kjyz59//s11OD8tBxOcXMufnMzPX8CzXqMVFIBdAsvX8yArfyF/koPJS9SWnknK6jixULG+n0m/MmFsLuFPl69ztckr2dJvUSVrOAAJqm0F+T6gttM4VxunTFCUsksiKZRIqqGDFOm0lvaysns/LqdSXqpWyzthv9sITC50yuXyUnkV3i0HWer37rS2TZickr0/B7A0GR+C5W2PYJLTByFiILgHxLH+9NM//vTzc3hTk1b0QjxguOft2qjnFXA3Ft8ujo56jsLBuV8tLYGVox74uNiDHtZ2VhapYQPvefoEzQ0tq7+6vgfs2WRtDWr7cQQOV6pka2N3CbumzS+Cal95/gKPANaGway3r0aX0IPo/soiiIyOCWiPMFx67eq3n7D37cqXsn24mliWsqmiQop8kKPKB7ncUql88CANlzXdr5BucLX3Bya88fYHUyYq09+AowP+wOvv1hS9q0lWJZPk6dNY/DD/WA6Jcbq6Sn6tMx4VJ/v7S09uq5lydMMSq8Pga/1hcUn35dceovq5kU8fgNrY+3V35YH2ocDWrfAw4e3PBhNcpT9/izWT7gMadau3O/cPcyw8TD5Qw6i27A/X2uL6EQgy2LRtj2fye4xq/uf4n+Nh8mF+r0x220FbdhuTcTDGGC9FpzQRGLkz5Uda42HC234Y05Zx8MYIBQdl1CVOmwijJ8rDhIcJb/th2b8LTAQHZ8Y29kQzL3GVG3mYHDKYZJ1FdmHHMMmx2O0W4Xsc6AvrZlEzTNTeXtCaavspr9dbsIP68mrhpOCqxsbGlLOUF9c+eTqROqbXUvtoL74xkcnrnU011kvOpVQwoXbtkjAURW0Kk0z2RZICARbVKZlbvDAMI7cskMntRIiBXZLRJCabh8khh0lVqRrajdM7hYkwYKYdzYlp1LJl+ztoMGwyWzDW2mDQGBq8oq239xo0YnZIHNH5qW3Ud0fSAd6/vHn37s3qvK2LKqpvSm6y44o+6mrctNiXhf/Yi2+sQGsQD7PXQje+6fiDqWBiDI5sTJO2sbExI7UVS56Hw0HjhkCKKpNMv1/gsrgFgmZgAnILgZFpt9v9wggsNjJhJtgFKOG2NFMWfzQ5AhMqBpO0/0Hj2/RhgYnyfkVFxQ1ueIMduTkUFTAnwcRF+3YAk5rNph4XaTXj4zXiQcWW26sUQxxM2tPPbQcmZRAmzyR3uh6XlaWQFKriag4mTwrLN4eJZE9gghUXGAbZaxE5o10okzHn6obEYMJzwIJbbM0EQYExiJHsMASSMfbHKRPAELMj00IvY5TDTJtDfnJzgUKFHLQPYkTotjdvVETQ7KPpULNQ4KPdYLfCSPJ6ZfLRbx8D+y/fpg9TzISsKJXtJmYS4mBC+cENBi3ogN8fG5lAZetjvQYdcEdseh1717X1ter0NhWCCWbTFcN8vQ7JkAKdAhQTibSGYnC/TreBpD69nt1Ju14Pd4P2pdAh/2YWNb1W3ZBmUKdr3y5MasFbIRz8RtWT9wjxiuzJy+sAx9HCvqF2zcKkvKdL8qynB5ZS9PR8lhomvUmjbmN9NnC2OkXcSYLPelsxPFnwJoJZ+L9ZmPTpzoutOh108C4ok6dZYGHCUBmRBXBOkI5gGLjGIJig7IjXAj6ANWrVGQ7POcPxW1DsCioM6WFcRTChxpzByKZMgjIRRmFiNtt9ZrMbCAsSujMCtIT+D9IhcIVyI5gIMQvtxpA4wRIkinCZXl6mQ5ggxMFkM2WS8dFv3/EwOWwwOat+eHo3MOGUidtB03SgGfebaWi+6DP/4oYaFPnQEV6VlyAIwxCMDGhrhsViYgrCBDMRgwAbw0S6WAvJcUszThDi8VatAWx3TmzDVVYNQaRbQZbVQGjE2lagQm6BHaabYjDRpwPTEMOx4zqS+1douYm/APhK0hOBSXndHRJveSwpk3x1D2ACrJRJJoAKqQMq5HZZSwwmXXVlkrq6OqhjHqEiiVGYwsfJl6T0WlL0pQGerXgWLxgk0gmtDo6DTIBzAn7ZLaIgIkVELExAEXAm6fBnJtKSK8oNlAkzEowsgHOyOsCuzwRXg0YIE2YgOMYwI+FV6LUw08ExkJERds5QY0B6ZMCMAZQRXg2PZDAzwRkmYwDugwpDmIwFw853weAMSBgIjiBtsF6ZmAMYHHECE2RafMvQnRH6l0N2N1hYKJAGKEO6IEyALgnRy3Y72Jiy2F3CmDBx0QHMTZtdZCi1MgEw+Y6HyaGCyRn5GXzXyiQHKF+Lyw4cHMptoUNud9yg9OcIEa5S4d50m148+P2UVgMFhVasnZ0yfQ9h4hWfU+DFg4TV9kLToIDtS2Oasg4BmIiKbTWadlxPAM0xSOjwghrDVN+sCcBE8yukkynmFEBlMpygTJQlV6CV9CcFYBsRTJ6SxU8Lb+PYY0lt+URZtQKfKOwqvwdjqT+UQZhI4mDS0tElyevoUCAZUvgsdQBW3Z/kwQwTNUNTJr1qkDDZpjRaBW4Ve/t0Vt0GMMHaY8rkzNXkOVsQTKiwcxoqkXdzxqBzDugNkLTqhH7MNICJIOhcNVIo4x30Xpxz4DUNYZIBYMJmrBqZaZANPw84Byhmbs7IwYSZeTcHdwU9nXfOVSYhZkIhmNhjMMn00Q4HbcFIO20OmH0Y5qNdJGVeJgVCBBPMDxwihyNAARDRoFxUmJB+2i4MwCSfeTvKhIfJoYLJkYfqY7uCCatM/HTI5XKb4XpyzMRK6FsbTPigoXgwHTQaE2KAVmNDv1toqPES41DuE8M2m22YgO1LfAt6HSJtek2NoWYINsWhvj6r2AQYomXjsSxM4pUJTBtP+BXEsa9Z693gmJ9J7lbfLKtuwTskj8vLW6ol9/Dawlo2bz1MgFqRcDGTjurqFIGWI9KmJnl9U9PFuKsIzgAKjf+zd/Y/aWRrHM901k1Os72EXZeYXszq2r21na1ekxGN1Up306Y7bXfpwKKFsmg1tE0V265mg8S0jqiti5vbihqQCvYG4kua8JtRfzHhN/+q+zznDDC8dJXa7cYbn6gMcwaYAc7H7/NyzuGb9Zbp6eEp/VMCvGBNxcoEr2iaXUlLU8G4kIwyifrkYMK7secGHHh3AS0Ak705d3BuLpoGloDegDbghk9AeCTcwep0dMuXBtkCDV6A0TKHje4VL4PJXhYmIAUS0a2T1JtSYZJTJjpnnBPiToRKStkUUwgUgw6+APwmODPOJAdoyIMJPArcHEHgMjDJJG3gkeAOv4VdzrhOF8+GVfKUCQ3YHCuTIwiTxs4B/hDKJCSK1L9JFsGEb65Ynzba+mxTZosEfXNaj6yw2VjrFHg0oPZ5h77CarVWGKnyD7MAbMWURQ/0cEnYZDWOmc11RmlqojkfJmq4kh+29h/4nJdqex8M4hDz7jbwX8CLmSFDg7V3H87w74LJUOZq9svefvHTJVK3LVEAACAASURBVGoXc4M+edOUh0IQfDF6JWtw7hWWVTtfEiY1uQBs0asxmFRv7Cai8JMOYniD/tmNBoWTGDPZwKgJIGJjd3cvmhZkhMZJGfgBtufNNWxF93wJemQGJjKDiQwwYTGZoG9FGzNRk7kYEKEfNQiStzgFsB+o8lbcSTn5Yphw9QCTejUTFM+FTPiQqPhDCvLFQJ/yWJn8P8HkcXa6trKVCRYt7og7ClhKKFYmLk9dv+QZr5hgqZvhApjU2SRwTtb0qw406HT9NOZKMABrnjDW1bs8tjA2DcNTjVs8RuALhclTfZ4yKYTJuUfMBkrC5Dq59UPtE9LQdr8b7SohQy/u1mIohcLk4btgsq+dbnnW0vRjS94Kte0W6Xe8DevHMhdp75f0+lhpZbJ/NmdvA1kQDfqg38srgAaASUKm2RzwUUCoQPMumA+3EswzmvXtAXCyDd40uDNpb6GbA8dmYaKGcDXKJOfupEL+TR04KmzOcEMckBJRDMUwwQAsYwWN1GbLUBTR79cpzPPRaVJCHzFmwut0OsMxKv4CmHx9JTvtUbnKhM4prWSXtKgphIl5XvKMWmygN6asAIRx/TrCxMIaLRJwZKydDBvnM8fnYOIi5in9tNkmVWl0zhR0tSqEicOoKpMwg4knLzVc33jxR7SLnSVh8gpXWvoBfl9q3rQnl3sJeYUTbP1HhcmNT/Jh8t39+/f2f/OLYiYqTPr0mlM0r+mnzAATuNh59O7I75LNpcJkmh1y4vnPjaWyOdDtN3Y3QE6gKJGZMtlQYbKb2NhwM0RgNgboMUdTw9EEujhytkEW3Mt70WV6pKCFiUaZsACsVpmoiV+MmYRowEPgDZim4Xmn4vfHMWbCO0UKE39WmVCY6GgANpvMSYqgZ0Lwm0epfGXCUtP7wWR6YpTZ+HB5fSSxsLDgY5uGYqg0XvvzbmBIKji/oFPJRQfjSqoGGlKpo0CI+kZKh7MFu1u+OnV4mJzPrqFRLkx2xFDcSeL+SBLTwvj++iNxQfvpjBut9lGj1EwmjPOuZgt2Hw1MzOZ54zpx2axrZpN9wpQPExI2rsLDzoAYGQeGrE2TqjHoaiaPrblqlcHkqX5quA8EhEuSpqs0a1ef/oLZl++CCQ/SpP3B5W5ifnLdRO41mMjQjQeELLa9NM/cYDB52LZEK2WX2l5eNaHL0d1WFIAtYSWyORQmLkvFmrndPuEijrDLHK5YNQNa5012D4WJeUw/3ldFtdaZ5iosvW3p6LhWSpkAAaJAgj15DsEBHo6sgQm3BUoFuFEteH0JWYUJjdnCkcuJ6J5bcPvm5JWgwKUBJEE4OhilMNmKbuGzV0d3We65OGaSVSab9Zgn5jBmwscVgUvFebIJIEHChBAmnDMSiauRVpoUdvpzMRNM7gB64BAhn1LlZ3P4tcxSwxcu/BYu64vr/m+gVV05KzDJFbY+urTPNCabtFpT0awLpYi4PgPItiOhNx43oVUWBjs6vzo0TD591Nn4fjDhkxHRvyngwsIRv7jJ8CL6c6lhwtv1NnPYCH6Na8xok4zrKOYl1c2xWM2ADaOD2CW9zabH/82regYTyQM9sN2mt5vGjBK4N2vgIVktkhF0TP26UZI8xjP0P/yq0WrFLM66vkJaPdg5L9G5gmfafjA/Gazt7a29e5W8ahvsvXy5gZA7vbW9gzfaECb80GAtXe/g1t3aG4MzB4bJv/ODvrzJwmImxG4zwkVKLrKKt9aneJV6m0difo3Do7cCX0iVxeiRMGL7rOPS+VLKBJixIW+hIGG5GZrNycBEkHehBRs2UHSkmZuDUVrQHPgwbAgCSDDdUy17MXlDYSIn0PEBjGBmqEQ2R6NMxEg9hj1C3LYYifgxAOuHD3/HwMXptwBhggmeSLIeoCKWyOagYvFTvPyJMqHCZB9l0pdbaRhX4iqrO9V4M8vwTfYUSZNHHfvCBDhSo4EJXJK4aSDw5hwNmHS2VFZWfpaPgecfAiaftORykOUO9IsrCg7PSYZ2dlTNl1IUrdRrd9iJy4H9xRRbP+OgQUWHGhaw493hGNxrjs3PjyNGpsMu9igHreGKNROzY7Ru1GGCXRN16zFsdY3DseE+9eljdB9vj8XsBzvl7xbRbTE3LLaTO0v371+He7eWXjx8RV2YoZcvZu4tmtQDr3fj7dWGpSXEy63FxTvlf25mu0OVTHCR/XiRfbH5ugnKzL7RM46+GGPNcDiGQVlSFY7FsF8MdPx0tmTM5KTPxwpEZF867cuVnpx0bwVleW7Lhzt20z7Yt8IaglvVtHLELQTT0OCFh6d3t8CtkRPwDD6sPMGak61lwIfb9446k0yf19H6d6eSMnBKaCeU4gwp/PAFdF92QkksuAeDbwFoE0NcCSm0zkTR1pmAZAmFUnwBpYpjJt59lEk4u9bwxJRmDljd6+WVwOQbHalZDky+9uJbFwxMBmZ1hMzOwldl1ofv8xyFCfc60NUVCLw+XTZMIgJVJpyyvbkdMqAyAWlyZJRJZ3ZGuduPb7MxaLev/PIBYKKdrq3sUcM1RRmO+ndMVMeXfMHC1MUh5rh5j1XRD/RqvDrzzqEn4OHLOdGmju9JSWXiFQS1PlUQmEuSGaTHdsq0fFUQctWyQvYotUFmoRNWCStkSmpZzauQOVouyuZkhvHRUTc47I+nN/UsdMLpsCKW1cRiUSwbnMPTwAjPa5I29D7PF1KqKGayrzLJLA96YYJo1homctdIV9fIzQR509q1cLPHTWp8rV2TPbCDjIwAP3oWuCxMdJMLN2/2LBR4Ogwm579nduqZulGpgcmOqFCYpECaR8RtgyLu+LePEEyu3X5GhUn9z03PKVhOdP567UPAhBwCJsf2F8XIHg98Vjqb8xHNW0KZcJxm2G/pgX6ZZp0GH1zBgGFt0/vGTDIwGWt3eLQwGWl9IwgJYaU1IJAVXLlzEkDCJYQMTCZzMCEct9AD11jKzelUKx/PP1I3ftXAJBmJGBAmzpRADG/FJGzviMmjApOBps6mpudfa2Dy6S9XvvzgMPn8wCdU1Xc4cx0Tozxzep1/gxk+mnHV6qjRmmr1teX9YYI8mb5l06w1zMsjIzQK8qY1MDv7pmtEIIHW2TmcP74ETDBmoit84ucd5+DvqcZKtMbP/6FunNXAJB4SFRozEcBl26bbcfHtEYEJ39J4rnKgiY4ia7n2jKdJmPPkQ8PkxMw3B7RvVy/88zB2Yf3bb46tHPuj4Y+/wT7i9S1mXizz2t3/2g8m/ePo5Mx7fstzc9gy4oHWLrQFmayMtP6PvfP9bRpJ47h2jSpZdwtSFqoc+6ZzutOGBtKtSk0wORKbjdWcHXajVUmKvN3YLy52jQm4itiKSKBVy5KkVeOwImijcJQK7s3uVRxXLdqFF/smuvuv7pmx0zj9sSV0r1C2U9QMnvHMeJr5+Ps8Y88ksw/7XxomV8/gOdK+A06g2pGAFybB6z9gmOApCOxNxnEQKHtEmQwE8NY5VzpmyMH4+PtHpqNjvl9VmVjHXzb8YYfhz8f3Q68h9DYH74VmyJHGf7aByYk/0X+/xVz47Fo3TJbJ53Ly0SEImBzB+eV0+L4Dk0PdMKE2gYnvIL5Zx92HlU6Nu5ExL0zon07+SADyVTD4lQOTxye/3yMwIbM3U/GD3mlhEiZfk5nz+ejOArNvuPQc+t/msPFCj28Hk2t/+yedEj49sSlMZsIzxCviHJ0PN2k6CzD5Ik1gcjk95yqTwnqYUO8exvfsc1NOGBpzI6e6YPLgOp4f/vY6tPt7Byb9P57cG1PDR7HGOhbFzhLq6tTVPpr+cGJsbGw8Ojn4mhywn/t3FvZhsh+2CdvD5MRnF4mRc83rM3HNnMvZ9MKd+dkm3b/cfLQ0i5XJcvjh0lyYwKR/Lvnw/h0sYMLN+aWuCbaj8dNj200NPyCPVGFl8tPjb046MBl4vEdgcuz29M2JqeEJ72wOjTch+4jekzAZ9XscsIG+vl/aNnRicH9cveEevYmPXgNMLmIH7F//S1hy7YMLndkcR5nQd+4mk8n0At0/C5/JJgiQL7Lh5Jxj5pBUvEXwZUjtFidHo2ent4HJdYAJSJNv6Aff4qc0XWcsSJMf9sKf6904WDTxaQwRajI62R57E9HBncPk2ODg0NFXgcnoy/+rtGbn5pqeI56n36knKyurT7es6NRZ94kL25BpWrbIiVQut8l6z/mi1UOf5suWlY9tm03WrN36K8tGZsu0cpHfafEhLfUqp9W1yFZJotuo8TO/23WYDIx++gHQxGHJiVtr73BRQRcN1DuXlx4FB/A+PEtLl52kR3f6D7nJ7wSDhCoDwWCw+wki3/sHfrlhQfLKCDk/+PhxkA7295OyoMi9AJOAb+hme27q90fWHkHo8/XtGCYT8eFodPLI/1mZ8LN3w9mKR5p4zJwnqysjT7Y08KLnneumVLwgdM1ZvVVQE5tgINNemOSlQgIhxKlbrFEiJtoDz2Lt3for59jSlmk1diPTtERPu2IW2fyrtKrKCuv7pv0ocIJ1uu/g6Su7r0zoG7fWXs259bVnAFAbY5vqKTeZoijq1RroPsyI/31MDnz81mnO3mByLDp16vBVYkD1DJMKBH/Xp9+NrR3qpPnTWe8Rr88ksLg1TIbOjrvXpeI1XOuI8ILnNlvKuTeY6Fw9VELS5s/Il7g2TGJl+U2FScLsqXi+/EqOKr7czW3KRvIaZ9xGXTnz3q7DZGDAf+HGRfi5cfHr/aeW3giYDEbPdZZH6g0mfHN29iEPeLi/PNvEnwsLreXZGQwM+HQOQZ7lGQKR0TZM5knuru/1Uxcmiy9evFh0Iz//4+fvIHbp7CkvTPIw3vgcDDsNNINm2ORrbdVSoqHlHZhYJbhbBhqG0cC3bUYs5zRD7MPv3dS6Vb4uxfDLwfgFP9twbBnBNgwblHujpCOjZEN+3q6JPCknU3YzQbXleqhzM4vUGoaY10pkbUfDEIlREDKKGrlrZyCCM8uiYZR49/xMHe/KQxpJdcFEEw1cK50rQUFOF5W1YinvwiRU6tg6EbGkSKUSzkXVIbd3xFtizbAa2GiSa3BFRJBk7FqDIZ3F14xaV/fD+UXXmAtpTistG3cpdHgITsNGcM62SqQSt2+ELphMuO84+6Yv3dw1ZeJqA0ca7Ic3ACZD0UmKvjk83bsyaWXDhUJ4uVJZSCYL4SygI5ssFJJhYEcrncwWkgsVP383XEgmmxUPTBaSacjd8trhAy5Mnt4bgZ+nNLWIIyMjmCvRMx96YSJzRkzn8hZgI8RxClLyREYkkIk0ApOyBIciVWTCAfjqy5JuchJeelFkudw6mDB4JwuR5qEYjqsDS3SkqlAOZSgSUhQV8luKSeROSjJNBUlQWwaqlTi9M3ZTCCqQJMgW0RBkSsCl1ZCpSwqULyJJlyQB2ximypkw9soSPl+N4HWs3UauwQRKUpAu0BHyQjO2tGIaklSkRwhMRJToWBxCVeEgF5gcFOQx2aKnIJuVSKNSNNThVEtrcI0YEzZ5M9rwGkglyCSpeJsAg9RGcuEureKu4HDzcfeZJmsM0EXSNwrfBZPDp287vr3zf7m9mzDZD28UTOiJ+PhkfPyPvcNkLrzA8zMzlVa60JKbYSDG3XBTvp+c81ea4QW/PN/CkabcKiRbHZi0kndb/pnwbGSjMgmsjDx5/u+RFV/gGYlgmPR9+WXbQ5THG1EISjXPsWIdWRFVspgGW4RRUWKVcipnAUwaZUmV8W3cZhgNG/QyDABeDgl4NKANMAnwOmtRGisyOTz0M2wpFslBLkbQuJwgQNExoUwMq5SJ6oKIbDqiSDnGZj0wEVAxx+m8WsUrUzMRjCfGVGRKLkN7VY6nUhmIZCyGynMJOqZyFlNjCR5qbiM7MJEsAdpOxxr5WIwsTRtiE3IkL+LcORFVPYKCYoSEmRKYAG2haipVZD1r59eQpbGNOirTIajW4vBaCoxQJOs82WwiJauSR6UJpiIEZGzMiKwhMznRwVEmlSuT0zgHJrqcqiLL0zeg23Jug46cH3ZgcuZfV/Zh8tuFyWA8Ho9e8vUIE4ppJecq2BVSmQGOVOQkoCKb5iuVbGEUGLLMj2J0zKVboFzCoFFcmFSWw82ZmYV0mtmoTJ7fW4HfqyPfPV+556P7VjFMjnwy3OVjDiT0OqcUbU7IgYSgY7opYJg0XJ9JQlLw7VxHYr1ewqaQbCpuTbkNZg7SdY6tRhhFjeG7s0WX2aLsQq605kvJOTCREjDquCKdRwZGSwcmlIBqMbNIJxJ0AlcL8gGUheRusqNzGVdMCFa9ISmOt0cw1Ui7kSWvmQNpDF6miZbLdRtfYKK9nnWNrRLN0+0zCThJZXyu0elPWwLw8TzemwOqFU2dnGg4MEEhHOW9MDGd1sYSa1dtk2VfyPUZLkzq2Bldo93VLde5yc87K8z5zk0O7sPkN2zmXHmvb3r4XK8+k8h9x3rxO6wYBYb4s1n4L4ZJqxBO3m2O+uVsdtShzRpMZsN41j9ZEDYqk6cjq/D72cji4sgzIMgLV5l0z9MVTUM39KrpeluL+ItdcjVHBiFWgYJTCt7sRpIwTKQtN93TUaKKvQApDu9+04DBIiQQUonPAmDCr4MJlHNAqtJEqMRUrzLhxIgCMNFjqlMtFCdyyCTz1A0wNopYfDRMSESqs1pkQFdjnkZ6fCbQsaoai2gcB4aT5tpiDjEQu34GK2GSAxpebVKWPHv42KbQQDIPTRWxBYZ0xgMTbO1pXpgAX5BpWFj2rV2Wjdb8vW2YwFXkUWlzmLSVya/ugIWwD5O9ApPANF5N2jcVP9AjTCrz3TApeGDi9/Mzs2lACMBE3gCT+RYO8PU+ODTk8ygTahHDhMIwubfaRyLEZ9LdJpuTtLoJOsGBSRVvmfU/9s72p4lsDeCRKU2OClwUCbcX185qditrWhrSMmKRdnapW0rXVpCiGbSthPKidql2I4RGDaVKgcBqbCWkJNKYsMRcoutN9gN+8EuzX27uv3Sf58z0TXmxggtk50mg05kzZw4tz2+elzPPmbQEJMtkzo5r9Vm9PsEFYkQd698QJpKeusD5QGWBG7Yp1u8Vgw/9G8GEwsDky7dMMjDRgPMgXZYEnthohIXwdhsL6itYfH6Xy+uF7iYRRj5z3iALYGL2+pgF8M1cQQuFiSkDk8n+rLXwIUxoMGkuzzKRYLLAWwb84NT4NoeJOFqBGL0DpixMAh9aJt2bwKTqS+SGz/z5v/+iyDq9XyyTO/oHhHxbPEx60u4QOjmGqWkMwqYd8ak8mExJeyIOcHOSHM3nhGh7fIO5Yfj3fnw2s2qdaJm8er6qJBpwc16tNqzBOwqTbDZHEi3blLDiTTuA/oLRi15MDiZ2MgQ/GpsYEmDyYaIdsPHrwsQ0gNbMmGTdWL3oOOUpTKAQJgKiJ2BZzzJhxKBEpvrRr5kohh0gQGeruMDNcaEXw7cPmPIGmYPJnMi2IZwRkkC0jLFo1jAMxkzMNrZwVszcLRPJeSD9H1smCQxUw5Azlgm/AUyQSGw3lsYNSCPKK8o/ZDHSi9gzufd1CvZnsjmKwXs3dw4munLyww+yRu8fmDxoGWwsG9YPF50ankpxkXQ6lZziQ46RdATNk6ybk0ym00kuMgVGyUR6xOHGJHENRkvSU2m3eyQ9nUqCGgw2N4t5RPVsw+rrt2vg4bybfYcuzvuG/7z+Q8zmZOeZZHTbAsrgg39qUC270N8k3ipzMLFi0ifB2vxC91wwHybrZ3PEm/6QsMCCDxEbCgqJdnp3TjQNBTHgywcSbH8goMnChIw1TXbb8jyOPMskyHpjrthYghjHFoQgrqdh7rcLgTFWS3jWFwzYmnyYjMbz4SK5QeYCsKydx0gq2Fd87Bbiwc/e6hYS/UaazQnQiFBeFqZpEufwwu6gfyDnlxRYJr6gH65mJMYAP8dqA8I6MHENJXC0AST1QEywD+UBwxgIzFmCcJq96VbM76OItUufTZ78fE78Hztysbl1B2FSJqvzvoIJcwefPb5cVnw2h6fhjyQQI8Q5uAjYIzmYwBHOkwbfBtpwbnGiSTrOcRNiazhNhEnG6njf0NDwlsyuwssqIOQVkOT5KoWJsuViwaCM7WCz96NP4veyFpo+zQY46I0zZhmwMk8scKzdXwiT9g1gYsVFh704p4LFDTql3TUGPQSJxgd7WItFsGZhIthY1uZdzzIxEfstaG7REhMOje3XYCgYZMhEmEl49YGbg4v24PmwKzvIHEy87bQ1Bm8sNjp02uWcWZxnAmqcHzbhoXevQCM0rCXfBcrChOBlB9DNiVmwEWtbByYCjtbyK95O7O14tTyYaDOn2Zt80IhOCrTiZ1NgnJSfG5Q2fmq+LMPk75vNIeUP6qqkIGeRM2DTIyOY9J3iF+lrTTot/TKkR2amBTpFDdtI0+iFNB6b4nGXAWDy9aFD2eDq2traEYDI7OvfX1FDe2127Y/na9R0Ol9QDZXhQXusPN4YjUGtn+qWlRdVzMQjHgQ8KMQSQReoh4bPRHqNPF+QF1K7+MxcC3NAS9MZZj6WiEntGYGn/fBUzBrehdd20RHwLu9czjtR8VZGcBGXgLXsg4kgffUntFRdrX6tVvR9Alq/0UWTJQJv9c5pSG6QGVHwVl5LHzoyBbUBk0CHgl0apT9Zw/MFE+hNODTsqLs7f5qu2ipojLxZBR8H46eXZWhTEAE6UuY+Mck0CUqjJYwrlqDpXiuvynxq4mn2ppg/0wg/m4JY8OWzUoHUuvPnqmSY/I1hkifFPpsjTZnPvUo/Ndlp9blj2Qbirg9mdjOaH/AJCUmz1t7Prr2lKR2QE+slG9ef8rjpTMhiZ0mqs49eFJwaSAiuJ0XN25f+QrErElgQXPZPO1/9yeP/oNp1wTt1dp/6Mwt2q6lhF9z4enWZr2i4+doOBmB15bI677L81SUIpMeAP64yUPjGUEQ9k7UGyd/Ze6LWNrW3s2OfXY5F3d1kaS+YfbY/xM5+ysPTuvqjOwmT0+Wy7K6UAEzKTkgwefAFYWLIZ4YhhwxD7pDhY8JIhzbVJs3v7969frU3tUoZtNuD5s8/XxW0P9nO+bskfML6V1/yjO5QmSy7KiUAE+WxOhEmV3RKuWyjLPtTzuhKlLLsqijAzVGoqihMTtQdLQomJZ9eJ/rf25R/yiLL5rIAMFHIsptyGGGiUOjqrlypf/C1qjg358+vPlV6/7U9Gf1KFlk2lyoZJnsCJkrl0dPflB8GlnwhN8fcsz0xy2a8LFuIDJO9ABP8DpQqjUapVOz75UFV17Yo70uMhu2RyfTxAoPHfparWO/+Ny/DZI9YJgpqnigVW8ZMFPXDw3WKHYaJ+jYtrftiZhp+L8483UZXPzZvVfp8vO3GRofme3t7x+9uUeJzvq+vb1ScC9JTI7bVZCrPyiLDRLZM4IeGY7eyTFTX9K2t+uHDOwuTCrp4CRPhPN+R425u5vN7OnJPv0WtcHKq9u4GR5jl2tLSytLeTesuM4aHp2pPiTaK0ymZKI1bLXcgiwwT2TL5QOr0144eG9Y37ixMDjjogmkRjpsmM9x2YNJ4fnhTEmwOk5OV8zXzbZXzH59UIIZKESZmZ6cEk8P37illdZZhIsOkGMvkjl6HFZK+LxomLydGIp4IOjAVMx5P5CVsVC/GPZ7UbfJ0Iu5wx+NJEnG4U2TCjasdXUrCoeu4dglseGZAnyuWYGMJNl5EPJ4J9IeqoaOlJC4xfT3l8SSpp3T5PD7sMR42iHDoJT0rTmeYrmwwHr4adkbnKUxMK7jawd1lp3MFcfAoOg/NTgFM7hMyinaHcdTpjOJKTbjh7K0h5pVeMzH2rpih2xsIE6Zn2dnX4YyGKU8en/+G/pn1rYPyEyJ7FSZKpUpZ2ERDFApVdtFxbKDatI+8trJs2zK5oz9ESFXLY1WxMFnkuHjKEbpNqpNcHKjxFBd09SQj7kVyPIUUicwATJKhl44lsEwuxblIxBE6SKoj3EQyHq/AhRnjyQk3bETckWTIsUjAhvGk3Fz8ALnudkSgHS6XpD+HGaaHtVfxmndLl83RWme0lEZJntX2tXX2LQNMbvSEa0dN5G5faThaGTUSMl/Z1tHZ1mk6WdmFlssoga3O5b6OLsKM1nY+i/Z1gUvTZiRTfU58ZJDChPScjHZ0RMPLFCY/Sn7OzeazOlmv9yZMyJF/6MpUTD4b6r7/VqUbzpzHKEt0p48QVAVm3a6UuuEymSY7aJmcoEVNlMXDxFNBRrgl8tQBaFjkUoQkwakhdFWzCnFd6IhjOhQPLQJMlnAZaWz9nSMOB25riDrkPgAbYIY8BWgchN0V7tAl6AhgksKOlnB5WIVYtvFq7UPSdZ/8Vnv1fmXUxIzTGMez2miNuecGwKIrXIkR1HApwOJZ5W8Ak9K+LrP5kflk5crD8ba2R9DBsol0lYaJubMDTBhDjwSTtqgpY5mgbeLsnJJ8oMbmmzJM9jRMlJo7595ceNOiy6MJafmlhNy8UC/u0jTq31z45ad6jUJZ1nh0vb6gbR2RmbFTlklJa2t9XWvLoKJ4mMzgYvIRsEdg44DbUw3qH5k+LgVgJZgcnOBSL6GBx5EC4SZIhcex9AJ5o45zS9OXaOvppVTK4SEvHUlgUSheXUFbT+DC9ccu0vhrTVv4/+yd4Usi2xvHybED56a2M1qEeAls2UZ7Yb5oJ3FHg/nJDIIp65Q/F3KFwhcRocw6VBDXqEz41avYIC51cdvA7aV/xf2zfueMk2W1tIWku/t8l9XTzLF098yn7/Occ56ZU+P/22WXr6hHmYmrcxQmrfu4vWbjns80fRpPNxqNlGeFOpOGmTNhPR5iQ3CDGJNGY1AdYxqezx+WjWRrGyamMyEhUDtnggPm/le7v8LBdd2PMME1uRkszsuiwFNPwtN4pgMmbpcoBxeiup5lcEk3oIFINxNFRvzTgglygzvpijPBlWI0ULc/vQAAFzZJREFUtrb6nDDn3Lj0id8gjdGT8jD+Yy8xm9n7g5ycuobJ+83yYQsmeaITgod6fna2THMm9ZPEbPnLKB64mM3kTwhMDCqN5k9G1zMZozf5kgkmjYmmlLpYYE+rqTkS0xAQqHEKE3bGnM1Jp1XSXC6kU1RbFCa7Jkx2FxvsFTEtrEpPNcbwcnXQU1h50JngpRuY+MUSXM79AxPEt3WdHRF0WluLycnzbivCDpfF7e6ECV6QaaWmrJzkuQVZcXJWnre4HEaWBHNDQyT+MWCC3A67DcDRjXUm2OayW6JPLttIYLJJncl+y6IMlPP0Zs7H5/sklCHOxJzNSazjYVynMMnQGhhGEYyB+pdMok7zrZdHGRLPXBrJkfItZzJV3jd60+6xkLGp/Sq+klJXCg185VmkRsVwJoPXMPm245lg8FI81V46wu6YMKHJERL9bA+270bLLO7EPd/wHIXJWOF7zqQUaS1bQ06nG67rXsMEBfzXEjiTLjFZwnSMB8NDjCMmNsXgkLsTJqtyFpNLQMlOknCHhquBIOm2OomsvBJuNsMKY8CEr4k5sCZdcSZUUrCCnw4Twov67AWBwR6hCKUHvRP8cWLPCHNOrmGCDZhczFJ8DAxjhnY6omaGNjbJqTrFT504k6lMfpjYk5MBvJ8wZoloAlZqXdSLbHplN81u4V2WRDQf2BXmNkyW57Y9xIqkCjR+GXt7GyZ/0YRLg9n1XNGp3zHM0O3Kpx7iXrYLS/iAbcEkXTUW0b6rFmbMjxcLtypzKO2q16CewQTZpNqC+SfXOoi4edFihCyck3NH5fDqhhxEnTCR5JDioGuMuLWwvLH6apI+huUiZsb1ZjTaJKEPhUlN3vACTLrhTPi1kpILLlifAZPZi81y4hIP78+ebeZpyvRsf5M4k01qOvZmL44Ob8HkOJP5cv6lvEmcx8X5UTlzjIdPaIO8fj2ROSIWJU9TrvtfyhQm9UT56PwsQ/ljCRnlRZfT7Idllv2E36rs6504naS5FeZ8Il4lfUAYE989XYkvUlq0YNKgMHmbYg+WVHblw5baIIak+s+OShMvnz0N0jBg8q7Kbl9R63LlqW7t0COWcLGVidUiIsCk985EWDBVU1oRCXKIIc4c5VYul0MYJ3V7B0zQSFSWm8mSnbHikixg3lKTMB4RQ1ZunnAEZ8UihUlODnJu4EY3nAlTikVja2Z9rKfBZK+cKFNyrO9lSINce4QNicwZ9RPM+l45s4fP8jSBckl71fczicwJRU8mkcjTLMsFaRivPy8nMhf7+3TlSbl8lj8h8dJhnvTepyRiVo3C5+8mUktL26kxgpVqIa1+o1f6ljpmvJPdr8SQnKoTc8ypWkjHqwQxf6mnxod7rVLqfPv6Gi9PxNMFdQfzK/F0Wt0iwJippuMT1QlqSZjlbfXrP6Qx81lVje8qXd9hIyfOW+C67n3OxKRJTRtB1zAJW9un8YgwrSR1V+dsDrJmYxFdjvgZnDMSrdghjGuRyKRFT5L4B/lIXz0pB23Akm7lTLxD7emKp8HkcPTjQKs99XHUeB5d/3P4ob5GrmTqz6nWTM/xeqv38MfrxvrNq95nLlrPx+YxX/junVhmlh/c2GesmZ85WLr1Izu0dDBjmI23nz61KjPN3d3ed6ORpFlu3R0U1+Cy7oPZHL5SoyyRuOvIZyQsOgwIYIzckqhTvemECS0qbBNICMQZMEFcUZR1XQ6NBOQYndtxI9JXlqMMBDldzJk8DybnN/bmgdZ9D8TcO9B5hKlfnB/u3fq25pvydXmQ3vzY775bZN5rEDs2klDVuB9ggtA0ZUk7uYHcQTlLicBn17wBXZQES/QOTLiKQGd/uZD4xoAJVuSwIrwJRSZ9+gZdKctTmKwm5TVYatItZ/JMmBxmDrs9euoktikfjfbVgLZ44aruB5iQwTxeLN1KlDJZOUw5L+jipCLXMLaGOmGCuGRTIL8v7KJoJ8cUErIS/GBXMzQ5Em4GyCvDNXK8Yo/oCtCkt85k+Hi426OHeX95+R4uItBDMLEhTuhY+k6sSSin1ZqyhANNMafNG2GOfONMGEkWc1kpLK8yWJPD0mRWDpVKITnkJF9GSjlR1ozZHL/evL2KFvTyzgQEekmYWO8uVEVcTZdlOSLxVrckyvpGrDmEY8SZlHR/azYHrYmkQ7M4iZA3qOsCKuqyHpsPOREqkTPNNRLm0GkdSZ93Qtqkl84EBHpZmNzbnON+5df8XhqiMPZKgJv0cVYv+ev0jZgdsGVaGx+i+VVkcwU45B6qDCGHxWZFjEMQ7OSE0Re9GuIAHOBMQL8vTOheYMybM8W8GyE3BUyHgyEdGPf1XpzW1pzWb1i6Ph+13Q7szXlRZ2JzOGF0g/oMJqC+cyYM/zhMsqH5Bdg9CwKYgDN5QF5h+hV95gNZpTL5GEyc01ERCraDACbgTO7J6tckyaj6I0hZv5blHs2ZCBEJxjcIYALO5K5GlErAgIlNUax4WnI9BhM+EIECHyCACTiTe0KT2GHAZEgTsEOTHi9BIABMQAATcCYP/l9ZKEyYgGThxxVlnH8MJr7IKoxvEMAEnMkDshvORJC8Ac0+rjxattFdDBcluOsDCGACzuRhZ0JgEiCBTvZxmODp+UgSCrWDXhImNlBPxT3NmQQ0TbGiHwhznOGwi2NgiINeDCZvXG9AvZXvSc7Ep2kW7NUeTcDygUgNxjfoZZ0JBBo9luWHnAmy+aSAzYqRojjdguSD2RxQ38EEUnS91o/lTARNkzTFj7FLU7KSH/0ATGDRGghg8luJ+bGcyRt/hShgtPyCDT8CE+94DJbTgwAmvx9Mur9reDo8vwob/UAvCxMov9sHYU7365mMuKAWKuiFYeL77wSot/qXg0proF9AyPe3hwX1UoP/clBpDfRLOJO/2UFQL5UGZwL6JfQfgEk/wAScCQicCQicCQgEzqQ7YtknnGHvH+uGMxGmA7ALBwTO5Gc3FhPqd/4F0yvVuyhJq6k4+1xnYvVazay5l7sDk9VQaIGH0QwCZ/JT+5IU3mK/d2am0HGKrS4uzc3spp/lTKz+hZixpNVaWYhpd2DCuaLhVzCaQf3tTExfTh5bLaNxY9fZ9vnO59sdBtunfmJmXEct5kP7w7Zgwt463P7Aha2Vjo/NqjN49/UBvmKf4UycxWA0OE0a/AJplO7lTEoRKF0C6mtnwqZTjWqa9FDVQrVBHHqaNLbJkXjrMBvf/j975/OaONfF8ZdGhcNYmastBAn0pZZW3VgXGoqmCkEiWbSBxEALurFkIbOYUglFCK0IsTyz7sLVbNWlf+F7brS/pn2ZTmfmqc6cb5kkXqNw7uR+/J57b248fb4fG4s9d/0MzzaCL9DxbMsw8ZsWJSspx9CRBRhG2LAWwWFdGLruWRwmTPfnxTx23XB8z+GfsizuT8aew+aISeGpkiUOzTc4k7XP9WwAk9DnC7nyHCYqwYS01M6E6adlEIYGY3Z7KICYYs6w24bqZNqE6ik2mKkIUEgx5hcAin2TjXHfHJjMaANURzpjZyIItt3WmYGfL/fNFfUlfvlWMkdFg+niSApCGTlMLwxFGFjQk6zuF4/5GHOzZ7KpOBSaSBV8f8LMfhmg7TNz0HekMZ4q6S/B5PvOJLQHubkzSUDmOUwEVZHpaiYtszMZwcTrQddhXbC9abntOF0YjYeQ7qW6MJa8and822xaZrd55tlV3ymIZ96wbITt4tQ7halklJu3eLqoO8Nqzxv9v+6FpYeJ1RzhP2SBB1OnHYTSR7BgXaAz2bHa1TNER/HWG2KlTEGcepwXenEkpWCE9WaHdQEM5tjNwY5dvGVvG82ZwwS1+4IzqSsq9cCSlteZMF2w0Z/3wZO6RV1iI8Fy2qIuGdVTJp3BrTQqo2k5gx2ECDYVX9eLbQstv27yZMAoT7BhpSQ09qLjY+Njz36UV4cmp6IzFkRbGgiWBwOJmcOm5XwZmowZwmTYHDO2A1OGwDllUwRK0HeiN3kFoF8zMD9KnWGqt8PHb9vWW/pMUPIdTDZegEmiU8rT80BJy+tM/KBz0UNstAvhsNQHhIltMr08YbyUddPdLqY9E2kA1WHPYuYEysMdCxtVz+4WhAmbIG3C7Ep0zkDEU6Ggr6g16YE1afea1lXb7IGHMfUE3/kyYXzMBmCA+z60eYRtNq0a8yARJrzPVRyNzaBPlo2r7VuvXx06v8GZJGoHBBPSEjuTRzBph3l7+RYm5Qmqj77dG7UB3UnYO8XWYzkF6H4dVSesz2EStjlMhvzM3qrCxBB63b5RnaLZeAYTsYmRY+WMgggXMGGBM0E31rObMJkbMjRyEpO+gs9+vTOpKy26mklL7Ex0uFqkORwmz5wJpjmWJJmW41i6FO7BAA8lsw9TAzAPMqrc5e8wyS/yNGcgSczSV3Y4py0Wx+FCoTqWxg9pzhwmvbHQ1THUsyDCBUx0M4CJZTHJKhQt5jjMvCpaCJM+jNkbncli6bTMS6M51AFLWurRHHME/VSv2nXYi85E8oRuKjUUPKtYOPNGcGtVCynPhrEF7VQK0x9micLXvojZTdABO4DRys4z6aPhwk1TZ3qh3EuNMDj9DiZoVmxTF5vT8VfMeDhMWErsBX0mA/jq3TYxfntosSnYntErivpb+kxiuZP8RS6DCU0uW2nlMsI3ozk0NExaamfCrCveY4iN496ZFDhMqos0J9wrA5QHZngH98LICV5X0dT3AdJDfpZhl5sDW9SZ38VvGlqrOm+N3YLN2BidGqZ9bQzF1gPnMYeJeYoQ8UQsPkVnksb6mnLYcGdig8AHz/VmGd3JBIQyFLw3jeac5yv418CEBnf5Sif01Jm0CCakpXYmfNKa7/N+DoNPONMNk0/aCvPBmmAeF9LG84KpaHwfTG6bv8aPGY7BR3YsXQ8P8beYOb7nO6s7B9aZx2wFwzS+z4MNqmE+n033Db4J6oDXUtjxdSkwcDxsXoGWwftRjLOp92230Sudycb1YkHpteBAfvIQrnrn4HiPrmbSEjuT8OM54vNJ5Y/mlH9vOj3KB/HWm8DkrmDVbw7+Nti7LVtsHp9j2MEoz5PS8AuV8CvuGm5c1q7pYiYttTP5afWaUIUr6y+8mRDTntGr4v4V65lEQnQpk5bfmfykMAGwzL/yxmRTD78qblppjUTO5LXZwd+6xsEr46aV1kh/jDORSO8qRs6E9Ic4k392SO+rXXImpD8CJvREv3fXb3miH4n078OEnjX8zvo9zxomkQgmfyVMXuVM1uXg8cGbcjabIZiQCCakl9Kc7zsTIaPWghv95E4+n6/VBYIJaelg8jFOel+tvcaZxCqVTrAEQfbzfk7uVHIEE9KywWR39wPpfZV5jTOJnefmiyNFI/Bf4Tp/QjAhLZ0zWQt+E0nvpuir+kyERyutoT1ZHBJMSAQT0hOY/NhKaxD6XNklmJAIJqS3OBN47Ewu8nUgmJAIJqSfdSb1/HmIYEIimJB+1pns5xt3DCGYkAgmpB92JsJiQelspREFggmJYEJ6ozPJ1dX8p/o1yJWKelKv0zwTEsGE9CZnIqj5SoUvKF2vcOXPCSYkggnpTc5kM8aVgHiwj20STEjLDZPIM7JEBBAIN0sxmvOCCCakZYVJJB79BhywLWflPaAmvwSjOQQT0urAJLJ3UU88oUlSPdQ07WBLoDZPzoRE+gGYxFo3aiL5cJ0LJ+6so9bcmZzmZBHSkUXqM898khEsS4aelGEJpUXkTEgEk1bjRo0lH3pQ8hqfJ6VqNQgl0x/lXBQtSgRico5nPtFMDDLyOmdHUBYP3lyT5U0yMuRMSASTxs352h1NIqFLV4ZIJL4lRyLbNcV1j2RERwsPDurpyPphpzNzlRZvA7yslE1Hojf8zf00MYKcCemvh0nj5tPGXRE0tAM1EwVAOOS14/OOpmSgpZVaDcXdgjXXVRqtQ00FONdK5zczZQNNzJHacJUYZTrkTEgEE8x0ovcFeU1zj1rrgiBrR3GA1uF+XFHWAbLucXJt5mYBcrODeOLwMAFQ1xpQ07Ao26LJK+RMSASTRqMl3xdFQtlOydUOZfQeKuDLWEh2a3gQLSmxdfeIP+T20l3PuceqqrbcS3Qmys1WAogl5ExIBJObVu6hB5av8JXM5bU8Jjz7vH81CVvoP3B/PPsQc/OAqVBNy1277ozrMh1vKa6mfCKYkDMhEUw+7T6wZE/dR3DA+uwgonJngiWRuTOJl5RtdCYCOpNj7kwqe7HYdiIREiAuI0+uaTzn33EmcbqEScuiNMLkXslY6+bTWvqhYFtRcumIsKUdpWW3tJ1M38y24spsIymcaJfpNdc9EdLXbimeOFRyIOQ69Yh6gw3hs3YBEdIrFVqP3/8HJJO4TfznY/SV+pCIkkhLovjGx829O8XXVXU3fv9ybzPeUC7ruYujQzUarym1/dZBaTd0ruRPLo4Ps9FMSTmu1y+Viygvy9bzeNRROnL9+CD36FtI39FaYvOJ/tfe+fOoqoRx+ESM9xKRGHUbm5NYuEqDVGQymaEgJFQzFYUNH4BQSGgoLfdjX/4dFlz0nlzZsHvP7yk2s6JTvGMe33lnBvQfG9yyH3xDNp1HXSyXx87VyaL4f7lY1s3iT9moX1q2LxatunFEYJ/gx0QB4Nsx2ywQhK/G79dMAPhKBVg8HvTLAZkAyARAJgAyAZAJAJAJZAIAZAIgEwCZgGdR1ov1FjIBkAl4jl3iSCqdeD+ITLb6r0dzTfUDggsgkz+IVDAuMsEZjaf/KpOtvtAe9qZb0q6bprQwqAAy+WOYBpxE9k5bmwFl3vqhTGbXIBNUeucHZ4Rdavw69De1RYIAgwE5xH7xPTy+dl59PWqqFhuQydgkTOajsDA2xQPJmbd9IBPD4uKSuEHGpa/c6+/Nem8rXoAAgwE58zzt3Tss7nwvJTmpykXsIJNRUWxCzTydIIwEM3WXsfSuTF4CkvllSrIyHO7pvyETNfIQYjAcWuYo6k9KeNhKrWNOyU9VnZMEMhk3bYwKfVwJ9UTRsHm2viMT3SFJc9MSxafSvCMTBzIBn/XTx1N1JR2DtmRiksDnuUwUJ5tCJmMyIVluiIC56pUXU5yIXftlMslodeWlss08o3avnaywPYeSWM8Bw+ESU9WMqd6WiW6oRiETNSEmZDImPi+qGm42yZOSQiZnFvbK5NWiZj0/FUlZL9Ezsf/Y397L2uOoW9ERQQZD4dEy+Vi2ZZLnJJVMzsyATMYk5mWR5KAuM1bUyW3i9cokJVVeMpOck3klCnH52N+Jd9dvUm4gyGAoHKn2yKTOTK78DJmMSVgPgOawaFpOQPtlcqqrW9tCJlVGYpD4Y3+rk2jbwxY+bg4LBsPqlUmdmdjch0zGJOFu7Xar3Itmk6hXJmpMqjf6lISz8hPU6/WE185XOtVYAJ7NTMSDzMRgJ8hkTAxeyeNKK1ekzO2XySHkQambybye93j9O9ewmgM+jTe6fpeJonQzk7RZPIBMRmFNRblh5GCWla2Zw81+maiKS6xm/WYT8cud+culs88kQojBcPi89MWR5DLZi+Z378SKyXpAdchkTJSQlZtUjWpkUuZM78gkf09GPGPxstrZb4Sm97bAhm2ZWCFCDIbjWNXpdMstNsM21Tlb5o7RpKdAJuMOjyjLVmdajJJNSWfzyM12+pUrCZVSEBHeP058IpdN3VwExEeEwYBEskmIQ/pyM2Nv5AKZjIRBSJyPSh79qU9vFnY/nBrW7DCKAuPRs0APidOcGvYSDQEGAzKnzdzG8TrJ8cp6P1cGmYw2D6VMJoZ5TS1Obg75/sebIykIKvgkJo0m4u4Optnm/SQxZDIapkcYJ5xx63aDGe60Br4jkMmYOnEvThTbMxUyAZAJeIbDnYkJZAIgEzAIkAmATABkAiATAJkAAJn8v/gLMgGQCRjCJX9DJgAyAU+j5C75By5rMb7b2aXQAAAAAElFTkSuQmCC" width="1100" height="337" />

**Note**: For more information see [Firefox JavaScript Debugger](https://developer.mozilla.org/en-US/docs/Tools/Debugger).

Functions and interfaces available in workers
---------------------------------------------

You can use most standard JavaScript features inside a web worker, including:

-   [`Navigator`](../navigator)
-   [`XMLHttpRequest`](../xmlhttprequest)
-   [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array), [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date), [`Math`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math), and [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
-   [`WindowOrWorkerGlobalScope.setTimeout`](../windoworworkerglobalscope/settimeout) and [`WindowOrWorkerGlobalScope.setInterval`](../windoworworkerglobalscope/setinterval)

The main thing you *can't* do in a Worker is directly affect the parent page. This includes manipulating the DOM and using that page's objects. You have to do it indirectly, by sending a message back to the main script via [`DedicatedWorkerGlobalScope.postMessage`](../dedicatedworkerglobalscope/postmessage), then actioning the changes from there.

You can test whether a method is available to workers using the site: <https://worker-playground.glitch.me/> . For example, if you enter [EventSource](../eventsource) into the site on Firefox 84 you'll see that this is not supported in service workers, but is in dedicated and shared workers.

**Note**: For a complete list of functions available to workers, see [Functions and interfaces available to workers](functions_and_classes_available_to_workers).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#workers">HTML Living Standard<br />
<span class="small">The definition of 'Web workers' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

See also
--------

-   `Worker` interface
-   `SharedWorker` interface
-   [Functions available to workers](functions_and_classes_available_to_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers</a>
