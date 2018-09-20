## Lab Exercise - CSS Layout + GitLab Pages

The task in this lab session is to work in your groups to produce a website with a fairly complex layout. In your group you should look at a website you visit often, and attempt to recreate that website layout using the HTML and CSS we have looked at to date.

One person should take the lead with coding, and the other(s) act as reviewers and editors, helping the lead coder create the code: suggesting solutions for implementation, watching for typos and minor errors, and providing feedback and evaluation. You will also be using Git for version control for the code on this exercise, and will share it to GitLab so that your entire group has access to the code (see below).

?> While working on your website, you should make a note of the things that work, the things that don’t work, what is easy to accomplish, and what has been tricky to do.


### Resources

While working on your website you may find the following resources useful:

* http://www.lipsum.com/ - allows you to generate filler ‘Lorem Ipsum’ text to use to pad out your website content while working on layout and design.

* http://lorempixel.com/ - allows you to generate placeholder images to use on your website while working on layout and design.




### Deploying to GitLab pages

Your group will have been set up with a project in the `cmt112` group on GitLab. Within this project's repository you will find a folder for this weeks lab activity - `week2-csslayout`. You should start the week's activity by cloning this repository to the lab machine you will be working on. Periodically, when you reach a stage you are happy with, you should commit your code and `push` it to this repository. This will ensure that your whole group has access to the code after the lab exercise.

Using GitLab also has another benefit - it can be used to host web pages as part of a project. In order to host our pages on the GitLab server, we need to tell GitLab to use the Continuous Integration/Continuous Deployment (CI/CD) function to deploy our project to the public GitLab pages server.

We do this by including a '.gitlab-ci.yml' file in the Project. This has already been included in the repository for this week. It looks like this:

```yaml
image: alpine:latest

pages:
  stage: deploy
  script:
  - mkdir .public
  - cp -r * .public
  - mv .public public
  artifacts:
    paths:
    - public
  only:
  - master
```

You don't need to worry about the details, but this file essentially sets up a task that GitLab will run every time you push new code to the GitLab server. This task will copy the code in the repository to the public GitLab pages server. Your page will then be visible at WEB_ADDRESS_HERE


### Completing the exercise

You may not have time to complete the exercise during the session. You should ensure that you work as a group to complete the activity by the end of the week. 

!>The next part of this exercise will involve your code solution being reviewed by another group(s), so you need to make sure the final code is available on GitLab for them to review!