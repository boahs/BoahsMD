---
title: "First log jitters..."
path: "/First_log"
date: "2020-06-16"
coverImage: "../images/Gatsby_Logo.png"
author: "Boahs"
excerpt: '"The third overhaul for my website has been deployed!"'
tags: ["js", "gatsby", "react", "cli"]
---
## First log

The third overhaul for my website has been deployed! Behold the creation.

After long consideration of wanting to completely overhaul my personal portfolio website I decided to finally take a plunge into the gorge, and I'm very satisfied with what I've accomplished with this new design! 

The first iteration of [my website](https://boahs.info/) consisted of as a simple SPA that used some fancy CSS, and your basic HTML. I had it set up to present four of my latest projects, and a little bio/about me. 

Taking things to the next level with the second iteration I decided to use [gatsbyJS](https://www.gatsbyjs.org/) for the generation and [graphQL](https://graphql.org/) as my database. Gatsby has a lot going on for it - it's a little more complicated to use than your basic static site generators such as [HUGO](https://gohugo.io/), and [Bootstrap](https://getbootstrap.com/) but once you start to understand the gatsby CLI things start rolling quite quickly.

Gatsby takes markdown files, and generates HTML files when the user loads your content resulting in very fast load times, and great SEO overall. To get started with gatsby just install the cli

``` 
npm install -g gatsby-cli

```

Create your new site 

```
gatsby new gatsby-site
```

Change directories into site folder
```
cd gatsby-site
```

Start development server
```
gatsby develop
```

At this point Gatsby will start a hot-reloading development environment that is accessible by default at http://localhost:8000 

### Cool right?

The third, and final(so far) iteration is what you're looking at now. This'll be the first time I've actually bothered to write logs but I've been yearning for a while now to start posting, and conceptualizing the new things I learn somewhere, and I guess what better place would be my own little area? You might see 5-6 random problems I've solved on [codewars](https://www.codewars.com/users/boahs), or an article on React. It'll just depend on what I'm doing that given day!

Now we'll go over some of the more interesting things I've integrated into the website. 

- A dark/light mode 
- Awesome reading experience thanks to [Inter UI font](https://rsms.me/inter/)
- NICE code highlighting thanks to [PrismJS](https://prismjs.com/)
- Responsive youtube/vimeo etc. videos utilizing  [gatsby-remark-embed-video](https://github.com/borgfriend/gatsby-remark-embed-video)

<b><i>Hopefully this will be the last version of https://boahs.info/ we'll see how much I enjoy blogging :-) </i></b>

**— Boahs**
