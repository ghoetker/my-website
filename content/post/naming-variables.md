+++
title = "Naming variables, especially in Stata"
date = 2013-11-06T17:38:34-07:00
draft = false

# Does the project detail page use source code highlighting?
highlight = true

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Stata"]
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

A consistent scheme for naming your variables is very helpful. It makes coming back to a project after it’s been under review for 3 months much easier and is especially valuable when collaborating with someone else. This is one of those points where there are bad practices and good practices, but no "right" practice. More important is consistent project within (ideally across) projects. So, as a starting point for your consideration, here is what I have developed over time, through lots of trial and error. I think this approach make it easy to find variables and understand their provenance.<!--more-->

We're aiming for a balance of quick and easy to type, while being easy to understand. Remember that Stata allows us to use descriptive labels for output, meaning the reader won't ever see our variables name, so don't call a variable, _theYearThatYourParentsEnteredTheCountry_. Something like _yearParentsEntered_ is sufficiently descriptive. On the other hand, _ype_ is probably going too far in abbreviation.

_Capitalization_. My strongest feeling here is to avoid ALLCAPS names. They are hard to read, hard to type, and scream 1990s software. Favor, instead, lower case. Well, actually, what's called "Camel case" by some, since it has "humps" in the middle. For example, _workEthic_. I find that relatively easy to read and type.

_Modified variables_. Indications of modifications of variables go at the end. This has several advantages. If we want to describe all versions of the workEthic variable, we can use the command `describe workEthic*`. We can also take advantage of auto-complete more easily. Examples to follow include:

•	_workEthicSq_. The square of _workEthic_.
•	_workEthicCu_. The cube of _workEthic_.
•	_workEthicC_. The centered version of _workEthic_.
•	_workEthicSt_ The standardized (mean 0, sd 1) version of _workEthic_.
•	_workEthic_ and _workEthic2_. Suppose we have two ways we've measured work ethic. Perhaps the first is based on the average of three variables and the second is based on the average of just two of those variables. Name one of those _workEthic_ and the other _workEthic2_. A third version would be, of course, _worthEthic3_. We want to avoid the confusion that results from having multiple versions of a variable with the same name. We don't want to wonder which _workEthic_ was used in a given regression.

Add indicators of modification in the order in which the modifications were made, from left to right. So, _workEthic2CSq_ means we took the second version of _workEthic_, centered it, and then squared that. _workEthic2SqC_ means we took the second version of workEthic, squared that, and then centered the result (which is a really weird thing to do). _workEthic1C_ and _workEthic2C_ are the results of centering the first and second versions of _workEthic_, respectively.

_yr2000_. Stata doesn't allow variables to start with a number. This is most often a problem when raw data has observations labeled by year, e.g, "2000". Renaming by prepending "yr" is helpful when it comes time to reshape the data, as it allows us to refer to the stub "yr". If we just preceded the variable with "y" (as I used to, sigh), then if you have a variable named _youngKids_, you have to take extra steps to work around it. Very few other variable names start with "yr".

There are some characters allowed in variable names in programs that don't work well or at all in Stata. These include ampersands, dashes, hashmarks(#), periods, commas, parentheses, question marks, exclamation marks, asterisks, and probably about any other punctuation.

Just FYI, here's why I now avoid several things I used to do. I no longer use underscores, e.g., _work_ethic_, because they add lots of typing and add length to variable names without adding information or much readability over camelCase. I don't use the number "2" to indicated squared variables, e.g., _workEthic_2_, because it can be confused with the version of the variable. Lastly, I try to avoid descriptors such as "original", "new", "old", "main", "regular", "alternative", etc., because they aren't easy to standardize and tend to pile up over time. Which came first, _workEthicNew_ or _workEthicAlternative_? Did _workEthicOriginal_ come as is from the raw data or was it or first attempt at forming the measure? Etc.

You will often get data in which these norms have not been followed. Actually, I've never gotten raw data in which they have all been followed. It's not worth renaming all of the original variables, especially if a lot of them won't be used. My preference would be to add lines to the variable manipulation version of the do file if and when it becomes obvious that we'll use a variable. So, if we're going to use _var1_ a lot, it's worth doing `clonevar var1 yearPartentsEntered` and subsequently using _yearPartentsEntered_. If you group those together in the code, it's pretty easy to track down the original origin of any variable.

On the other hand, if you are going to average ten measures called _Var1_ through _Var10_ to generate the _workEthic_ variable and then just use that, I probably wouldn't bother renaming the original variables either to the camelCased _var1_ or to the more informative _finishJobImportant_, _lazyPeopleBad_, etc. Just not worth it when we can just do `egen workEthic=rmean(Var1-Var10)`.
