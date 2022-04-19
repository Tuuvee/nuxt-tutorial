---
title: My first Blog Post
description: Learning how to use @nuxt/content to create a blog
img: first-blog-post.jpg
alt: my first blog post image is based
author:
    name: Benjamin
    image: https://images.unsplash.com/.....
    bio: All about Benjamin
---


# My first blog post

Welcome to my first blog post using content module

## This is a heading

This is some more info edited while live editing the page

## This is another heading

This is some more info

## This is another another heading

This is some more info

<info-box>
<template #info-box>
   This is a vue component inside markdown using slots live editing is pretty cool
</template>
</info-box>

```js[nuxt.config.js]
export default {
  nuxt: "is the best"
}
```
```html[my-first-blog-post.md]
<p>code styling is easy</p>
```