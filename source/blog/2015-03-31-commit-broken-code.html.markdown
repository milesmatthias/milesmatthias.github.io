---
title: Commit Broken Code
date: 2015-03-31 16:38 UTC
tags: []
---
One of the mantras that new developers are sometimes taught is that they should never make a commit until their code is working. This is true in some situations, but for the majority of use cases, it destroys all collaboration that tools like git and the internet afford new teams of developers. It can also leave new developers feeling stranded and alone in their difficult quest to become a better developer.

## Git in the Real World

When first learning to code, they usually start with some simple examples of git branches and show you the following setup:

* master <-- the branch you put production ready code into and deploy to production from.
* staging <-- the branch you put new code into and deploy to a staging or test server from.

They'll then tell you that since you deploy code to the staging environment from the staging branch, you should only commit and push working code to the staging branch. This makes sense and is generally what real world develompent teams do. However, if you look at the branches in a real world repository at any point in time, you'll usually see branches like this:

* master <-- the branch you put production ready code into and deploy to production from.
* staging <-- the branch you put new code into and deploy to a staging or test server from.
* new-buttons <-- "Some new buttons I'm working on. Our buttons look pretty crappy right now."
* feature-123 <-- "I'm working on a cool new feature, but it's nowhere near ready."

The branches `new-buttons` and `feature-123` aren't merged into staging or master. They have been created from (aka branched off of) the staging or master branch, but they're just random branches that have code that isn't anywhere near ready to include in deployments. Most likely, a more design oriented developer wanted to start working on some new buttons for the site, so they created a new branch, did some work, but not all of it, commited it, and pushed the branch to the repo for other people to see. Now that they've shared their work through a branch, even though it's not finished yet, the following is now possible:

* other members of the team checkout the `new-buttons` branch and give the developer feedback
  * "I saw you're working on some new buttons. They look a lot better! Have you tried green? Green is cool."
* other members of the team checkout the `new-buttons` branch and make improvements of their own
  * "Hey I saw your work on the new buttons and noticed they weren't rendering correctly in Firefox, so I made a few tweaks and pushed them to that branch."

This is exactly what git and the internet were made for. People are in the middle of working on things, but other people can see their work, so they can comment and contribute.

This is the entire basis of open source. Think about it: you usually can't sit next to or call up the creator of an open source tool. Instead you fork it, do some work, make your changes public, and let anyone who wants to help see how far you got, the direction you're headed, and what challenges you're running into. Usually when you do this, people want to help. They'll give you advice and submit pull requests to you to address the challenges you run into -- all without talking to or meeting the people who are now your teammates.

This also makes sense when you think about how people work. Imagine if you were building a playset for your children in your back yard. You wouldn't do it all in one night. It's most likely something you'd work on for a few hours, come back at a later time, make some more progress, and repeat the process until it's done. All the while it's not ready for actual use so you don't let you kids play on it yet. (aka -- you don't merge your branch full of work in progress code into branches deemed as "production" ready.)

In fact, one of the criteria of hiring engineers I've seen used is their ability to contribute to open source. If you can jump into an existing project, learn the code, understand git branching enough to work on some new feature without messing up the production ready version of the project and get feedback/help from other contributors, then you'll work great on a team of developers. This skill is even more important if you'd like to work remotely.

Another piece of advice: it doesn't count as progress unless it's code. Creating long documents full of explanations or diagrams of features without writing any code isn't progress. Code is the only thing that matters when it comes to a team of developers. Either put it in code or it didn't happen.
