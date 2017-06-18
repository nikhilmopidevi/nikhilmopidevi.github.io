---
layout: post
title:  "Remapping Keyboard Keys"
date:   2016-05-02 10:00:00 +0530
tags: [remapping, keyboard, keyboard keys, XKB, Ubuntu]
comments: true
---
<br>
Recently, the spring beneath the Backspace key on my keyboard lost its tautness. I needed to press it hard to make it work. So, I decided to swap that key with the Insert key which is right above it.

## Windows
Doing this in Windows is pretty straightforward. Just download and use any of the programs like [Sharpkeys] or [KeyTweak]. I used Sharpkeys. It's easy and worked as advertised.

## Ubuntu
Now, let's get it done in Ubuntu.

The basic keyboard mapping package in Ubuntu is **XKB (X Keyboard Extension)**. This extension handles the mapping of the physical keys on your keyboard to their respective function.

XKB symbol files can be found in `/usr/share/X11/xkb/symbols/`.

Head on to `/usr/share/X11/xkb/symbols/pc`, a file where the modifer keys are mapped in.

In my case, I need to remap the `Backspace` and `Insert` keys. So, I just swap the functionality of these two keys.
After swapping, these two entries look like:

{% highlight shell %}
 key <BKSP> {        [  Insert	       ]	};

 key <INS> {	[ BackSpace, BackSpace  ]       };
{% endhighlight %}

That's it! In order to apply these new mappings, the XKB's cache from `/var/lib/xkb` must be cleared.

You can visit that directory and delete all the files. Or you can run the command below:
{% highlight shell %}
rm -rf /var/lib/xkb/*
{% endhighlight %}

Now just restart your system. After logging in, you should see your new keys working as you want them to.

[Sharpkeys]: https://sharpkeys.codeplex.com/
[KeyTweak]: http://keytweak.en.softonic.com/

