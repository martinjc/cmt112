## Overview

In this section we look at REST APIs, what they are, and how to request data from them in our front-end websites. We'll look at a _relatively_ simple way to request data from an API - but be warned that we'll also look at a newer method next week.

### Compulsory Reading

- [A Beginners Guide to HTTP and REST](https://code.tutsplus.com/tutorials/a-beginners-guide-to-http-and-rest--net-16340) - An introduction to some of the technologies that allow us to build and use Web APIs.
- [Eloquent JavaScript - HTTP and Forms](http://eloquentjavascript.net/18_http.html) - Another look at HTTP, and a bit of revision on HTML Forms
- [MDN - Getting Started with AJAX](https://developer.mozilla.org/en-US/docs/Web/Guide/AJAX/Getting_Started) - A look at dynamically updating pages with information retrieved from a server.

### Videos

You should watch all these videos before the contact session in Week 8.

#### APIs & JavaScript

<p><small>If the embed below does not work here is a <a href="https://cardiff.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=9be52154-c476-48dc-8072-a5adadfac582" target="blank">link to the full version of the video</a></small></p>
<iframe src="https://cardiff.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=9be52154-c476-48dc-8072-a5adadfac582&v=1" width="720" height="405" style="padding: 0px; border: 1px solid #464646;" frameborder="0" allowfullscreen allow="autoplay"></iframe>

## Code Examples

There are some example pieces of code for this topic. The source code for each example can be viewed in the GitLab project '[cmt112-examples](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples)' and the end result can be seen on the [GitLab pages site for that project](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/).

### Sunrise-Sunset

These examples use the [Sunrise-Sunset API](https://sunrise-sunset.org/api), a simple API which accepts Latitude and Longitude coordinates as input and returns details on the time of sunrise and sunset at that location.

- XMLHttpRequest - Event Listener [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/3-2/sunrise-sunset/xhr-listener) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/3-2/sunrise-sunset/xhr-listener)
- XMLHttpRequest OnReadyStateChange [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/3-2/sunrise-sunset/xhr-onreadystate) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/3-2/sunrise-sunset/xhr-onreadystate)
- Fetch [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/3-2/sunrise-sunset/fetch) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/3-2/sunrise-sunset/fetch)

### Spotify

These examples use the Spotify API. They are more complicated, as login is required to access data

- Login - An example showing logging in to an API using OAuth< [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/3-2/spotify/login) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/3-2/spotify/login/login.html)
- Recently Played - An example showing logging in to an API using OAuth and retrieving some data [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/3-2/spotify/recently-played) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/3-2/spotify/recently-played/login.html)
- POST - An example showing logging in to an API using OAuth and then POSTing some data to the API [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/3-2/spotify/post) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/3-2/spotify/post/login.html)