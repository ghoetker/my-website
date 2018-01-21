+++
title = "Reasons to Prefer a Mac"
date = 2014-02-06T16:06:49-07:00
draft = false

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Software"]
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
I’ve been a Mac fan since 1984 because, well, I think the Mac OS is more intuitive, stable and enjoyable to use. But, totally aside from that, I think there are three reasons that a Mac may be a better choice for many PhD students.<!--more-->

{{% alert note %}}
Obviously, a bit out of date. However, I think my observations still stand. The one caveat is that I've moved to BibDesk rather than EndNote, so can no longer speak to the quality of its AppleScript support. BibDesk's AppleScript support is quite good.
{{% /alert %}}

## Applescript

Applescript is Apple's rather, well, funky, scripting language that allows one to automate programs. Several ways this can be useful. Within a single program, you may find yourself performing the same action very frequently. Especially if it requires several steps, automating it could be helpful. For example, I take notes on PDFs in the free PDF reader, Skim. I want to export those as individual text files, each named according to elements of the notation. Applescript lets me do that with a single click of a menu.

Even more useful is using Applescript as the "glue" between programs. For example, I don't like how Endnote automatically stores and names imported PDFs. I have an Applescript that goes into Endnote to figure out the files current name and location, as well as what the file should be named according to my preferred scheme (firstAuthor-year-recordNumber.pdf). It then goes out to the Finder, moves the file to the right folder and renames it appropriately. Lastly, it goes back into EndNote and points the "File attachment" record to the now properly named and located PDF. As another example, the Skim export I mentioned above actually follows up the export by tagging each text file with tags generated from the annotation I made.

Not every program is Applescript friendly, but for the ones that are, Applescript can really help create an efficient, integrated ecosystem.

## Unix

The current Mac operating system is actually a pretty user interface on top of the Unix operating system. This has two advantages.

First, you have access to all the power of Unix. In particular, _awk_ and _sed_ are occasional lifesavers when it comes to munging very funky data. For example, I recently dealt with a 1.5 gig text file of patent data. I didn't actually need many of the columns and had to deal with some very, um, "Interesting" decisions that had been made regarding the coding of the data. I certainly could have pulled it into Stata and managed it there, but it was easier and faster to throw a couple lines of *awk* and *sed* at it to keep just the columns I wanted and regularize the funky coding. Other little commands like *head* make it easy to peek at the top of a big file, *curl* and *wget* make it easy to download information from websites, etc.

Second, there are a ton of programs, some very, very specific, others more general, available for Unix. For example, there are some sophisticated web-scrappers. These are generally easy to install and run on the Mac (see <http://www.macports.org>, <http://www.finkproject.org> and <http://brew.sh> to get a sense of the packages available in an easy to install way).

## Tagging

Mavericks, the newest version of the Mac operating system, introduces the ability to tag files. For example, I tag PDFs with the name of projects for which I think they are relevant. In that way, I can do a quick search and pull together all the relevant files for a project. I also tag according to the subject of a file (PDF, Powerpoint, text file, whatever). Especially combined with programs like Ammonite or Leap, this makes it really easy to see what you've gathered about a subject. So, I can start a search in Leap with "teaching" and see all of the files related to teaching, as well as the tags they have been given. Further limit to "strategy" and I can see that I've tagged 12 files related to Five Forces, of which 2 are videos, 1 a cartoon, and the rest PDFs.
