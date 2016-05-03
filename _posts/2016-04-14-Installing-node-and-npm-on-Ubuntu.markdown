---
layout: post
title:  "Installing node and npm on Ubuntu"
date:   2016-04-14 10:00:00 +0530
comments: true
---

## Node.js
Node.js is an open-source, cross-platform runtime environment for developing server-side Web applications.

## npm
Node Package Manager(npm) is a package manager for Node.js with hundreds of thousands of packages. It's main goal is automated dependency and package management.

## nvm
Node version Manager(nvm) is used to manage multiple versions of node installations on same machine. You don't need it usually, so we are not looking at it now.

## Installing node and npm
There are several ways to install node and npm. The following installation method worked fine for me.

Type these commands in your terminal.

{% highlight shell linenos %}
echo 'export PATH=$HOME/local/bin:$PATH' >> ~/.bashrc
. ~/.bashrc
mkdir ~/local
mkdir ~/node-latest-install
cd ~/node-latest-install
curl http://nodejs.org/dist/node-latest.tar.gz | tar xz --strip-components=1
./configure --prefix=~/local
make install #this step takes some time
curl https://www.npmjs.org/install.sh | sh
{% endhighlight %}

The above method of installation is strongly inspired from this [gist](https://gist.github.com/isaacs/579814).

Now you have node and npm installed on your machine. You can check it by running the commands below.

{% highlight shell %}
node -v
{% endhighlight %}

{% highlight shell %}
npm -v
{% endhighlight %}

This will display the current version of node and npm installed.

That's it! Now you're all set to build some amazing stuff with node.

