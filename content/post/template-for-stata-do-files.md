+++
title = "A template for Stata .do files"
date = 2010-09-07T14:11:04-07:00
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
There are many different approaches to writing and documenting the many steps that go into an empirical project. J. Scott Long has a great book, _The Workflow of Data Analysis Using Stata_, which I strongly recommend. He recommends developing a series of small, highly focused do files, which are run in sequence as needed. I take a different approach, which is keep all of a project's code in one honking large do file, which is divided into sections. This posting provides more details about my approach. I've pasted a skeleton version of this below. To explain what I'm trying to do in several places, since this is pretty idiosyncratic.

## The HEADER section
a) gives information on the file (in case I ever find a print-out of it somewhere and need to find it on the computer)

b) lists what files are used and produced by each section. Great when I can't figure out where "important_data_file_1" comes into play. I could probably do the same just be searching, but I like this way.

## The MACROS section

a) I use the local macro "do_me" to control which sections get run for a given run of the do file. The sections are labels a-z and I just insert the letters of the section I want to run into the do_me macro (here, I'll run parts a and b). More below.

b) defines some temp variables, files, etc., just for future reference.

## The MAIN CODE block

a) Since I like to run my code and then examine the aftermath, I turn more off

b) The line
```
if strpos("`do_me'","a")>0 {
```
evaluates to some number greater than 0 if I included "a" in my definition of _do_me_. In that case, everything with the brackets defining section "a" will be run. If "a" isn't in _do_me_, this evaluates to 0 and nothing between the brackets is run. And so on and so forth. This way I can go to one point of the do file (the Macros section), see what each section does and flip them on or off for a given run.

Typically, section A is all about taking raw data and manipulating it into the data I'll use and then saving that for use by subsequent sessions. With any luck, I only have to run this section once. Section B is probably descriptive statistics, C-?? will be different modeling strategies. Then there will be a section for producing publication-ready output.

The pluses I've found to this system are that everything is captured in one place, easy to reference, edit and run. I don't have to comment sections in and out to control what runs. There are minuses. Because the file is so long, typically, one has to watch it all scroll by on the screen. When editing, getting from one section to another can be a pain. I've solved this by always using text editors that allow for tags or bookmarks. I assign the tag "0" to the line "_local do_me..._"; the tag "A" to the starting line of section a, etc. Puts any part of the code within a few keystrokes.

As I’ve re-read Long’s book several times, I’m seeing benefits to his approach. I’m not sure if I’ll actually switch, but I’m tempted to experiment.

{{% alert note %}}
As of January, 2018, I've slightly modified my approach from what is described here. One of these days, I'll make an updated post. I think the logic of this approach, however, is still valid.
{{% /alert %}}

## An example file

```
/*

FILE NAME:

DESC:

A:

Input files

Output files

B:

Input files

Output files

*/

/*MACROS*/

local do_me "ab" /*Which sections to do */
// a. Description of what part "a" does
// b. Description of what part "b" does
// c.
// d.

local base
local base
tempvar tv1
tempvar tv2
tempfile tf1


/*BEGIN MAIN CODE BLOCK*/

set more off

/* A. Description */
if strpos("`do_me'","a")>0 {
set memory 250m
clear
cd `base'

[Insert code here...]
save working_data, replace
}

/* B. Description */
if strpos("`do_me'","b")>0 {
set memory 250m
clear
cd `base'

use working_data
[code here]
}
```
