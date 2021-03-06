title: How Django Makes Web Programming Stupidly Easy
date: 2012-02-02 03:59
categories: django python illestrhyme

I developed [IllestRhyme](http://www.illestrhyme.com) using Django, having never touched it before. I chose it because it's Python based, and a quick search showed there were a lot of third-party applications available. In two weeks, I had a fully functional site. The site has come a long way since it launched in the beginning of January (looking at the git commit comments is especially fun), but what let me add features so quickly was the third party apps.

<!--more-->
First off, some best practices. When I began installing applications I did so using pip, which downloads packages (by default) from [PyPi](http://pypi.python.org), the Python Package Index. This seemed reasonable, as I wanted stable versions of packages and an easy way to re-install everything in case of emergency. The packages on PyPI, however, usually trail the main branch of a project, sometimes significantly so. So I went back and removed all of the pip-installed packages and checked everything out from source. 

I can still rebuild everything in an emergency since (a) my entire site is under source control and (b) setting up a Python dependencies file to download the packages I require was a breeze. OK, enough meta-discussion. The real question is, "what applications am I using?" Here's the current list:

* django.contrib.auth
* django.contrib.contenttypes
* django.contrib.sessions
* django.contrib.sites
* django.contrib.messages
* django.contrib.staticfiles
* django.contrib.sitemaps
* south
* django.contrib.admin
* django.contrib.admindocs
* voting
* django.contrib.comments
* basic.inlines
* basic.blog
* basic.groups
* tagging
* django.contrib.markup
* pybb
* pytils
* sorl.thumbnail
* pagination
* postman
* oembed
* analytical
* basic.tools

Those applications gave me, in no particular order: forums, a blog, voting on user defined objects, database migrations, tagging, analytics integration, groups ("Crews" on the site) and group membership work flows, and oEmbeded links. Most required minimal setup. More importantly, they allowed me to quickly deliver features that users wanted while being able to focus on the site's core features, which were written from scratch.

In addition to being well written, most are very well documented, either via an .rst file on GitHub/bitbucket or, even better, a Sphinx generated page on [ReadTheDocs](http://www.readthedocs.org). And the best part about them is they're all open source, so they're eminently malleable if you're doing something a little outside the lines. Since you have the source, it's trivial to fork the code and change it locally, merging bug fixes from the main branch. This is another reason why using the checked out code is superior to PyPI packages: you get bug fixes and features as soon as they're written.

For all of Django's pluses, though, there are some minuses. The framework can be rigid at times, forcing you into a particular way of doing things. Often that's not an issue, but sometimes you want the framework to just "get out of your way" and code closer to the bare metal. Those who are interested in a bit less restrictive frameworks should check out web.py and Pylons. That said, working within the framework (the way it's meant to be used) can lead to a huge productivity increase, as so much is taken care of for you. In the end, it's just Python code, so you almost always have an "out". 

What's interesting with Django is how my development process has matured since starting the site, something I'll go into in a future post. For now, if you have any Django related questions, feel free to hit me up at [jeff@jeffknupp.com](mailto:jeff@jeffknupp.com)... Or do what everyone else does and Google until you find a StackOverflow question that matches yours.
