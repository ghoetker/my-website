+++
title = "Some useful utility programs for Stata"
date = 2013-12-06T16:25:56-07:00
draft = false
highlight = true
highlight_languages = ["Stata"]
# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Stata", "Statistical packages"]
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

You’ll probably spend a lot of your time doing data management and statistical analysis (which you _are_ doing in Stata, right?). So, small efficiencies in data related tasks can really pay-off in the long run. One way to get those efficiencies is through creating small utility programs that automate tasks that you perform many, many times. It's very easy to write short programs for Stata. Below, I offer a few program, each only several lines in length, that I find really useful.<!--more-->

Consider the dta command, which is saved as dta.ado in my "PERSONAL" directory (which you can find by typing `sysdir` at the Stata prompt. On the Mac, it is at _~/Library/Application Support/Stata/ado/personal/_.)


```
program define dta
    ls *.dta
    regress auto dog cat
end
```

Now, I can just type `dta` at the Stata prompt and get a list of all the data files in the current working directory. Here are some other examples. Each should be saved as _name-of-program.ado_, e.g., the next one should be saved as _ddo.ado_.

Same idea, lists all do files in the directory:

```
program define ddo
   ls *.do
end
```

Quick way to open the current working directory in the Finder. Makes it easy to get to related non-Stata files quickly. (May need to be different for non-Mac systems):

```
program define oo
    !open
end
```
