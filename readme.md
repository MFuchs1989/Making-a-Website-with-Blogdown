
# Making a Website with Blogdown

<p align="center">
  <img src="https://github.com/MFuchs1989/Making-a-Website-with-Blogdown/blob/master/images/Blogdown.png?raw=true" alt="python"/>
</p>



The goal is to create your own homepage with the help of Blogdown.


## Table of Contents
1. [Introduction](#introduction)
2. [Requirements](#requirements)
3. [Getting Started](#getting_started)  
4. [Homepage Design](#homepage_design) 
5. [Add Google Analytics](#add_google_analytics)
6. [Authors](#authors)
7. [Project Motivation](#motivation)



<a name="introduction"></a>

## Introduction

I am passionate about blogging, but wanted to avoid public sites like [WordPress](https://wordpress.com/de/) or [Medium](https://medium.com/).  
So I thought of another way and found out that you can create your own homepages with the help of [Blogdown](https://bookdown.org/yihui/blogdown/) and [Netlify](https://www.netlify.com/). 

I really recommend watching the following YouTube video by [John Muschelli](https://www.youtube.com/channel/UCWI1xyk6Jb4t2OOyP2LS4DQ), where he demonstrates the same procedure live. 
Just click on the image to play the video. 

[![YouTube](https://github.com/MFuchs1989/Making-a-Website-with-Blogdown/blob/master/images/YouTube.png)](https://www.youtube.com/watch?v=syWAKaj-4ck&t=1s)





<a name="requirements"></a>

## Requirements

+ Account on [GitHub](https://github.com/)
+ [R](https://www.r-project.org/) and [R-Studio](https://de.wikipedia.org/wiki/RStudio)
    + [Install Blogdown](https://bookdown.org/yihui/blogdown/installation.html)
    + [Install Hugo](https://bookdown.org/yihui/blogdown/hugo.html)

**Additional notes:**

You may not be using the latest version of Hugo. You can load a specific older one with the following syntax: 

```
blogdown::install_hugo(
  version = "0.80",
  extended = TRUE,
  arch = "auto",
  os = "auto",
  force = FALSE)

blogdown::hugo_version()
```
With the following syntax you can check which libraries are already installed:
```
installed.packages()
```

With this you can find out the path where the installed libraries are located:
```
.libPaths()
```

<a name="getting_started"></a>

## Getting Started

1. Sign in to your GitHub Account and [create a new Repository](https://docs.github.com/en/github/getting-started-with-github/create-a-repo)
2. [Create a new project in R-Studio](https://support.rstudio.com/hc/en-us/articles/200526207-Using-Projects)
3. Run `new_site()` within the Console of R-Studio
4. If necessary, add a folder 'public' in the created directory from step 2
5. Push everything to GitHub
6. Log in to [Netlify](https://www.netlify.com/) with your GitHub account
7. Choose your Repository you want to deploy
8. Add 'public' to Publish directory
9. Go back to R-Studio (make sure you are connected to the appropriate project) and create a new post via Addins


That's it. 





<a name="homepage_design"></a>

## Homepage Design



Of course you still have a lot of possibilities to design your homepage. 
For example, you can use the [toml. File](https://bookdown.org/yihui/blogdown/configuration.html) further complement / redesign. 
Yihui Xie the inventor of Blogdown gives [here](https://bookdown.org/yihui/blogdown/) quite good tips what you can do. 


Gladly I put you also [my toml. File](https://github.com/MFuchs1989/Datasets-and-Miscellaneous/blob/main/miscellaneous/Making%20a%20Website%20with%20Blogdown/config.toml) at your disposal. 

Here is an overview, which files I added to make my homepage as you can find it [here](https://michael-fuchs-sql.netlify.app/):

```
C:.
│   config.toml
│   README.md
│
├───content
│   │   about.md
│   │
│   └───post
│           2021-03-03-entity-relationship-diagram-erd.html
│           2021-03-03-entity-relationship-diagram-erd.Rmd
│           MFuchs.png
│
├───public
│   │   MFuchs.png
│   │
│   └───images
│           MFuchs.png
│
└───static
    ├───images
    │       Database.png
    │
    ├───post
    │   └───2021-03-03-entity-relationship-diagram-erd_files
    │           p2p1.png
    │           p2p2.png
    │           p2p3.png
    │
    └───themes
        └───hugo-lithium
            └───static
                │   MFuchs.ico
                │
                └───images
                        hugo-logo.png
                        logo.png
```


Here is the result of the settings I made:

<p align="center">
  <img src="https://github.com/MFuchs1989/Making-a-Website-with-Blogdown/blob/master/images/Result.png?raw=true" alt="python"/>
</p>



<a name="add_google_analytics"></a>

## Add Google Analytics

If you want to include Google Analytics on your homepage, follow these steps:

- 1 Sign up for [Google Analytics](https://analytics.google.com/)
  * 1.1 Create an analytics account (see this guide from [Jennifer Sloane](https://www.youtube.com/watch?v=l27LNXm5LHA))
  * 1.2 Create a property
  * 1.3 Create a data stream -> here you will get your Tracking-ID / Mess-ID
- 2 Go from the root directory of your repository to `\themes\hugo-lithium\layouts\partials`
  * 2.1 Create a folder with the name "google"
- 3 Go to `\themes\hugo-lithium\layouts\partials\google`
  * 3.1 Create a html-file with the name "analytics.html"
- 4 Go to `\themes\hugo-lithium\layouts\partials\google\analytics.html`
  * 4.1 Add the following code:

```
<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=XXXXXXXXXXXX"></script>     <- put in here your Tracking-ID
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'XXXXXXXXXXXX');     <- put in here your Tracking-ID
</script>
```







<a name="authors"></a>

## Authors

+ [Michael Fuchs](https://github.com/MFuchs1989)

<a name="motivation"></a>

## Motivation: 

I've been blogging since 2018 on my homepages about all sorts of topics related to Machine Learning, Data Analytics, Data Science and much more.
To enable others to blog on their own homepage I wrote this tutorial.

You are welcome to visit my Blog Posts:

+ [Python Blog](https://michael-fuchs-python.netlify.app/)
+ [R Blog](https://michael-fuchs.netlify.app/)
+ [SQL Blog](https://michael-fuchs-sql.netlify.app/)



