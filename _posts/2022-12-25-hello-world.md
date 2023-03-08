---
title: "Github Pages and Jekyll"
classes: wide
---

I have created my personal webpage using **Github Actions** and **Github Pages**. Github allows its users to publish their webpages for free using the **Github Pages** feature.

**Github Pages** simply serves the contents of a repository branch as a webpage, hence assuming there is an `index.html` file that serves as an entrypoint.

Since I am not a web developer myself I have decided to use **Jekyll**, which is a tool that processes **Markdown** files into **HTML**. I have used the following repository as reference in order to build a webpage using Jekyll:

[Minimal mistakes pages starter](https://github.com/mmistakes/mm-github-pages-starter)

As I do not want to install and run Jekyll locally I have defined a **Github Workflow**, which is the equivalent of a pipeline in Github, to run **Jekyll** command line for me and deploy the resulting **HTML** code in the `gh-pages` branch of my repository every time there is a new commit in the `main` branch. To do this I have followed this guide:

[Jekyll actions](https://github.com/marketplace/actions/jekyll-actions)

This allows me to publish a my own webpage in the internet, for free, and without installing any web development related software in my computer.