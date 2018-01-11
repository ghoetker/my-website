+++
title = "Using Mindmapping software for class preparation"
date = 2016-12-21T15:55:54-07:00
draft = false

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Teaching", "Software", "Mindmapping"]
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

Mindmapping has been around for a long time in various forms and there are many software packages available. In this post, I discuss how I use iThoughtsX to plan my classes. Nothing I'll discuss is specific to iThoughts since many other packages offer similar features. Having tried most of them, I've found that iThoughts best meets my working style. I especially appreciate its amazing export options and the fact that files move seamlessly from its Mac to iPad versions.

As shown below, I've made a map for my class. Each of the branches shown has many sub-branches.

![](/img/iThoughtPreview1.png)
￼
This makes it a great tool for the doodling around stage of planning, especially since moving an item from one branch to another is so quick.

![](/img/iThoughtsmovingItems.gif)
￼
It also gives me a place to store items I come across between times I teach, so there are all in one place when I come back to prepare for the next edition of the class. I can tag new items with the pencil icon to give me a visual clue that these are new since last time I taught (there are a slew of additional icons available and you can search or filter using them).

That's all pretty standard application for mind mapping. My real breakthrough came when I realized I could use a mindmap for the more nitty gritty part of planning and organizing the class. My mindmap allows me to

* At the macro level, layout each class session and how they will fall into larger subject modules.
* Schedule the readings for each class.
* Add additional text that will become part of the reading list.
* Track which classes/modules have been fully prepared and which still need work.
* Export an image that I'll use in our first class to illustrate the overall structure of the class
* Export information that allows me to automatically compile all of the relevant PDFs and links, organized into folders by class session.
* Export information that allows me to automatically generate the syllabus I'll distribute to the students.

The last two items on that list depends on other geeky technology, but even iThoughts itself it can do amazing things. The material that will become the syllabus all resides in the "Class Sessions" node. First I created a node for each subject module and each class session therein. Because of how easy it is the create/delete branches and move items between branches, I started with a very rough outline and refined it as I went. In the same way, it was trivial to reorganize the subject modules between annual editions of the class.

![](/img/iThoughtspreviewme8_540.png)

Within each class, I created nodes for Readings and Assignments. Having created it once, I copy-pasted it to the other sessions. If appropriate, I added subdivisions for the readings in each class. Then, I created nodes for each reading. For most of them, I copied information over from EndNote, which is how I organize my reference library. I've set iThought to automatically alphabetize items for me.

￼![](/img/iThoughtspreviewme4_860.png)

The arrow on the node indicates that there is a link associated with it. That can be a link to a website or to a file (created by dragging the file onto a node). Clicking on the arrow will open the associated file, which makes it easy to re-examine items ("How long was the Carlson paper?"). I can also add notes for each node, either for myself or, as in this case, to become part of the syllabus.

￼![](/img/iThoughtspreviewme5.png)￼

Each node can also be associated with task management information, which I've repurposed. Here, I've tagged a class session with the date it occurs, how many days it will take and marked its progress as "Rollup", that is, what proportion of the nodes below it have been completed.

￼￼![](/img/iThoughtsPreviewme7.png)

This allows me to see that I've completed the "Setting the stage" module (the checkmark) and that I've dedicated 3 class sessions to it. Because this all updates dynamically, I can trivially track that I've not dedicated too much time to any one subject and have stayed within the 16 class session I have.

￼￼![](/img/iThoughtspreviewme3.png)
￼
Once I've finalized everything, I can take advantage of iThoughts export capabilities, which include exporting to a PDF, a website, images, Word/Excel/Powerpoint (with lots of flexibility), other mindmapping formats, and Markdown. Simply exporting to Word would give one a great start on the Syllabus, needing minimal additional formatting. To leverage the other systems I have in place, I go another route, which I'll *briefly* describe just to give a flavor of what is possible.

First, I export everything in the "Class sessions" node as a comma-delimited .csv file. I use a short Python script to extract information on each reading, which is used to copy the PDFs for each session into an appropriately named folder. Compiling all the PDFs in this way takes under 10 seconds and guarantees I don't omit a reading. Second, I export as a Markdown file. Markdown, if you've not encountered it, is a plain text format meant to create a document that is easy for humans to read, not locked into any proprietary format (Word, Pages, etc.), yet able to be translated into PDFs, websites, Word documents, etc. For my purposes here, the key thing is that Markdown is plain text, which means I can take advantage of basic Unix (Python, etc.) tools to tweak it to exactly how I want it--removing some exported information I don't care about, etc. Then I use the amazing (and free) pandoc software to turn the Markdown into a LaTex file, which I compile into a beautiful PDF. Because I've written a shell script to do the tweaking and have a LaTeX template set up, I can go from export to completed PDF in about 20 seconds.

Obviously, this is a time-saver (once I used it enough to make up for the development time involved). More importantly, it frees me to refine my class plan without friction. If I want to add a reading, move a reading between sessions, combine two sessions, etc., I simply do so in the mindmap document. In well under a minute, I will have an up-to-date syllabus and folder of organized readings, with no chance for error. It is easy to keep my class up to date and I've been more willing/able to experiment with alternative organizations.

Having set up this system, I use it for all of my classes with minimal change. It's great from the "blank-slate" stage of planning through producing the final syllabus.

Although I didn't show it here, I use the same mindmap to make detailed plans for each class session. It's especially helpful for my 4 hour evening MBA class, where I have lots of different activities each session and need to be very aware of time management.

I've also used iThought to deliver material in class. For example, I use it to present a timeline of sustainability-related events over the last 140 years. It works great because the map conveys the overall structure, while I can link individual nodes to videos, images, sound clips, websites, etc.
