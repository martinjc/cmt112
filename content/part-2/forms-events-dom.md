## Overview

In this section we'll start to look at using JavaScript to add interactivity to our pages. We'll look at getting user input, dynamically updating our HTML, and processing interaction events in JS.

### Compulsory Reading

- [Eloquent JavaScript - Chapter 14](http://eloquentjavascript.net/14_dom.html) - This chapter looks at selecting and modifying the Document Object Model (the HTML structure of our page) using JavaScript.
- [Eloquent JavaScript - Chapter 15](http://eloquentjavascript.net/15_event.html) - This chapter looks at how JavaScript deals with events (mouse clicks etc) on a page.
- [MDN - Introduction to the DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction) - A slightly technical look at the DOM API and what it is capable of.
- [MDN - Your first HTML Form](https://developer.mozilla.org/en-US/docs/Learn/HTML/Forms/Your_first_HTML_form) - Creating an HTML form.

### Videos

You should watch all these videos before the contact session in Week 6.

#### HTML Forms

<p><small>If the embed below does not work here is a <a href="https://cardiff.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=c0ea0d5d-f802-4601-8e62-a97600ffac1e" target="blank">link to the full version of the video</a></small></p>
<iframe src="https://cardiff.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=c0ea0d5d-f802-4601-8e62-a97600ffac1e&v=1" width="720" height="405" style="padding: 0px; border: 1px solid #464646;" frameborder="0" allowfullscreen allow="autoplay"></iframe>

#### JavaScript - Events

<p><small>If the embed below does not work here is a <a href="https://cardiff.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=87c65b1b-1e64-4cbb-b80f-a97600ffaab8" target="blank">link to the full version of the video</a></small></p>
<iframe src="https://cardiff.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=87c65b1b-1e64-4cbb-b80f-a97600ffaab8&v=1" width="720" height="405" style="padding: 0px; border: 1px solid #464646;" frameborder="0" allowfullscreen allow="autoplay"></iframe>

#### JavaScript - DOM

<p><small>If the embed below does not work here is a <a href="https://cardiff.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=bf484fad-09ac-4619-8cd6-a97600ffaa36" target="blank">link to the full version of the video</a></small></p>
<iframe src="https://cardiff.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=bf484fad-09ac-4619-8cd6-a97600ffaa36&v=1" width="720" height="405" style="padding: 0px; border: 1px solid #464646;" frameborder="0" allowfullscreen allow="autoplay"></iframe>

## Code Examples

There are some example pieces of code for this topic. The source code for each example can be viewed in the GitLab project '[cmt112-examples](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples)' and the end result can be seen on the [GitLab pages site for that project](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/).

- Dom Structure [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/2-3/dom) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/2-3/dom/)
- HTML Form Elements [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/2-3/forms) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/2-3/forms/)
- Selecting elements using JavaScript:
  - by Class [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/2-3/select-class) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/2-3/select-class/)
  - by ID [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/2-3/select-id) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/2-3/select-id/)
  - by Tag [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/2-3/select-tag) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/2-3/select-tag/)
  - by CSS Selector [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/2-3/select-css) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/2-3/select-css/)
- Using innerHTML
  - 1 [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/2-3/innerHTML/1) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/2-3/innerHTML/1/)
  - 2 [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/2-3/innerHTML/2) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/2-3/innerHTML/2/)
- Creating HTML [[Code]]() [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/2-3/create-html/)
- Modifying HTML using JavaScript:
  - Attributes [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/2-3/modify-attributes) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/2-3/modify-attributes/)
  - Style 1 [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/2-3/modify-style/1) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/2-3/modify-style/1)
  - Style 2 [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/2-3/modify-style/2) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/2-3/modify-style/2)
  - Class [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/2-3/modify-class) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/2-3/modify-class/)
- JavaScript Events
  - Click [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/2-3/events/click) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/2-3/events/click/)
  - MouseOver [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/2-3/events/mouseover) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/2-3/events/mouseover/)
  - MouseEnter and Mouseout [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/2-3/events/mouseenterout) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/2-3/events/mouseenterout/)
  - Parameters [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/2-3/events/params) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/2-3/events/params/)
  - Bubbling [[Code]](https://gitlab.cs.cf.ac.uk/scm2mjc/cmt112-examples/tree/master/2-3/events/bubbling) [[Demo]](http://scm2mjc.pages.cs.cf.ac.uk/cmt112-examples/2-3/events/bubbling/)
