---
layout: post
title: Websockets are getting some much deserved love
date: '2012-09-24'
tags: []
tumblr_url: http://milesmatthias.tumblr.com/post/32200275321/websockets-are-getting-some-much-deserved-love
---
Websockets is a new standard protocol that allows for real-time bi-directional communication between the client and the server. A connection can be established and data can be sent as often or rarely as desired and the connection will still be there. If you’re still unsure about what this means, consider the fact that HTTP was designed for simple one-time requests and responses. Fetch a file and return a file. Websockets allow for true real time communication between the client and the server.

Since HTTP doesn’t inherently support behavior like this, socketio was made to hack together a real-time bi-directional connection over HTTP, but isn’t an official standard. It’s currently the de facto standard for real-time apps, but as the Websockets standard grows and is supported, expect socketio to be used for rare cases.

Interested in learning more? Check this stuff out:

It’s supported in all of the latest browsers (except IE of course).
There are some awesome demos out there.
Armin Ronacher gives an awesome in-depth introduction to building websocket support on the server side.
My favorite demo is a multi-screen aquarium!
