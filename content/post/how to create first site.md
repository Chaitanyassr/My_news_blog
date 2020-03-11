+++
title = "How to create a first site using hugo"
description = "hugo firtst blog"
date = 2020-03-03T02:13:50Z
author = "https://www.freecodecamp.org/news/your-first-hugo-blog-a-practical-guide/ Flavio Copes"
+++

# hugo first site creation,

## How to Create Your First Hugo Blog: a Practical Guide

Hugo is a great tool to use if you want to start a blog.

I use Hugo myself for my blog, flaviocopes.com, and I've been using it for more than two years. I have a few reasons for loving Hugo.

First of all, it is simple, boring, flexible, and fast.

The main reason is that it is simple. There’s not much you have to learn to get started.

You write content in Markdown, a format that lets me use my favorite editor (Bear) to write posts.

Hugo is boring. Don’t get me wrong, this is a very positive thing. As a developer I am tempted to tweak things here and there all the time. There’s no fancy technology underlying Hugo. It’s built using Go, one of the languages I love the most, but that does not mean I want to dive into the internals of Hugo and change how it works.

And it does not surface any cool or next-generation stuff like many JavaScript frameworks tend to do.

Hence it is boring, which gives me a lot of time to do what is really useful when working on a blog: writing content. I focus on the content, not on the content container.

That said, Hugo is pretty darn flexible. I started my own blog with an open source theme, then changed it completely over time. Sometimes I want to do things in my website that are out of the scope of a simple blog, and Hugo allows me to create those things.

Finally, another reason I love Hugo is that it is fast. Why? First, it has Go at the core, which is known to be a very fast language. And in the Go ecosystem, there’s no concept of 100 megabytes dependencies. Things are made to be as fast as possible. Plus, Hugo does not need to do some of the fancy stuff that is needed when using fancy technology. This is a by-product of being boring.

Anyway, enough with words.

Hugo is amazing, especially if you are a developer and you’re willing to write in Markdown. Non-tech people might just refuse to use Markdown, and it’s perfectly understandable.

Also, you have to be prepared for a Git-centric workflow to make things really click.

This is the process for writing a blog:

write a post using Markdown,
then commit your changes to a Git repository, most commonly on GitHub,
and then some glue technology deploys the changes on the server that hosts the site.

## Hosting a Hugo website

A Hugo blog is completely static. This means you don’t need to host your own server, or use a special service for it.

Netlify, Now and GitHub Pages are three great places where you can host a Hugo blog, for free.

The only cost is the one you have to sustain for the domain name. I can’t stress enough the importance of having your own domain name. No .github.io or .netlify.com or .now.sh sites, please.

My own Hugo sites are hosted on Netlify.

## Choose a domain

Put your blog under your own domain. Pick one. Use your own name. And use .com or .blog. Don’t try to be clever by using a localized domain - for example, don’t use .io. .com just gives a better impression and it’s reusable for all your future projects, not just to host your blog. I picked that one.

Oh and if you have an old domain lying around, just use that. Why? The older your domain is, the better.

Note on subdomains: every subdomain, to Google, is a different website. So if your domain is flaviocopes.com, and you create your blog in blog.flaviocopes.com, then that’s a completely new website to Google, and it will have its own ranking separate from the main domain.

My suggestion is to avoid subdomains completely.

Install Hugo
To install Hugo on macOS, from your terminal run

brew install hugo
The brew command does not exist on your Mac? Check the Homebrew guide.

For Windows and Linux, check the official installation guide.

Create a Hugo site
Once Hugo is installed, you can create a Hugo site by running

hugo new site myblog
I suggest that you run this into a www folder in your Home directory, because the command will create a new myblog folder where you run it.


Pick a theme
Now before you can start you need to pick a theme. I wish Hugo included a default theme to make things straightforward, but it does not.

There are a lot of choices on https://themes.gohugo.io. My personal recommendation is to start with https://themes.gohugo.io/ghostwriter/ and tweak it later.

I also recommend that you avoid the git clone workflow they suggest on that page. You’ll surely be tweaking the theme in the future, and I find it best to have a single repository for both content and theme. It simplifies deployment.

So, go to https://github.com/jbub/ghostwriter/archive/master.zip to download the current version of the theme.

Then unpackage it in the themes/ghostwriter folder in your newly created Hugo website:


Notice there is an exampleSite folder in the themes/ghostwriter. Open it, and open its content subfolder. In there, you can see the page, post and project subfolders.


Copy page and post in the content folder of the site:


The configuration
The sample data also provide a sample config.toml file in themes/ghostwriter/exampleSite/config.toml. This is the Hugo configuration file, which tells Hugo some details of the configuration without you having to hardcode information in the theme.

I recommend that you not copy that, because it has too many things, and instead use this:

baseurl = "/"
title = "My blog"
theme = "ghostwriter"

[Params]
    mainSections = ["post"]
    intro = true
    headline = "My headline"
    description = "My description"
    github = "https://github.com/XXX"
    twitter = "https://twitter.com/XXX"
    email = "XXX@example.com"
    opengraph = true
    shareTwitter = true
    dateFormat = "Mon, Jan 2, 2006"

[Permalinks]
    post = "/:filename/"
You can freely customize the information in this file later.

Now from the command line, run:

hugo serve

Open http://localhost:1313 in your browser, and you should be able to see the site live!


This is the site home page.

There is a list of posts that is taken from the content/post folder of your website:


Click the first, called “Creating a New Theme”:


You can open the file content/post/creating-a-new-theme.md to change anything in the post.


If you save, the website will automatically update with the new content.


This is pretty awesome, right?

You can create a new post by creating a new .md file, prefixing it with anything you want. You can use incremental numbers, if you prefer. Or use a date.

If something doesn't look the way you want, you can open the themes/ghostwriter/layouts folder and tweak it.

The “post” template is defined in themes/ghostwriter/layouts/post/single.html:


Hugo uses Go templates. The syntax can be pretty unfamiliar but the Hugo website does a very good job at explaining them in this Go templates introduction.

However, try to not look at customizing your template now.

If you want to tweak the colors, add a <style> tag with some CSS in the themes/ghostwriter/layouts/partials/header.html.

For example, make links black:

<style>
.site-title a, .button-square {
    background: black;
}
a {
    color: black;
}
</style>
Focus on the content instead.

Remove the existing files, and write 2-3 posts to start with.

It’s too easy to get trapped in making things perfectly the way you want, but the important thing is the content.

And the cleaner your site is, the better for your readers.

Let me now write a little about deployment.