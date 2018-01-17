+++
title = "UPDATE OF ''What statistical package should I use?''"
date = 2011-09-06T18:07:47-07:00
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
Technological progress continues. In an older [posting](/post/what-statistical-package), I mentioned the role of specialized packages that addressed models not available in the general purpose software, such as LISREL for structural equation modeling (SEM). That example is now somewhat moot, as Stata 12 has an extensive SEM capability and new add-ons for R allow modeling of SEMs. I suspect that if I were a power user, I would find limitations in Stata/R relative to the dedicated packages, but at my level, I haven’t found them.

Of course, there are still uses for dedicated packages. From the viewpoint of a Stata user, TDA still offers a few unique features for survival time modeling and HLM & mlwin offer some multilevel functionality not available in Stata.

I consider it an open question whether the broader availability of these models is a universally good thing. As I noted in my 2007 SMJ [paper](/publication/use-of-logit), one reason for some of the shortcomings in the field’s use of logit models is that they “look” just like OLS regression in Stata. I didn’t enjoy learning the funny Greek notation for laying out a matrix in LISREL, but it mean I had to have a deeper understanding of what was gone on in the model than is required to set up and run an SEM model in Stata.
