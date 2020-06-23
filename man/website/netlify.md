---
subtitle: Buid a Free Website on Neilify.com
hero_height: is-small
layout: page
hero_image: "/img/sitev1.0/homeen.jpg"
---

Another alternative, you can host website on https://www.netlify.com/ for free.

Finally you will get an website with costum domain name and https url, you have to buy an domain name,and point to your netlify website on your DNS manager settings.

#### Login to github.com

You have to sign in [github.com](https://github.com/) account, or go to [sign up](https://github.com/) one for free.

#### Template of website

Copy "bulma clean rheme" by click 'Fork'(on top right of the screen) https://github.com/chrisrhymes/bulma-clean-theme

#### Configure website

1. change neme of your website repository by 'Settings' --> 'Repository name' to yourusername.github.io -->  click 'Rename' button
2. set up _config.yml, by clicking the file under root location, 
	baseurl: ""
    url: "https://yourusername.github.io"
	google_analytics: UA-xxxxxxxxxxx
3. You can visit website by https://yourusername.github.io

#### login netlify.com

- step 1: login with github account by Login https://app.netlify.com/  click `Github` --> `New site from Git` --> `Github` --> `Select from specific repository` --> yourusername/yourusername.github.io --> `Build options, and deploy!`
- step 2: Before you click `Depoy site` button, 
		- add following line `gem 'github-pages'` below `source "https://rubygems.org"` on `Gemfile`
        - create a `.ruby-version` on rooot then fill `2.4.3`in it
        - refer to: https://www.netlify.com/blog/2017/05/11/migrating-your-jekyll-site-to-netlify/
- step 3: click `Depoy site` button
- step 4: after successful deploying site,you will have a site hosting on netlify.com, you can edit on github.com and publish the site on netlify.com.
