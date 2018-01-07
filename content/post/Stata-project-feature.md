+++
title = "Stata Project Feature"
date = 2013-11-06T17:58:54-07:00
draft = false

# Does the project detail page use source code highlighting?
highlight = true

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Stata", "Statistical packages", "Software"]
categories = []

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
# Use `caption` to display an image caption.
#   Markdown linking is allowed, e.g. `caption = "[Image credit](http://example.org)"`.
# Set `preview` to `false` to disable the thumbnail in listings.
[header]
image = ""
caption = ""
preview = true

+++
One of the features of Stata 13 and later is “Projects”, which are meant to provide easier access to multiple files related to a, well, project you are working on. The files can be do files, data, logs, graphs, etc. In fact, they don’t even need to be Stata files. One advantage I have found is that they make it possible to maintain a strict organization of certain types of files going in certain directories, while still having access to all of those files from one pane within Stata.

![](/img/stataProject1.png)

So, this project gives easy to access to data, do files, a text file mapping variables to hypotheses and, eventually, results. Setting up and managing a project isn't quite as automatic as I wish it was. For example, I haven't found a way to have a "template" to set up a new project just as I want. But, it's still pretty useful.

![](/img/stataProject2.png)

Equally useful if you have multiple projects going is the fact that opening a project by double clicking it opens up Stata and changes its working directory to whichever directory the project file sits in. So, on my Mac, I have a smart folder set up with "Kind is Stata Project File". This folder is dynamically filled with aliases to all the Stata project files on my computer. I've dragged that smart folder to my dock and now have, effectively, a pop up menu that can take me to any of my ongoing projects, ready to go. I suspect Windows has some way to do something similar.
