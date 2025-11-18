---
title: "My Website and Where It's Hosted"
date: 2024-06-15
draft: false
description: "My Website and Where It's Hosted"
---

#### This is my personal website where I write whatever crosses my mind and keep you updated on some of my projects.

#### I've written and rewritten this site several times and I think I've finally arrived at a solution that suits **my** needs, so now let me explain what I did. As a framework I'm using [Hugo](https://gohugo.io/), an open-source static site generator with the [Blowfish](https://blowfish.page/) theme. This allows me to organize the site content simply and write posts in Markdown format. Hugo takes care of converting them to html files and generating everything needed to make the site work. At first you have to struggle a bit with the configuration, but when you're done you'll see that everything will run smooth as silk. The result of deploying with Blowfish is a *public* folder to insert within your web server (for example Apache). However, this has the *small* inconvenience of forcing you to redeploy and update the web server every time you publish a post. Too slow and cumbersome for my taste.

#### So I decided to use [GitHub Pages](https://pages.github.com/) for deployment and hosting. Basically I created a repository (you can find it [here](https://github.com/CommanderKen/commanderken.github.io)) on GitHub with the site source. The repository **must** be named *your-username.github.io* (obviously you need to replace your-username with your GitHub username). On the repository page go to settings -> pages and select *GitHub Actions* under *Build and deployment* (see image).

![GitHub Pages](IMG_git_01.png)

#### Now it's necessary to modify the static.yml file that handles the deployment process. You can find the file on [my repository](https://github.com/CommanderKen/commanderken.github.io) or try to understand how it works by reading the [GitHub](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages) and [Blowfish](https://blowfish.page/docs/hosting-deployment/#github-pages) guides. Now, if you've configured everything correctly, every time you do a *git push* to the main branch the deployment should start automatically and you should see your site online at your-username.github.io.

#### Now comes the *fun* part, which is using a [custom domain](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages). This allows you to use your domain that you will have previously purchased somewhere (I bought mine on [Aruba](https://www.aruba.it)). As you can see in the image, you'll need to enter the domain name under *Custom domain* and press *Save*. You need to go to the DNS management page of the provider from whom you purchased the domain and enter in the A Records the addresses you find [here](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#about-custom-domain-configuration). **Attention!** There must be no other A Records, if there are you must delete them. Finally it's necessary to add a CName Record with host name www and cname your-username.github.io. Now you need to be *very patient*: you have to wait for the DNS records to propagate (it can take several hours), so go take a long walk. *Theoretically* everything should be ok now. If it doesn't work after a few hours you can try removing and re-entering your domain in the GitHub Pages Custom domain. To enable HTTPS you need to click the *Enforce HTTPS* checkbox. Again, this may take some time, so be patient.

#### If you have any problems feel free to write to me at my email address me@andrealucchini.com  
