Building an Internet-Connected Phone with PeerJS
================================================

-   <a href="build_a_phone_with_peerjs/setup" class="button minimal">Next</a>

One of WebRTC's main issues is that it is pretty complicated to use and develop with — handling the signalling service and knowing when to call the right endpoint can get confusing. But there is some good news; [PeerJS](https://peerjs.com/) is a WebRTC framework that abstracts away all of the ice and signalling logic so that you can focus on the functionality of your application. There are two parts to PeerJS, the client-side framework and the server.

In this series of articles we will create a simple phone application using PeerJS. We’ll be using both the server and the client-side framework, but most of our work will be involved with handling the client-side code.

### Prerequisites

This is an intermediate level tutorial; before attempting it you should already be comfortable with:

-   [Vanilla JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
-   [Node](https://nodejs.org/en/docs/)
-   [Express](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs)
-   [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)

Before you get started, you'll want to make sure you've [installed node](https://nodejs.org/en/download/) and [Yarn](https://classic.yarnpkg.com/en/docs/install) (the instructions in later articles assume Yarn, but you can feel free to use [npm](https://docs.npmjs.com/getting-started/) or annother manager if you'd prefer).

**Note**

If you learn better by following step-by-step code, we've also provided this [tutorial in code](https://github.com/SamsungInternet/WebPhone/tree/master/tutorial), which you can use instead.

### Table of Contents

1.  [Setup](build_a_phone_with_peerjs/setup)
2.  [Connect Peers](build_a_phone_with_peerjs/connect_peers)
    1.  [Get Microphone Permission](build_a_phone_with_peerjs/connect_peers/get_microphone_permission)
    2.  [Showing and hiding HTML](build_a_phone_with_peerjs/connect_peers/show_hide_html)
    3.  [Create a Peer Connection](build_a_phone_with_peerjs/connect_peers/create_a_peer_connection)
    4.  [Creating a Call](build_a_phone_with_peerjs/connect_peers/creating_a_call)
    5.  [Answer a Call](build_a_phone_with_peerjs/connect_peers/answer_a_call)
    6.  [End a Call](build_a_phone_with_peerjs/connect_peers/end_a_call)
3.  [Deployment and Further Reading](build_a_phone_with_peerjs/deployment_and_further_reading)

-   <a href="build_a_phone_with_peerjs/setup" class="button minimal">Next</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Build_a_phone_with_peerjs" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Build_a_phone_with_peerjs</a>
