---
layout: post
title: The Current State of Client-Side Storage
date: '2012-04-18'
tags: []
tumblr_url: http://milesmatthias.tumblr.com/post/21323839252/the-current-state-of-client-side-storage
---
One of the biggest parts of developing the next generation of web applications is the ability to store data on the user’s browser. With the goal of being snappy quick, nothing is faster than getting data from the user’s machine instead of wasting time waiting for a server to send it to the web application. Storing data on the client is still a work in progress as the community continues to flesh out standards for the next generation of web apps, but this article is meant to serve as a summary of the current designs in storing data in a browser.

"Web" or "DOM" Storage

"Web" or "DOM" storage was orginially part of the HTML5 standard by W3C, but is now a separate W3C spec. Please note that while some places may call it "DOM" storage, this type of storage has nothing to do with the Document Object Model. "Web" storage is broken down into two types:

Session Storage

Per-page-per-window storage You don’t want to use this type of storage if you want multiple windows of your app running in the same browser to be able to communicate with each other.
Limited to lifetime of window When the user closes their browser window, this data is gone.
Separation This is a good option if you want the user to be able to use your app in multiple windows without interfering with each other
To use session storage, use the sessionStorage keyword in javascript:

sessionStorage.setItem(key, value);
sessionStorage.getItem(key);


Local Storage

Per Domain When the user has multiple tabs or windows open connected to your app, if they’re all coming from the same domain (example.com), they will all be sharing the same data.
Persists after the browser has been closed. The next time your user comes back to your web app (barring them resetting their browser), you’ll be able to access the data from the last visit.
To use local storage, use the localStorage keyword in javascript:

localStorage.setItem(key, value);
localStorage.getItem(key);


Notes about Web Storage (both Session and Local storage)

Limited Data If you use either of these types of storage, you’re limited to 5 MB in Firefox, Chrome, and Opera. In Internet Explorer, you’re allowed 10 MB.
Very basic It is strictly a client-side, key-value pair storage implementation. No tables, relationships, or anything like that. 
(Note: You might be wondering, is Web storage equivalent to setting a cookie? No. Cookies are generally set by using HTTP requests to let both the browser and the server know that they’re setting a cookie. Then both the client and server have access to them, as opposed to setting values in javascript in the browser only where the server can’t see them on its own.)

WebSQL

SQLite Browser Implementation The browser stores a SQLite database and provides a javascript API to interact with that database and do everything you would normally do with a SQLite database.
Limited support Only implemented in Chrome, Safari, Opera, iOS Safari, Opera Mobile, and Android Browser.
Discontinued Although some browsers currently support it and plan to continue supporting it, WebSQL has been dropped as an official standard by the W3C. (They decided to go with IndexedDB instead.)
SQL!! Transaction based, relational database, SQL implementation with tables and rows. If you love SQL and don’t need to support every browser out there, this might be the way to go for the short to medium term.
Nice size The default database the browser will give you is 5 MB, but you can ask the browser for more storage, even unlimited storage if you want, and the user can approve your request.
IndexedDB

Official database-in-browser implementation standard by W3C
NoSQL, key-value, and transactional You get the advantages of transactions, but without all of the schema business.
Asynchronous You don’t need to wait for the database to finish doing its business in order to keep allowing your user to use your app. There is also a synchronous API if you want it.
Object Oriented That allows you to store javascript objects, decreasing the amount of data format conversion you need to be doing.
Uses requests and indexes Very nice.
Same origin policy Requests to use an established database must be from the same domain, use the same application protocol, and use the same port.
Big sizes Firefox allows up to 50 MB before you need to ask the user to approve more and Chrome allows 5 MB but allows for unlimited storage if you declare it in your manifest file and the user approves it. I’m not sure of IE’s size limit.
Very, very cutting edge IndexedDB is currently only supported in Firefox, Chrome, and Internet Explorer 10.
Summary

Client side storage is still being thought about, designed, and implemented by browsers. We’re still a long way of having a solid, unifed, and universal method of storing data in the browser. The most advanced web applications that need to support all browsers use a combination of these implementations in order to make sure they can give their users the best performance that their browser supports. Depending on your project requirements, you may only need to use one of these methods. If you’re working on applications that push the limit of client side storage or you have any questions or comments, feel free to comment!

Further Reading

Web Storage - Wikipedia Summary

Web Storage - W3C Standard Draft

WebSQL - HTML5Doctor Introduction

WebSQL - Abandoned W3C Standard Draft

IndexedDB - W3C Standard Draft

IndexedDB - Mozilla Reference

IndexedDB - Mozilla Introduction
