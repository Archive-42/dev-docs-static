Ending a call
=============

-   <a href="../../build_a_phone_with_peerjs/connect_peers/answer_a_call" class="button minimal">Previous</a>
-   <a href="../../build_a_phone_with_peerjs/deployment_and_further_reading" class="button minimal">Next</a>

You've nearly finished! The last thing you want to do is ensure your callers have a way of ending a call. The most graceful way of doing this is to close the connection using the `close()` function, which you can do in an event listener for the hang up button.

1.  Add the following to the bottom of your `script.js` file:

        const hangUpBtn = document.querySelector('.hangup-btn');
        hangUpBtn.addEventListener('click', function (){
            conn.close();
            showCallContent();
        })

2.  When the connection has been closed, you also want to display the correct HTML content so you can just call your `showCallContent()` function. Within the `call` event, you also want to ensure the remote browser is updated. To achieve this, add another event listener within the `peer.on('call', function(stream){...}` event listener, within the conditional block.

        conn.on('close', function (){
            showCallContent();
        })

    This way, if the person who initiated the call clicks "Hang up" first, both browsers are still updated with the new state.

3.  Test out your app again, and try closing a call.

**Note**

The `on('close')` event that is called on the `conn` variable isn’t available in Firefox yet; this just means that in Firefox each caller will have to hang up individually.

**Warning**

The way we’ve currently coded things means that when a connection is closed, both browsers will be updated **only** if the person who started the call presses "Hang up" first. If the person who answered the call clicks "Hang up" first, the other caller will also have to click "Hang up" to see the correct HTML.

-   <a href="../../build_a_phone_with_peerjs/connect_peers/answer_a_call" class="button minimal">Previous</a>
-   <a href="../../build_a_phone_with_peerjs/deployment_and_further_reading" class="button minimal">Next</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/build_a_phone_with_peerjs/connect_peers/End_a_call" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/build_a_phone_with_peerjs/connect_peers/End_a_call</a>
