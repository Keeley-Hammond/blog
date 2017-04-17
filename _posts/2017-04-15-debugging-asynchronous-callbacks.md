---
title: Debugging Asynchronous Callbacks in Node
description: This post brought to you by two hours of teeth grinding
header: Debugging Asynchronous Callbacks in Node
---

This past week, we've been doing a lot of work with aynschronous processes in Node. While I'm a huge fan of Promises and would prefer to use them whenever possible, Marty has been insistent on us using callbacks, making sure that we have a solid foundation in callbacks and how asynch works before we move onto promises.

We've been mimicking CRUD requests with a database that we wrote ourselves - and I have to say, I've really enjoyed it. Debugging asynch issues has been oddly fun, and I wanted to record a few thoughts and questions while they were fresh in my head.

*Dev Environment:* I've been working in VS Code with Node, Mocha and Chai for unit testing. I added mocha to my scripts for "npm test" and mocha -w for "npm run test:watch", which is nice, but I don't like to use while debugging because I find that it clutters my console messages.

So, one of the trickiest bugs that dereailed me for a while was this one:

Can you spot the problem right away? You probably can, but let me tell you: *I sure couldn't.*

In case you can't spot the problem as well, come take this journey with me.

So the first thing I could figure out is that my 