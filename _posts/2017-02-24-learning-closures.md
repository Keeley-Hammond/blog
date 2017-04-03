---
title: Learning Closures The Hard Way
description: A beginner's experience with a complicated JS topic.
header: Learning Closures
tags: javascript, Code Fellows, learning
---
We recently finished our final project for Code 201, the beginner Javascript class for Code Fellows PDX. During the project, we ran into an awesome challenge and one that made me very excited: closures.

I'm sure most people already know what closures are and how they work, but for a beginner, it was an eye-opening experience to use them in the wild.

My experience, in a nutshell, went like this:

1. {Intended Audience, JS Level, Purpose}
2. Needed to get five questions with four answers each (one correct) to user
3. Tried a for loop; didn’t work. What now?
4. Decided to stick to question[0] and question[1]
5. Called click handler in question[0] function to start question[1] after the user clicked - okay, working!
6. Now how to loop it? Let’s learn about closures
7. Fantasy vs Reality (pooping out questions)
8. Show how the two functions overlap and time out (hit over length)
9. Success!

So let's take a look at how we got started. The first thing I tried to write was a for loop with an event handler inside of it - we'd loop through the five questions, and the user could answer each one. Easy, right?:
{% highlight javascript linenos %}

  for (var i = 0; i < arr.length; i++) {
    var temp = arr[i];
    var randomSwapIndex = numGen(i, arr.length);
    arr[i] = arr[randomSwapIndex];
    arr[randomSwapIndex] = temp;
  }

{% endhighlight %}
