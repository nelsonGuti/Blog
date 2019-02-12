---
title: "Build an Animated Hamburger Menu from Scratch"
date: "2019-01-12T10:40:32.169Z"
layout: post
draft: false
path: "/posts/build_a_hamburger_menu/"
category: "CSS"
tags:
  - "CSS"
  - "HTML"
  - "Responsive"
description: "Build a menu from scratch using Vanilla JS and CSS transitions "
---

In this article you will learn how to make an animated hamburger menu using CSS transitions and some vanilla Javascript. We will be building this:

<img src="menu.gif"
     alt="Menu Animation"
     style="width:100%" />

## The Setup

I've created a github repo where you can find the starter files, which is just a basic HTML structure with a CSS and JS files

### The MarkUp

The HTML for this one is very simple, consisting of one div which will be the hamburger menu button which will toggle the nav back and forth.

```html
<body>
  <div class="menu-button">
    <div class="menu-button-item"></div>
    <div class="menu-button-item"></div>
    <div class="menu-button-item"></div>
  </div>
  <nav class="menu-nav">
    <ul>
      <li class="menu-nav-item">Item 1</li>
      <li class="menu-nav-item">Item 2</li>
      <li class="menu-nav-item">Item 3</li>
    </ul>
  </nav>
  <script src="main.js"></script>
</body>
```

### Finally some CSS

We will start by creating the hamburger menu. Each div with the of class "menu-nav-item" will be what makes up our hamburger menu button. In order to create, we will give it the following styles:

```css
.menu-button-item {
  width: 100%;
  height: 4px;
  margin: 0 0 4px 0;
  background-color: var(--primary-color);
  border-radius: 2px;
}

.menu-button-item:nth-child(1) {
  margin-top: 5px;
}
```
