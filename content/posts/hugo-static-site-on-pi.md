---
title: "Part 2 - Set-up a blog on your home raspberry-pi server."
date: 2020-05-21T23:03:27+05:30
draft: false

tags: [
    "raspberry-pi",
    "home server",
    "web hosting",
    "NGINX",
    "Dynamic IP",
    "DHCP IP",
    "no-ip",
    "hugo",
]
---

With Nginx server installed on pi and domain forwarder working, Our next task is to deploy our blog. I used a static site generator called [hugo](https://gohugo.io) for that. 

<!--more-->

This is a two part article, read [part-1 here](/posts/testpost/)

Installing Hugo on pi is straight forward, use following command:

```
    sudo apt-get install hugo
```

If you are using a different operating systems, you can use [Installation guide](https://gohugo.io/getting-started/installing) for detailed steps.


Once installed you can use command bellow to initialize your blog:

```
    hugo new site myblog
    cd myblog
    git init
```

Once your first site is setup, next step is to install a theme. I used a theme called [anubis](https://themes.gohugo.io/hugo-theme-anubis/), you can get full list of themes [here](https://themes.gohugo.io/). To install a theme:

```
    git submodule add https://github.com/mitrichius/hugo-theme-anubis.git themes/anubis

```

you can download theme archive manually and extract in themes folder of your site directory if you do not use git.

Once theme is downloaded, update theme name in config.toml file:
```
    theme = "anubis"
```

Based on theme support, you can also add following configurations in your config.toml.
```
    paginate = 10
    disqusShortname = "dummy"
    googleAnalytics = "UA-dummy-1"
```

You can also provide other configurations of your site in config.toml
```
    baseURL = "https://yourblogURL.com"
    languageCode = "en-us"
    title = "My first blog"

    author = "name"
    description = ""
    env = "production"
```

To create your first blog post use following command:
```
    hugo new posts/my-first-blog-post.md
```

This will create a file named "my-first-blog-post.md" in the  content/post folder of your site directory.
The Language supported in the post is Markdown and you can use [this tutorial](https://www.markdownguide.org/cheat-sheet/) to understand it.

Once the blog post is ready you can test your site using following command, this will start a test server and provide a link for testing the site.
```
    hugo server -D

```

When everything works, you can build static pages with following command:
```
    hugo -D 
```

Above command will create the static pages inside ./public/ directory of your site folder, copy it to NGNIX html directory for deployment:
```
    cp -rf ./public/ /var/www/html/
```

Now you can visit your blog URL and your blog should be up and running.

