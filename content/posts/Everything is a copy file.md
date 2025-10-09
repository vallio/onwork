+++
title = 'Everything is a copy file'
date = 2025-06-15
draft = false
tags = ["AI"]
weight = 10
+++
One of my early work projects was a mainframe copy utility, something I called bldcpy. It had all kinds of options to help system programmers with their daily tasks. Copy files across mainframe nodes, automatically link/detach drives, sfs/minidisk, on the fly content modifications. It even had tape/tape and disk/tape support. 

This was 30+ years ago, so details are fuzzier than a Qingdao sunset but I remember as I was developing this tool, an experienced (old) systems programmer told me “everything is a copy file”.  Well not everything, but many things. And throughout my career, I came to see it in many things we did. System builds. Migrations. Source repositories. Copy/Paste coding. Data cleansing. PPT generation. 

I recently found myself wanting to convert my family blog from Ghost to Hugo. My motivation was pretty simple \- Ghost is easy to use but as a service was prone to occasional glitches. All I really needed was a static site (just files) I could update easily. I started to think this could be a side project for me only to discover there were many such solutions already. I ended up selecting Hugo for its templates, its go-ness, and its simplicity. So I needed to convert my family blog with its 550 posts from Ghost to Hugo. 

Everything is a copy file. 

The blog goes back to 2006\. I originally hosted it on Windows Live Writer, then when that was killed moved it to a self hosted Wordpress site, then Medium, then back to Wordpress, and then a hosted Ghost, and finally a self-hosted Ghost. Along the way, there were no great conversion tools. These tools were something I could do well, but I didn’t have the time or motivation. The tools, such as they were, preserved the text but dropped many of the image links. For this final conversion, I had the time to do it “right”. By right, I mean have ChatGPT right python utility scripts for me. It was iterative and step by step:

- Ghost2Hugo.py: Takes a ghost backup and creates hugo posts.  
- FixImageLinks.py: Matches and updates image links in hugo posts from a library of existing images.  
- VisualImagePicker.py: I GUI where I could manually fix/verify image links, selecting from a local repository of images or by pasting the image.   
- FixFrontMatter.py: Create hugo post front matter with correct cover image and tags.  
- Markdown2Hugo.py: Convert Google Docs markdown to publish ready hugo post (unwinding images, writing front matter)

I didn’t bother to read the code or inspect the scripts. I checked the output. And when it didn’t do what I had in mine, I had ChatGPT correct the script. I trusted the code more than if I had written it myself. 

Pre ChatGPT, I could have written the scripts and probably would have been more systematic about it. I may have made parts of the scripts reusable. My value when I used to write code, was I could do end to end solutions and not get lost in a specific detail. I’m not sure how much of my coding background is helpful in writing prompts; the solution thinking does seems key. 

A comparison between cooking and coding: In the future, both will be done by hobbyists. 

When I was writing bldcpy, it was not lost on me that it was a wrapper on the real system functions that actually copy bits around. Since we had access to the mainframe source code, I spent some time looking at this system code. Most of it was “just code”. Today, ChatGPT would have no problem creating those parts. But deep inside CMS’s copy command, there was a “bit special” code that ChatGPT would not easily be able to recreate. Not without the right prompt. 