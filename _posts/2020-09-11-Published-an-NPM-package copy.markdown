---
layout: post
title:  "Published an NPM Package"
date:   2020-09-11 6:00:00 +0800
categories: coding
---

### Issue:
I've been trying to figure out on how to use sessionStorage in node.js, it's true that you should not use these on projects but there are some useful use case of these, so i decided to create one and published it as npm package for others to use if they need it.

### Solution:
installation:
```bash
    npm i sessionstorage-for-nodejs
```
usage:
```nodejs
    const sessionStorage = require('sessionstorage-for-node');
    
    sessionStorage.setItem('id', 'value');
    
    console.log('product: ', sessionStorage.getItem('foo'));
    
    sessionStorage.removeItem('id', 'value');

```

### Resources:
[Github Repo](https://github.com/AdrianDucao/sessionStorage-for-node)

[NPM Package](https://www.npmjs.com/package/sessionstorage-for-nodejs)

Happy Coding.