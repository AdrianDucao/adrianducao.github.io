---
layout: post
title:  "Thoughts on React.js"
date:   2020-10-03 6:00:00 +0800
categories: coding
---

# For starters
React.js is a javascript library for building front-end UI and components, it's mainly used by front-end developers and full stack developers for static sites, web apps, and mobile apps. The competition is mainly Angular and Vue.js on web and mobile framework.

I tried using the react and experiment with it last early months of 2020 but I've decided to take a look at it last September of 2020 to better understand the framework, I did quite a lot of googling and watched youtube videos to understand the basics of the syntax, there's no easy way to learn a framework but to read the documentation and from there i understand that you are still using some HTML tags, using CSS to design stuff, and still using the normal JavaScript, so basically your generating a static HTML file with javascript.

```
public directory - contains the static HTML file and images or videos you want to use.
src directory - contains the source file, components, and pages of your static site.
```

# The Point 
Most developers will tell you that React.js offers reusable components, however with stock HTML5, CSS3, and JavaScript you can also create a reusable components. The thing is you're still designing some of that components with CSS, probably the point is to save time, you can argue that you can write all those by your self but if you are in a deadline, it's better to shave minutes or hours to meet that said deadline.

Performance, is one of the main reason developers use React, so how does it work? the way stock HTML, CSS, and JavaScript work goes something like this; you enter the website, the html, css and js stack loads, and if you go a different pages that said stack will reload everytime you go to different pages of that site. React.js works like this, you enter the site, the static file such as HTML, CSS, and JS is downloaded at once if not incrementally being downloaded to your browser, and whenever you go to a different page the only thing being refreshed or re-rendered is the content or the API. that's why React.js is a client side application.

# Cons 
The only Cons to these web framworks are the hyped up nature of it and the fact of FOMO(Fear Of Missing Out) this pushes developers to learn new framework because it is hot and hyped up, and may lead developers to Burn Out.

# Conclusion
Learning curve is a minor setback, you are living in 21st Century different information, tutorials, documentations and overall human knowledge is available on the internet, anything can be learned. React.js is a pretty good front-end framework, in order to complete a full stack project you have to use a different framework and runtime to finish the back-end you can use Node.js and Express.js web framework for your REST API, even better if you add GraphQL on the mix. This industry is changing month by month and it's up to you to catch up and learn.

Happy Coding.