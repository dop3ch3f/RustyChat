# RustyChat
Chat client made using Rust, Cursive, and PubNub.

## What is RustyChat?
RustyChat is a realtime chat using the [Rust language](https://www.rust-lang.org/), [Cursive](https://github.com/gyscos/cursive) as a Terminal UI, and the [PubNub REST API](https://www.pubnub.com/http-rest-push-api/?devrel_gh=sambarustchat) to send and receive messages. 
I used a seperate thread to run a subscribe loop that pings PubNub for new messages. It will try to receive messages using a time token until the request times out or we get a message. The next request either has an updated time token if we got a response back or will redo that same request. 
The main thread handles creating our UI using Cursive. It calls the publish function and also checks for more information to be sent to the UI.

## What is PubNub?
[PubNub](https://www.pubnub.com/?devrel_gh=sambarustchat) is a Realtime Data Streaming Network, essentially a Pub/Sub provider. They provide over 75 SDKs in addoition to their HTTP REST API. They have a huge free trial that allows users to send up to a million messages a month for free. 

**Sign up for PubNub click here:**

<a href="https://dashboard.pubnub.com/signup?devrel_gh=YOUR-REPO-NAME">
    <img alt="PubNub Signup" src="https://i.imgur.com/og5DDjf.png" width=260 height=97/>
</a>

## Why RustyChat?
I wanted to create a Pub/Sub project in Rust and I think a multi user chat is a great demonstration of Pub/Sub. The concepts behind this project can be used towards any use case where one would want to publish and subscribe to channels. I soon want to integrate this into a Web Assembly application. 

## Installation
Use ```curl https://sh.rustup.rs -sSf | sh``` inside your command line interface to install Rust using rustup

Next run ```cargo run``` while inside of the folder containing cargo.toml

Your CLI should show packages being installed then the Cursive TUI should pop up asking for a username and channel name. 

Open up two or more CLIs to simulate multiple users chatting in one channel!

## Contributors
[Samba Diallo](https://www.pubnub.com/blog/author/samba_diallo/?devrel_gh=sambarustchat)

Special thank you to [Jay Oster](https://github.com/parasyte) for both explaining and contributing!



