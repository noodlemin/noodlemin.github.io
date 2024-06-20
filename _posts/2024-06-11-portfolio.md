---
layout: single
title: Portfolio Website
typora-root-url: ../
categories: Project
tags: Full_Stack, HTML, CSS, JavaScript
toc: true
---

# Summary

# Plan

- Responsive Website using HTML, CSS, and JavaScript.
- Features animations triggered upon scrolling.
- Offers smooth scrolling through each section.
- Includes both dark and light themes.
- Allows email sending directly from the contact section.
- Designed with a mobile-first approach, then optimized for desktop.
- Compatible with all mobile devices, providing a beautiful and user-friendly interface.

# Prerequisites

- Text Editor: VS Code
  - [Live Preview]( https://marketplace.visualstudio.com/items?itemName=ms-vscode.live-server): Useful extension to hosts a local server in your workspace for you to preview your webpages on.
- Web Hosting: [Netlify](https://www.netlify.com/)
  - Github (optional): You can import your repository to host your website + version control.
  - Github Pages can be useful.

# Implementation

## Header and Nevigation

- Create a dropdown menu with a transition duration of 0.4 seconds.

``` javascript 
// javascript
/* Menu show */
if(navToggle){
    navToggle.addEventListener('click', () =>{
        navMenu.classList.add('show-menu')
    })
}

/* Menu hidden */
if(navClose){
    navClose.addEventListener('click', () =>{
        navMenu.classList.remove('show-menu')
    })
}
```

```css
/* CSS */
/* Navigation for mobile devices */
@media screen and (max-width: 1150px){
  .nav__menu{
    ...
    transition: top .4s;
  }
}
```

## Home

- Animates a scroll icon by moving it up and down continuously with fading in and out effects over a 3-second loop.

``` css
.home__scroll-box i{
  animation: scroll-down 3s infinite;
}

/* Animate scroll icon */
@keyframes scroll-down{
  0%{
    transform: translateY(-1rem);
    opacity: 0;
  }
  50%{
    transform: translateY(0);
    opacity: 1;
  }
  100%{
    transform: translateY(.6rem);
    opacity: 0;
  }
}
```



# References

- [Responsive Personal Portfolio Website Using HTML CSS & JavaScript (youtube.com)](https://www.youtube.com/watch?v=-uQIBlaZ4P0&list=WL&index=26)
- [Remix Icon - Open source icon library](https://remixicon.com/): for icons

