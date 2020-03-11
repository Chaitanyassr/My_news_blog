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