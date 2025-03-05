# Making a Static Website to Host Documentation

This README file outlines all of the steps required to host a statically generated website using Jekyll.
We will host the website and its files that we create using a service called Github Pages, this will allow it to be
accessible to the public at all times. This README is meant to be accessible to any person with a beginner knowledge of websites and markup languages. A few of the terms that will reappear many times throughout this README file include: **Static Site Generator**, **Forge**, **Markup Language**. I will be relating most steps of this README to reccomendations outlined in Andrew Etter's book: [Modern Technical Writing: An Introduction to Software Documentation](https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS).

**Static Site Generator:**  
A static site generator is a software service that takes some template and files defined by a user with a static (unchanging) configuration. It takes these files, which can be written using a lightweight markup language like markdown, and renders them so they can be viewed in a browser.

**Forge:**  
A forge is a web-based service that will allow us to host the files and the rendered website publicly. Etter suggests to use some kind of distributed version control which will centralize all your documentation, a forge will acheive this.

**Markup Language:**  
A markup language is a type of language that is used to annotate or structure text in a machine readable format. Structural or organizational elements are represented by symbols which determine how they will be displayed. Etter suggests that choosing a lightweight language with simplistic syntax is optimal.

## Prerequisites

### 1. A Static Site Generator

To create our static website we will be using Jekyll, a static website generator that uses your favourite markup language and a layout to display a website. The language you choose should preferably be a lightweight language like markdown.  

For **Jekyll** You will need to install the following three prerequisites:
- [Ruby](https://www.ruby-lang.org/en/) (A programming language) Version **2.7.0** or later.
- [RubyGems](https://rubygems.org/pages/download) (which is usually included with Ruby)
- GCC and Make (Tools for compiling the project which are included when using the ruby installer)

    Here is a link to the official **[Ruby and Jekyll installation guide](https://jekyllrb.com/docs/installation/#requirements)**. Please choose the link for your operating system from the list of guides.

### 2. A Forge

To host all of the files for the website, and the site will accompany them, we will be using **Github** and one of its services called **Github Pages**. Github is a web-based platform used to store, track, and manage all changes to the files of a particular software project. Github Pages is a feature of github that allows users to host their statically generated website for the public to view.

For **Github** we will need to follow some steps to create an account and a repository (Where we will put all of our files and documentation).
1. Download [Git](https://git-scm.com/downloads) (The version control software that github uses, it comes with git bash which will be used later).
2. Create a [Github](https://docs.github.com/en/get-started/start-your-journey/creating-an-account-on-github) account if you do not have one.
3. Create an empty [Github Repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/quickstart-for-repositories)
4. Follow the steps for creating a new [Jekyll site with Github Pages](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll#creating-your-site).

### 3. A Markup Language

All of the content that you wish to put on your website will be formatted using a markup language to convert it into something the website can display. We will be using **Markdown** which is the most popular lightweight markup language. If you are not familiar with markdown, please follow this [tutorial](https://www.markdowntutorial.com/) to get started.

## Configure Your Website

Before we can get started adding new content to your website we need to configure a few things.

1. Navigate to your project folder.
2. Open the file called: **_config.yml**
3. You will encounter a segment in the file that looks like this
    ``` yaml
    title: The title of your website
    email: Your email
    description: A description of your website
    domain: The domain name of your website
    baseurl: The base URL
    url: The base hostname e.g. http://example.com
    github_username: Your Github username
    ```
4. Fill in the above fields with the proper information.
5. If you are missing any of the fields you may add them, also you may add additional customizations as defined [here](https://github.com/jekyll/minima/blob/master/README.md#customizing-templates).


## How to Add Content to Your Site

After you have created your site and hosted it on Github Pages, you will likely want the ability to change your sites content and the way that it is displayed. Follow these steps to achieve this:

1. **Choose a theme:** A theme is a preset layout of site visual styles and page layouts. Jekyll has a large selection of official and community made themes that you can choose from. We will be using the minimalist default theme which is already installed in your project called **Minima**.

2. **Adding content**: The theme we are using comes with layouts for a few different kinds of website content. The two that we can add are **Posts** and **Pages**. For any kind of content you wish to display you will have to create a markdown file containing that content. At the top of each of these markdown files we will place some code which is called [front matter](https://jekyllrb.com/docs/front-matter/) like below:
    ``` yaml
    # For a page
    ---
    layout: page
    title: Your page title
    permalink: The url path relative to the base url e.g {/page/}
    ---
    # Content written in markdown.
    ```
    ``` yaml
    # For a post
    ---
    layout: post
    title: Your post title
    author: Your post author
    categories: Your post categories
    modified_date: The date this post was modified
    tags: Any content tags you wish to include
    ---
    # Content written in markdown.
    ```
        For either layout you can choose to omit any field other than the layout field.

3. **Adding a post:** to add a post to your site you will have to follow these steps:
    1. Find the **_posts** folder in your project.
    2. Place the post markdown file you just created in step #2 in this folder.
    3. Rename the markdown file using this format **YYYY-MM-DD-TITLE.md**, the theme will interpret the date from the name of the file and display it.
4. **Adding a page** to add a page to your site that will appear in the navigation bar follow these steps:
    1. Find your main project folder.
    2. Place the page markdown file you have created from step #2 in your main project folder.
5. **Adding files to your Github project from your computer**:
    1. For any of the above files you have created, if you did not create them directly through Github, you must use the following command in git bash to add them to your project on the web:
        ``` bash
        $ git add filename
        $ git commit -m "Your commit message"
        $ git push origin main
        ```
## Further Resources and Reading
If you are interested in learning more about all of the topics we have covered, please feel free to visit the following official resources
- [Jekyll Offical Documentation](https://jekyllrb.com/docs/)
- [Git Official Documentation](https://git-scm.com/doc)
- [Github Offical Documentation](https://docs.github.com/en)
- [Markdown Guide](https://www.markdownguide.org/)

## FAQ (Frequently Asked Questions)

1.
    **Question:** Can you add and customize your own layouts to use in your site?

    **Answer:** Yes, you can absolutely add your own layouts to your project. However, you will need a basic knowledge of HTML and preferably also CSS to format the layout properly, here is an easy [tutorial](https://easyhtmlcss.com/). Next, you will need to follow these steps.  
    1. Add a folder called **_layouts** to your project.
    2. Add a .html file with the name of your new layout.
    3. Follow the steps [here](https://jekyllrb.com/docs/layouts/) to format your new layout.


2.
    **Question:** I have changed the files in my project on my computer but the website isn't updating, what is wrong? 

    **Answer:** This is a common problem when you are working with a platform like Git for the first time. For every file you change in your project on your computer you have to send those changes to the version that is on the web. Refer to the How to [Add Content to Your Site section](#how-to-add-content-to-your-site) at step #5.

    If you have already done this and nothing is happening the site is likely in a queue to be deployed, wait a couple minutes and check back.

## Credits

- Class group members who collaborated on the editing of this README:
    - **Yi Ning Ding**
    - **Daniyal Chaudry**
- Theme used for the website: 
    - **Minima**
- Technologies used and referenced:
    - **Jekyll**
    - **Git**
    - **Github**
    - **Github Pages**
    - **Markdown**
    - **Ruby**










 

