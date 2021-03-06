+++
type="page"
title="Lab Exercise: Server-Side JavaScript"
weight=2
+++

We are now going to start having a look at using JavaScript on the server using [NodeJS](https://nodejs.org/en/). [Node](https://nodejs.org/en/about/) is basically a JavaScript engine (the [V8 engine](https://en.wikipedia.org/wiki/Chrome_V8)), but instead of running inside a web browser, it runs on the command line, and includes a lot of handy JavaScript modules for doing certain tasks (like reading and writing files, or running servers).

### Setting things up for this week

Inside a new directory for this week, run the following command:

```bash
npm init
```

This will ask you a number of questions to create a basic `package.json` file. You can accept the default answers for all the questions _except_ the question which asks you what the 'entry point' of the program will be. Here you should type the answer `server.js` - we are telling NPM that our program will be stored in a file called `server.js`, not `index.js` as it is expecting:

![NPM Init](img/full-npm-init.png)

This will create a `package.json` file which is a simple text file that contains metadata about our code. It is also used to install _dependencies_, but we'll worry about that later.

Now we have the `package.json` we can create our `server.js` file. Open a text editor, and enter the following code:

```js
// http module gives us simple server functionality
const http = require("http");

// define where our server will run
const server_port = 3000;
const server_ip = "127.0.0.1";

// create a server
const server = http.createServer(function(request, response) {
    response.statusCode = 200;
    response.setHeader("Content-Type", "text/plain");
    response.end("Hello World!");
});

// start the server listening
server.listen(server_port, server_ip, function() {
    console.log(`server running at http://${server_ip}:${server_port}/`);
});
```

This is all we need to create a basic web server in Node. On the command line, type:

```bash
node server.js
```

and you should see the output:

```
> node server.js
server running at http://127.0.0.1:3000/
```

Open a new web browser tab, and enter the address `http://127.0.0.1:3000/` and you will see the response from the server:

![Hello World](img/hello-world.png)

### Debugging

JavaScript running in Node is very similar to JavaScript running in the browser. We even have access to a `console` object, just like in the browser, and we've already used it to log some information, just like we do in the browser, except here, as we've seen, it gets printed to the command line where the server is running, instead of the console inside the browser.

"HANG ON!" I hear you cry. "You said that printing variables to the console to debug code was too simple, and that we should use the debugger instead! Now we're stuck on the command line, what gives?" Well, yes, you are right. And in fact - there is a way to debug our code using a proper debugger.

If we run our code using:

```bash
node --inspect-brk server.js
```

it will start in a debug mode, and pause once our code starts running. If you then open a Chrome tab to `chrome://inspect` and click the `Open dedicated DevTools for Node` link, you should be able to open a debugger that will connect to your Node application and allow you to use the same debugging process as when running JavaScript on a webpage

{{% panel theme="warning" header="Bugs ahead?" %}}
!> There is an important caveat - Chrome as of v69 [has a bug](https://github.com/ChromeDevTools/devtools-protocol/issues/103) that means breakpoints do not work properly if we just set them in the DevTools. However, there is a workaround. Node also has a handy `debugger` command we can use within our code to set a breakpoint. So, if we do this:

```js
const server = http.createServer(function(request, response) {
    debugger;
    response.statusCode = 200;
    response.setHeader("Content-Type", "text/plain");
    response.end("Hello World!");
});
```

The Debugger will pause our code at the first line of the function that sends a response to the server, so we can see the values of the request and response variables for ourselves:

![debugger](img/debugger.png)

In fact, once our code hits the first breakpoint from the `debugger` command, we can add more breakpoints that will work just fine.
{{% /panel %}}

### Request Objects

We've written a server that has a single function, that receives two arguments. The first is the `request` object - it represents the request that has been made to the server by the client, in this case the web browser. The second object is the `response` object - this is the object we use to send a response back to the client. Both the `request` and the `response` contain a lot of useful information that we can use within our code. For example, we can get access to the header information that was sent with our `request`, either by inspecting the request object in the debugger:

![Debugger Info](img/debugger-info.png)

or by printing the information we need to the command line:

```js
// create a server
const server = http.createServer(function(request, response) {
    debugger;
    console.log(request.headers);
    response.statusCode = 200;
    response.setHeader("Content-Type", "text/plain");
    response.end("Hello World!");
});
```

![Headers](img/headers.png)

This means that we can find out a lot of different information about the type of request and the client that made it inside our server code. Similarly, we can pass lots of information back to the client by editing the properties of the response object. In this example, we are sending back a `200` status code, a header that sets the content type of the information we are sending, and then the content itself.

Let's replace the headers with some more useful information that we'll print to the command line:

```js
// create a server
const server = http.createServer(function(request, response) {
    debugger;
    console.log(`received a ${request.method} request to url ${request.url}`);
    response.statusCode = 200;
    response.setHeader("Content-Type", "text/plain");
    response.end("Hello World!");
});
```

Which will give us an output like this:

![Method and URL](img/method-url.png)

### Different request !== different response

Our server currently sends back the text 'Hello World' no matter which URL we ask for. You can enter whatever you like in the address bar, and you get back the same response:

![whatever requests](img/requests.png)

![whatever](img/whatever.png)

If we can check the URL, we can send back a different response for each request. First we need to include the `url` module, which includes some hand functionality for taking a url and breaking it down into its constituent parts:

```js
const http = require("http");
const url = require("url");
```

Then we can change our server function so that it checks the path used and responds accordingly:

```js
const server = http.createServer(function(request, response) {
    console.log(`received a ${request.method} request to url ${request.url}`);

    const u = url.parse(request.url, true);

    response.statusCode = 200;
    response.setHeader("Content-Type", "text/plain");

    if (u.pathname === "/hello") {
        response.end("Hello World!");
    } else if (u.pathname === "/goodbye") {
        response.end("Goodbye!");
    } else {
        response.end("How can I help?");
    }
});
```

Now if we make a request to `/hello` we get our original functionality:

![Hello World](img/hello.png)

If we visit `/goodbye` we get a different response:

![Goodbye](img/goodbye.png)

and if we visit anything else:

![Whatever](img/whatever2.png)

### Sending back different data types

So far we've just sent back text data, as type `text/plain`. Lets change this so we send data back as JSON. JSON is a handy format for web based tasks, and we've already seen some in `package.json`.

First we'll add a new function to our server:

```js
const return_JSON = function(json_data, response) {
    response.statusCode = 200;
    response.setHeader("Content-Type", "application/json");
    response.end(JSON.stringify(json_data));
};
```

Then we'll use this function to return data in our response:

```js
// create a server
const server = http.createServer(function(request, response) {
    debugger;
    console.log(`received a ${request.method} request to url ${request.url}`);

    const u = url.parse(request.url, true);

    if (u.pathname === "/hello") {
        return_JSON("Hello World!", response);
    } else if (u.pathname === "/goodbye") {
        return_JSON("Goodbye!", response);
    } else {
        return_JSON("How can I help?", response);
    }
});
```

The result in the web browser doesn't look very different, but if we open the 'Network' tab in the developer tools, we can see the data has definitely been returned as `application/json` rather than `text/plain`.

![Return JSON data](img/json-response.png)

Now lets add a little more functionality to our server. First, we're going to install a module called `[moment](https://momentjs.com/)`. Moment is a handy JavaScript library for dealing with times and dates, and we're going to use it so that our server can tell us what time it is.

```
npm install moment --save
```

NPM will download and install the moment library in our node_modules folder, and will save it to our package.json. Saving a library as a dependency in this way means that when we share our code with someone they can use the package.json file and npm to make sure they have all the requirements installed that are needed for the code to run.

!> You did remember to add node_modules to your .gitignore file, didn't you?

You can create a `.gitignore` file that will stop `node_modules` being added to your Git repository with the following command:

```bash
echo 'node_modules' > .gitignore
```

Now that moment is installed, we can require it:

```js
const http = require("http");
const url = require("url");
const moment = require("moment");
```

And then use it in our server:

```js
if (u.pathname === "/hello") {
    return_JSON("Hello World!", response);
} else if (u.pathname === "/goodbye") {
    return_JSON("Goodbye!", response);
} else if (u.pathname === "/time") {
    var now = new moment().utc();
    var data = {
        now: now,
        year: now.year(),
        month: now.month(),
        day: now.day(),
        hour: now.hour(),
        minute: now.minute()
    };
    return_JSON(data, response);
} else {
    return_JSON("How can I help?", response);
}
```

Now when we make a request to `http://127.0.0.1:3000/time` we get told the current time, and the data is returned to us in JSON format.

Next week, we'll go on to look at how we could make this request using JavaScript, and how we could use the data that is returned to us in the response.

### Going further

-   Can you add more functionality to the server? Look at the `fs` module in Node. Could you add some functionality that allows the server to read and return a local file?

### Further Reading

For more information on what we're doing here, and another look at setting up a web server using Node, read the [Anatomy of an HTTP Transaction](https://nodejs.org/en/docs/guides/anatomy-of-an-http-transaction/) doc at the NodeJS website.
