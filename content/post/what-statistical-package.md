+++
title = "What statistical package should I use?"
date = 2010-09-06T18:12:23-07:00
draft = false

# Does the project detail page use source code highlighting?
highlight = true

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Stata", "Statistical packages", "Software", "R", "SPSS", "SAS"]
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
This is an amazingly contentious question. My first answer is "If you are comfortable with a package and it is serving your needs, keep using it." That can be complicated, of course, if you have a co-author dedicated to a given statistics package. If your only need to is pass data back and forth with that co-author, I strongly recommend Stat Transfer, which can convert from pretty much any statistical format to any other. Another consideration is the package most frequently used in your field.

If you are not already using a specific package, here are some (very idiosyncratic) observations on some of the more popular packages.

* [Stata](http://stata.com) is an increasingly popular and powerful package. It is my runaway favorite. Strengths include the ease of using a command line interface, a menu-based interface, or saved “do” files of commands. The menu-based interface produces the appropriate command line commands, so it is a great way to improve your understanding of Stata’s command language. The Stata documentation is first rate both in its examples and its presentation of underlying econometric theory. There is also a large Stata user community which (1) powers the Statalist mailing list, where members are very generous at helping answer questions both simple and complex and (2) contributes a huge number of user-written commands which one can easily add to one’s Stata toolkit. Several of these commands make it very simple to produce ready to publish tables of results, summary data, correlation tables, etc. That saves one from having to do post-formating in Excel or Word. With Stata’s Mata language, aimed mostly at matrix manipulation, one can craft powerful and fast programs. Stata’s main command language is quite powerful in itself, but Mata can be pre-compiled and is good at especially complex calculations. Stata’s can produce attractive graphs of many types. Because there are so many options, it can be a little overwhelming at first (good chance to use the menus to learn) and Stata doesn’t do 3-D graphics (several user written modules to do so are quite basic). Additionally, it isn’t primarily focused on data manipulation. I’ve never found anything I can’t do, but sorting and merging huge datasets can take a VERY long time.

* [R](https://www.r-project.org/about.html) is the free version of the S+ statistics package. S+ offers a more sophisticated GUI, but most people I know use R instead. With its own commands and a huge number of very specialized user-written additions, R can do pretty much anything under the sun. It also has very good graphics capabilities. Its great strength and weakness is that it makes you get deep into the guts of problem. Performing a regression can involve

```R
`gfit <- lm(Species ˜ Area + Elevation + Nearest + Scruz + Adjacent, data=gala);`
`summary(gfit)`
```

That can present a significant learning curve, but it is also helpful in learning what’s really going on in the model one is running.

* [SAS](https://www.sas.com/en_us/software/stat.html) is one of the oldest of the packages. To me, it seems unnecessarily complex and somewhat stuck in the past (come on, “Cards” as a way of identifying that what follows is data). However, it has a huge user community, many very specialized packages, and is superb at data manipulation when using large data sets. I suspect that if I still used SAS (I abandoned it about 7 years ago), I would sing its praises, but I’m not sure why one, starting from zero, would choose it over Stata.

* [SPSS](https://www.ibm.com/products/spss-statistics) is another very popular package. For a long time, it offered one of the best menu-based interfaces and thus had a very low learning curve. With Stata (and even SAS) now offering good menu interfaces, SPSS no longer has that advantage. It also doesn’t offer the range of sophisticated models the other packages I’ve mentioned do.

* Specialized packages There are a plethora of specialized packages out there. Some can perform a broad swath of models, but are really specialized in one type of model. Examples include LIMDEP (limited dependent variables) and TDA (survival analysis). At one point, these offered significantly better handling of their speciality than any general package. In many regards, the general packages have caught up to maybe 90% of the specialized packages capabilities. So, unless you really need to capabilities available in a specialized package, you are probably better off to stay with the general package, rather than learning a whole new set of commands and syntax. Having once been a very capable user of both TDA and LIMDEP, it pains me to write that last sentence, but I haven’t used either in four years and don’t foresee doing so in the near future.

Another set of specialized packages offer capabilities that are either absent or relatively underdeveloped in the general purpose packages. These include LISREL and AMOS for structural equation modeling and HLM for hierarchical linear modeling. At least for now, it is worth giving these a close look if they address your needs for a specialized modeling technique.

In closing, it used to be worth mastering multiple packages to have a big toolkit to use. As packages have grown and now largely overlap in their capabilities, becoming highly capable in one (or perhaps two ) packages is much more useful.
Tags: Stata, Statistical packages, Software
