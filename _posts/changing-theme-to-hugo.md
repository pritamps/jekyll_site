---
layout: post
title:  "Hello"
---

## What is the purpose of the Homescreen

* Give people a chance to EXPLORE the site
* Make it attractive
* Make it fast
[^]
##  Links I used while changing my website theme

How to make an image full-width in CSS grid: https://css-tricks.com/full-width-containers-limited-width-parents/

Basic CSS grid: https://developers.google.com/web/updates/2017/01/css-grid

Image properties:

.img-full-width seems to be the class all images share, so we just display that in centre.

Gutenberg adds .alignfull for the full full-width images. 

Wordpress sets width and height for all images. They have to be removed so that we can set them in CSS. An alternative is setting !important in CSS, but then it's a lot of trouble overriding it in CSS.
```css
.img-full-width {
  max-width: 100%;
  max-height: 80vh;
  display: block;
  margin: 0 auto;
}

.alignfull {
  width: 100vw;
  position: relative;
  left: 50%;
  right: 50%;
  margin-left: -50vw;
  margin-right: -50vw; 
}

.alignfull .img-full-width {
  max-width: initial;
  max-height: 150vh;
  width: 100vw;
  height: auto;
}
```
  
  * To put image title inside image:
```
.post_thumbnail_image {
    width: 100%;
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    height: 100%;
}

.post_thumbnail_title {
    margin-left: auto;
    margin-right: auto;
    width: 100%;
    bottom: 0;
    position: absolute;
    text-align: center;
    color: white;
}
```

Needed to replace all WP-set fixed values for width and height in the images:
* Regex to find all width and height tags: `(width|height)="\d*"`
* Need to remove all custom set width and height including "style: width etc": `style="width: \d*px"``

## Naming Conventions

* `post-*` - Something in the post. For example `post-title`


## Responsive design

* Reasonably easy with CSS grid
* Media queries used by Bootstrap: https://stackoverflow.com/questions/19592968/bootstrap-3-breakpoints-and-media-queries
* Look at how images resize in this blog: http://simplebits.com/books/2015/02/25/2e.html

## Images

* All images can be a lightbox: https://codepen.io/gschier/pen/HCoqh (Meh)
* See shortcodes for how to add classes to figures etc.

## Javascript

* I want to be very strict about the JS I add
* Do lazy loading LATER

## References

[1]: https://gridbyexample.com/
Grid By example[1] is a great website by one of the main developers of CSS Grid.