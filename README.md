Subscribe Button
================

[Subtome](http://www.subtome.com/) is a **universal subscribe button**.
It decouples the content to which a user can susbcribe from the application this user may want to use to perform the subscription.
It's losely inspired by [WebIntents](http://webintents.org/).

<a class="minibutton" href="web+subscribe://">Try it</a>.

The spec is the code, and the code is open source. Feel free to contribute to it. You could very well run your own instance, but that means users may have to reselect his favorite subscription tool over and over again.

By design, all state is kept in the user's browser.

This is intented at running as a bookmarklet and/or an embedded button.

# Workflow.

1. A user visits a site that is able to povide some kind of subscription mechanism. That site will then embed in its page some JS that will register this application on behalf of the user.

2. The subscription button script will store in the user's session the fact that he can use the previously described app for subscriptions.

3. Later, when on another site, the user wants to follow a given resource and clicks on the bookmarklet.

4. The user is then showed the list of service that may be able to handle his subscription.

5. Once the user picks a service, he's sent to that service to complete the subscription.

Build
=====

Install dependencies (you need to have node.js installed):

<code>$ npm install</code>

Compiling the code:

<pre><code>$ browserify src/settings.js -o build/settings.subtome.js
$ browserify src/register.js -o build/register.subtome.js
$ browserify src/subscribe.js -o build/subscribe.subtome.js
</code></pre>

Todo
====

* Wordpress Plugin (button)
* Integrate into more readers
* Create a better icon

Going Further
=============

We intentionaly pushed the complexity down to the subscribing application, which should be smart enough to handle subscriptions if it has registered as such.

The subscribing application is in charge of extracting the data to which the user can subscribe (RSS or Atom feed, Social network handle, ... etc), from the page URL.

