## Lab Exercise - Making our web pages responsive

The task in this lab session is to work in your groups to make a responsive website - that is one that adapts to different types of device and screen size to ensure the user experience is optimal.

**One person** should take the lead with coding, and the other(s) act as reviewers and editors, helping the lead coder create the code: suggesting solutions for implementation, watching for typos and minor errors, and providing feedback and evaluation. You will also be using Git for version control for the code on this exercise, and will share it to GitLab so that your entire group has access to the final code.

!> This week, the member of the team doing the coding will be the person who's name comes first when team names are sorted alphabetically. 

?> While working on your website, you should make a note of the things that work, the things that don’t work, what is easy to accomplish, and what has been tricky to do.


### Setting things up for this week

By now, you should already have added code from last week's lab exercise into your group's project repository on GitLab.

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
|- week2-csslayout/             <- This is the folder for last week's work
      - index.html              <- Here's where our layout from last week should be
     |- css/
        - style.css             <- Here's our .css from last week
```

We'll need a new folder in our project for this week's work. Make a new folder (either in the file explorer or on the command line using the `mkdir` command), and call it 'week3-responsive'. Inside that folder, create an `index.html`, a `css` folder, and inside the `css` folder a new file `style.css`. These are the base filed for this week's project. Our layout will then look like:



```
 index.html                     <- This is the base page for our project, it should link to each individual week
 readme.md
 .gitlab-ci.yml
|- week2-csslayout/             <- This is the folder for last week's work
      - index.html              <- Here's where our layout from last week should be
     |- css/
        - style.css             <- Here's our .css from last week
|- week3-responsive/            <- This is the folder for this week's work
      - index.html              <- Here's where our page for this week goes
     |- css/
        - style.css             <- Here's our .css for this week
```


We can edit our root (the very bottom level/folder) `index.html` to link to our new project. Last week it started off looking like this (although you may have changed it since then):

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
    <a href="week2-csslayout">Week 2 - CSS Layout</a>
</body>
</html>
```

Let's add a new link to this week's work: 

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
    </ol>
</body>
</html>
```

Save the root `index.html`. Then, on the command line, do:

```bash
git add index.html
git add week3-responsive
git commit -m 'week 3'
git push
```

This will send your changes up to GitLab.

?> The general idea is that anyone can visit http://cmt112.pages.cs.cf.ac.uk/TeamName/ and see a landing page that will include links to your solution for each week.

Periodically, when you reach a stage you are happy with while working on the lab activities, you should commit your code and `push` it to this repository. This will ensure that your whole group has access to the code after the lab exercise.

You should feel free as a group to edit the root `index.html` and `readme.md` files as you see fit - this is the information and the web page that other groups will see when visiting your project. 

?> Please remember to keep things professional - expressing some individuality and flair as a group is fine - being offensive is not! You should also remember that these pages are public, so please do not publish anything that you do not want to be personally connected with in future.

### This week's task

There are two options for this week's task:

1. Take the existing website that you have created in the previous week’s lab session. (NOTE: This should not be the coursework that you are currently working on individually!)
2. Create a new basic website from scratch. This can be on any topic, and does not need to be full of real content (lorem ipsum is fine).

Decide in your team where you would like to start from. Whichever you choose, ensure that the website you are working on has a realistic structure (multiple sections, paragraphs, navigation links, headers and footers etc). You can then either

1. Modify the existing website (if you are using one) to be responsive, and to work across multiple device sizes
OR:
2. Create the new website from scratch to be responsive

You should refer to the class notes and the tutorials and articles we discussed earlier to help you in the task. You should not focus on the content of the website, but work to ensure that your structure and navigation is functional and usable across many different resolutions.