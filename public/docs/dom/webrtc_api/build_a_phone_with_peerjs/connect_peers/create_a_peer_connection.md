Creating a peer connection
==========================

-   <a href="show_hide_html" class="button minimal">Previous</a>
-   <a href="creating_a_call" class="button minimal">Next</a>

Next, you want to ensure your users have a way of connecting with their peers. In order to connect two peers, you'll need the peer ID for one of them.

1.  Let's create a variable to contain the ID, and a function to request that the user enters it that we'll call later. Add this to the bottom of `script.js`:

        let code;
        function getStreamCode() {
            code = window.prompt('Please enter the sharing code');
        }

    The [`window.prompt()`](../../../window/prompt) method provides a convenient way of getting the relevant peer ID — you can use this when you want to collect the peerID needed to create the connection.

2.  Using the peerJS framework, you'll want to connect the `localPeer` to the `remotePeer`. PeerJS gives us the `connect()` function, which takes a peer ID to connect to. Add this block below your previous code:

            let conn;
            function connectPeers() {
                conn = peer.connect(code);
            }

3.  When a connection is created, let's use the PeerJS framework's `on(‘connection')` to set the remote peer’s ID and open the connection. The function for this listener accepts a `connection` object which is an instance of the `DataConnection` object (which is a wrapper around WebRTC’s [`RTCDataChannel`](../../../rtcdatachannel)); within this function you'll want to assign it to a variable. Again you’ll want to create the variable outside of the function so that you can assign it later. Add the following below your previous code:

        peer.on('connection', function(connection){
            conn = connection;
        });

-   <a href="show_hide_html" class="button minimal">Previous</a>
-   <a href="creating_a_call" class="button minimal">Next</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Build_a_phone_with_peerjs/Connect_peers/Create_a_peer_connection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Build_a_phone_with_peerjs/Connect_peers/Create_a_peer_connection</a>
