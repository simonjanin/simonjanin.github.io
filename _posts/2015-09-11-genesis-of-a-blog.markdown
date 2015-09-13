---
layout: post
title:  "Genesis of a Blog"
date:   2015-09-11 14:44:40
categories: meta blog
---
I have long had an interest in writting, especially on conceptual topics - this blog is my attempt at delivering value on the topics I know the best, as well as to learn more about topics I am less familiar with.

It's quite natural for me to write most of the posts in English, since it's the language that will certainly create the most value for most people; I expect to write some articles in French, and maybe a few in German if the opportunity arises.

###Formating

I will be using `mathjax` for formatting LaTeX, here's a test:

>$$e = \lim_{n \to \infty}{(1 + \frac{1}{n})^{n}}$$


This looks pretty good!

Let's try now to highlight some `assembly code`:

{% highlight asm linenos %}
bits 32

exec:
    xor eax, eax
    xor ebx, ebx
    xor ecx, ecx
    xor edx, edx

    mov al, 11

    ...

    int 0x80

    mov al, 1
    xor ebx, ebx
    int 0x80
{% endhighlight %}


###Looking forward
I set myself the goal to write a blog post every week for the next few months, either on a book I am reading, or on the various topics I'm interested in.

_I am looking forward to writting some more posts and I hope my readers will like it_!
