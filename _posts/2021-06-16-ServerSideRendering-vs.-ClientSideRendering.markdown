---
layout: post
title:  "Server Side Rendering vs. Client Side Rendering"
date:   2021-06-16 6:00:00 +0800
categories: blog
---
> Updated 06/17/2021

# Which is better?
When it comes with new technology and and fad of web development overall is flawed some promoting this and that but most of the recommendation found in some cases are not that great, explanation barely understood and just like this post it's TLDR for some... This is a closer look to the concept, frameworks, and use cases for someone who stared learning with React.js and Node.js on January 2020 and after a year of learning, research, development and deployment here's some useful insight.

## Server Side Rendering
What is it? this is the traditional way of running things for websites, basically the server will provide readily available files like [HTML](https://www.w3schools.com/html/default.asp) and [CSS](https://www.w3schools.com/css/) and static files like images will be served and browser will render said files but is not interactive then browser downloads [JavaScript](https://www.w3schools.com/js/) then browser executes it to make it interactive... this applies to most websites or landing pages mainly showing some information of a business or personal blogs with no real purpose or data... and in order to see changes on the site the website needs to be refreshed for a new request to be initiated. 
#### Dynamic Server Side Rendering
Web Applications or Web App are DSSR and it's like SSR but with data, basically the client send request to the server server renders and respond with the static files but the difference is DSSR contains data from a database. Aside from static files this is stacked with [PHP](https://www.php.net/) and databases like [MySQL](https://www.mysql.com/) or [mongoDB](https://www.mongodb.com/).

## Client Side Rendering
The concept of client side rendering is not new, but is mainly popularized with the use of front-end frameworks such as [React.js](https://reactjs.org/) released on 2013 the concept of redefining web development and deviding it into 2 parts front-end developement for the overall face or aesthetic and back-end developement of functionality, this concept lessens the burden of developers so they can just specialised in one thing and not to worry about the next, this provides some innovation and breath of fresh air on designs. Development with client side rendering concept comes with a framework or library and if you have any background of javascript that would come in handy but React has it's own syntax so checkout the [Docu](https://reactjs.org/docs/getting-started.html). I also wrote a post about [React.js](https://adrianducao.github.io/coding/2020/10/02/Thoughts-on-React.js-copy.html)

### Microservices
Another concept that would come in mind if you devide the front-end to the back-end is microservices, what is microservices? from the name itself it is a way to distribute or spreading the work load of a web app, basically you can use a robust websever and high performance load balancer like [NGINX](https://www.nginx.com/) and is mainly used as a reverse proxy. This way you could put mongoDB on a [Docker](https://www.docker.com/) container and run as it is seperated from Node.js back-end server to provide API and is also seperated from front-end. Microservices also comes in handy for big Projects like serving hundreds and thousands or millions of users with the only bottleneck is the clients internet speed, good example is [Netflix's Microservices](https://www.youtube.com/watch?v=CZ3wIuvmHeM). a thing to remember and take note is that overdoing things will comes with a price of undocumented shit, so bare in mind that there are some use cases of microservices especially for big projects that handles a lot of work load but if you only run a blog site with no forums or any services whatsover please don't use this concept...

## Stacks: Things i've used before
what are the common stack that you see in SSR?
* HTML
* CSS/Bootstrap
* JavaScript
* and a Web server like [Apache](https://www.apache.org/)
* MENN Stack(MongoDB Express [Next.js](https://nextjs.org/docs/getting-started) Node.js)

what about for DSSR?
* same thing but with PHP and Databases like MySQL or PostgreSQL
* and Servers like Apache, [WAMPP](https://www.wampserver.com/en/), [XAMPP](https://www.apachefriends.org/index.html), or [Laragon](https://laragon.org/)
* MENN Stack or (MEAN Stack but i haven't used this... A is [Angular](https://angular.io/docs))

what about stacks for CSR?
* [React.js](https://reactjs.org/) Framework
* [Node.js](https://nodejs.org/en/) and will use [Express.js](https://expressjs.com/) Framwork
* [NGINX](https://www.nginx.com/) for the server and reverse proxy
* [MongoDB](https://www.mongodb.com/)
they usually call this MERN Stack (Mongo Express Reat Node) but you could also use MySQL or PostgreSQL on this so call it PERN Stack :-)

with Microservices
* [Docker](https://docs.docker.com/)
i mainly use docker since i haven't got the time to read the [Kubernetes](https://kubernetes.io/) Documentation but they say that it's much easier to pair docker with kubernetes since you can use kubernetes to manage docker containers afterwards

# Conclusion 
So after using this client side rendering concepts and stacks for about a year, i found out that:
### best use cases for SSR and DSSR
* Landing page or websites that doesn't require any data input and outputs
* Blogs and Forums                                                                                                
* Web Apps that requires good compatibility with SEO
* Load Time 

### best use cases for CSR
* Web Apps that doesn't care about SEO, good examples are web apps used on business end
* Load Time (Client will have bad experience if slow internet connection is involved)
* No full page reload, as the only thing that needs to load is the API's data


Happy Coding.
