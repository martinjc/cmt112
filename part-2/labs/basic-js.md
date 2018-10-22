## Lab Exercise - Basic JavaScript & Debugging

We are now going to start to use JavaScript, and learn how to use the built-in tools in our browser to monitor how our code executes and debug problems.

!> You will need to use Google Chrome for the coding exercises in this week's lab sheet.

**One person** should take the lead with coding, and the other(s) act as reviewers and editors, helping the lead coder create the code: suggesting solutions for implementation, watching for typos and minor errors, and providing feedback and evaluation. You will also be using Git for version control for the code on this exercise, and will share it to GitLab so that your entire group has access to the final code.

!> This week, the member of the team doing the coding will be the person who's name comes last when team names are sorted alphabetically.

### Setting things up for this week

By now, you should already have added code from last week's lab exercise looking at responsive design into your group's project repository on GitLab.

We'll start by cloning our existing repository to the lab machine you will be working on, if you haven't already.

!> Only the person who is coding needs to do this

```bash
git clone git@gitlab.cs.cf.ac.uk:cmt112/<GROUPNAME>.git
```

We have the following layout for code in our project:

```
 index.html                     <- This is the base page for our project, it should link to each individual week
 readme.md
 .gitlab-ci.yml
|- week2-csslayout/             <- This is the folder for week 2
      - index.html
     |- css/
        - style.cssk
|- week3-responsive/            <- This is the folder for week 3
      - index.html
     |- css/
        - style.css
```

We'll need a new folder in our project for this week's work. Make a new folder (either in the file explorer or on the command line using the `mkdir` command), and call it 'week4-javascript'. Inside that folder, create an `index.html`. This is the base file for this week's project. Our layout will then look like:

```
 index.html                     <- This is the base page for our project, it should link to each individual week
 readme.md
 .gitlab-ci.yml
|- week2-csslayout/
      - index.html
     |- css/
        - style.css
|- week3-responsive/
      - index.html
     |- css/
        - style.css
|- week4-javascript/            <- This is the folder for this week's work
      - index.html
```

We can edit our root (the very bottom level/folder) `index.html` to link to our new project. Let's add a new link to this week's work:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title></title>
</head>
<body>
    <h1>Our Work</h1>
    <ol>
        <li><a href="week2-csslayout">Week 2 - CSS Layout</a></li>
        <li><a href="week3-responsive">Week 3 - Responsive</a></li>
        <li><a href="week4-javascript">Week 4 - JavaScript</a></li>
    </ol>
</body>
</html>
```

Save the root `index.html`. Then, on the command line, do:

```bash
git add index.html
git add week4-javascript
git commit -m 'week 4'
git push
```

This will send your changes up to GitLab.

Periodically, when you reach a stage you are happy with while working on the lab activities, you should commit your code and `push` it to this repository. This will ensure that your whole group has access to the code after the lab exercise.

### JavaScript Debugging

Open your `index.html` for this week in a text editor, and at the same time, open it in Google Chrome.

!> You will also need the `Developer Tools` window open in Chrome

In the text editor, enter the following code for your index.html page:

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript</title>
</head>

<body>
    <script>
        let x = prompt("I will add two numbers. What is the first number?");
        let y = prompt("What is the second number?");
        let z = x + y;
        alert("The answer is: " + z);
    </script>
</body>

</html>
```

Reload the page, and enter a number in the prompt box when requested. Pay attention to the answer in the alert box. Is it what you expected?

Lets use the debugger to see what's going on and try to figure out why we are getting the wrong answer. In the Developer Tools window in Google Chrome, click on the 'Sources' tab. in the left-hand pane you can see all the files that make up your webpage - in this case 'index.html'. This may already be selected, but if not select this file, and the source code will appear in the middle pane.

![Developer Tools and the Debugger](img/browser-debugger.png)

In order to see what is going on, we need to set a 'breakpoint'. A breakpoint allows us to pause our code at a particular point, or during a particular event. We can then have a look at the internal **state** of our program to see what is going on. This allows us to find and fix errors in our code. We'll set a breakpoint on the first line of code, line 13. Click on the '13' in the code shown in the Developer Tools, and it will be highlighted with a blue arrow:

![Setting a breakpoint](img/browser-debugger-breakpoint.png)

We have now set a breakpoint - we have told our browser to pause our JavaScript code at this point so that we can examine it. Reload your page, and the browser will pause when it gets to this line of JavaScript:

![Setting a breakpoint](img/browser-debugger-breakpoint-paused.png)

We can now control how our browser executes our code, and **step through** the code line by line, or function by function. The debugger has a set of buttons that allow us to do this:

![Setting a breakpoint](img/debugger-controls.png)

- ![Setting a breakpoint](img/play.png) The first blue 'play' icon () allows us to resume our code. Our code will continue to run, until we hit another breakpoint or reach the end of the script.
- ![Setting a breakpoint](img/functions.png) The next three buttons (the curved arrow, the down arrow and the up arrow ) allow us to step over, in to and out of functions. We'll use these more as we start to look at functions in the coming weeks.
- ![Setting a breakpoint](img/step-line.png) The last button, the arrow pointing to the right, is the control to step through our code one line at a time. This is the button we need to use right now.

Press the Step button once, and our first line of code will execute, and we'll see our prompt:

![Setting a breakpoint](img/browser-prompt.png)

Enter the number 45 in the prompt, press OK, and we'll see the debugger updates our _state_ and moves on to the next line of code:

![Setting a breakpoint](img/browser-post-prompt.png)

You can see that Line 14 of the code is now highlighted as the next line to be executed. The debugging pane on the right hand side of the window has also updated. In the 'Scope' section, you can see that we now have a local variable named `x` with a value of `"45"`. Press the step button again, and we'll run the next line of code. Again, a prompt will be shown. Enter 78 in this prompt, and click 'OK'. Our debugger state will be updated again:

![Setting a breakpoint](img/post-two-prompts.png)

Our 'Scope' section now has two local variables, `x` with a value of `"45"` and `y` with a value of `"78"`. Click the step button again. and our next line of code will be run, adding `x` and `y` together, and storing the result in the variable `z`.
