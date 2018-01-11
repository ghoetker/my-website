+++
title = "Excel Is evil"
date = 2010-09-07T13:57:08-07:00
draft = false

# Does the project detail page use source code highlighting?
highlight = true

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Stata", "Statistical packages", "Software", "Excel"]
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
Excel has caused more trouble for more doctoral students than I care to think about. Doctoral students can hurt themselves with Stata in at least two ways (there may be more).

* Using it to clean, combine and otherwise manage data
* Cutting and pasting results into Excel (or worse yet, Word) and then formatting them for presentation

Both of these a very inefficient uses of time. The first is a disaster for data integrity, because it is hard to document, almost impossible to revise, and very easy to mess up (sort only have the variables, be one row off when pasting, etc.).

The second use of Excel is also prone to mistakes, although they are probably more easily corrected than butchering your data in Excel. Fortunately, there are many better approaches.

## Descriptive statistics

There are several packages available to produce correlation matrices and descriptive statistics for publication. I wrote _mkcorr_ several years ago (like most user-written additions to Stata, it can be installed with the command `ssc install mkcorr, replace`). _mkcorr_ produces a correlation table in a format that is easy to import into a spreadsheet or word processing document. So, there is still formatting to do, perhaps even in, shudder, Excel. But, by writing the output directly to a logfile, it avoids two problems with cutting and pasting correlation tables from the results window. First, it allows an effectively unlimited number of variables without wrapping around. Second, it requires less post-processing in a spreadsheet or word-processor, particularly for more involved tables. It also offers a number of small advantages such as allowing the use of labels, controlling the number of decimal places used, and other formatting options. _corrtex_ extends this and allows creation of tables directly in LaTeX.

{{% alert note %}}
As of January, 2018, this part is somewhat out of date, as Stata 15 offers multiple ways to output directly to Word and Excel. However, _mkcorr_ may still fit some workflows better.{{% /alert %}}

A brief aside--LaTeX is a document layout language. It allows for very sophisticated and elegant tables and excels in formatting mathematical formulae. It is also a bit of a throwback to pre-GUI days. If you don’t already use LaTeX, I wouldn’t learn it just as a complement to Stata, particularly in you have co-authors who don’t use it. Worse yet, several journals will only accept submissions in Word. There is a midway point: using LaTex to produce tables, rendering them as PDFs and inserting those into a Word document.

## Producing tables of results

{{% alert note %}}
Despite Stata 15's ability to output directly to Word and Excel, there is definitely still a place for _estout_ (and perhaps _outreg_, although I've not used it for several years) because of the fine-grained control they give over the content and appearance of the output.
{{% /alert %}}

Here is where the different between Excel and the right tools is largest. There are several approaches available within Stata.

_outreg_ was the original add-on for producing tables more easily. It produces a tab delimited file with lots of formatting options. This can then be imported easily into a word processing or spreadsheet program, where additional formatting (cell-borders, bolding or italicizing) may be performed if desired. Because of the control it offers and the fact that it is programmable, it beats cutting and pasting.

_estout_ is part of the “second generation” of table producing add-ons for Stata and gives the user tremendous control. I’ve yet to meet a table of results that it can’t produce. It can be used to produce a correlation table, too, but I find the more specialized _mkcorr_ better for this purpose (of course, I wrote _mkcorr_, so I may not be totally unbaised). One of the great things about estout is that it produce its tables in comma delimited text, fixed format text, rich text format (rtf), html, or LaTeX. Just a little bit of code makes it easy (at least on a Mac) to have a beautiful table open automatically as either a PDF (from LaTex) or Word (from an rtf file). estout’s syntax can be a bit overwhelming, given all its options, so there is also esttab, which is just a “wrapper” for estout, providing a simpler syntax. It’s worth the effort to learn estout/esttab, because once you’ve mastered it’s basics, you’ll use the repeatedly.

Roger Newson has provided a suite of commands that offers a slightly different approach. One saves summary statistics, the results of regressions, etc. in “resultsets” (which are just Stata datafiles) and then uses one or more commands to produce tables from those. My personal preference is for estout, but Newson’s approach has a large and enthusiastic following.
