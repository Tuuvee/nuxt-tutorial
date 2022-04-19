---
title: My second Blog Post
description: Learning how to use @nuxt/content to create a blog
img: second-blog-post.jpg
alt: my second blog post image is based
author:
    name: John
    image: https://images.unsplash.com/.....
    bio: All about John
---


# My second blog post

Welcome to my second blog post using content module

## This is a heading

This is some more info

## This is another heading

This is some more info

## This is another another heading

This is some more info

<info-box>
<template #info-box>
   This is a vue component inside markdown using slots
</template>
</info-box>

```js[nuxt.config.js]
export default {
  nuxt: "is the best"
}
```
```html[my-second-blog-post.md]
<p>code styling is easy</p>
```