---
layout: post
title: A First Encounter with Meteor
date: '2012-05-11'
tags: []
tumblr_url: http://milesmatthias.tumblr.com/post/22840353320/a-first-encounter-with-meteor
---


A few weeks ago a group unveiled a new application platform that blurs the lines between server and client, called Meteor. With the main goal of helping developers write web applications "that are ready for 2012, not 1996", Meteor provides automatic data synchronization across multiple clients, automatic hot code pushes, and a “Smart Package” system that allows for easy feature inclusion.

The idea of writing web applications in one, consistent manner is an exciting one considering all of the different components you need to manage when building and operating a website. In addition to the numerous advantages it provides seasoned web developers, I can definitely see Meteor being a reason for more people to start learning web development since it significantly simplifies everything.

After getting over the intimidation of trying to learn a platform that four guys from MIT are writing, I decided to try to play around with Meteor and try to get a feel for it. First, I forked their repo on github and downloaded it to my machine.

I travel quite a bit, so I wanted to figure out how I could read their docs offline. It took me a while to notice that their docs folder in the repo is actually a meteor application itself. So all I had to do to read the docs locally was to launch it:

cd docs/
meteor


A few days later I added a note to the README in my forked repo and submitted a pull request to get this changed in the main repo. It was my first pull request on github ever, so I was excited, even if the change was minimal. Hopefully I helped someone else read the docs offline faster.

Then I started thinking about a very small web page to build with Meteor as a learning experience. I saw that they had some examples, so I decided to learn by modifying one into my small example. Their simplest example is called “leader board” and shows a list of scientists each with a corresponding score and a button that the user can click on to update a selected scientist’s score. Deploying the example to a server (Meteor set up a bunch of free servers to test on, how cool is that?!) will allow any client connected to the example to see the score changes in real time and sync their score increments to every other connected client.

The small task I wanted to do was to modify the leader board example to be a launch page where a user could input their email address to sign up for some sort of beta launch or private invite, and the number of people that have entered their email address would be displayed and synced to every connected client in real time.

It took me about 30 minutes to get the hang of everything Meteor and to build a working version:



The way it’s currently written syncs all emails given to every client connected however. That’s probably not desirable. So I started wondering how I could tell one collection to auto publish but not another. In addition to thinking about my own concerns about security, I was led to an article on the Britto Blog where I saw I can remove the auto publish package from my app and then publish individual collections manually, which would mean I would need to then subscribe to individual collections manually as well.

I’d like to actually implement that and publish it on my github account soon, in addition to think more about Meteor’s security and post any thoughts.
