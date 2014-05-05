Web Fundamentals
================

Web Fundamentals is a technical documentation center for multi-device web
development.  Our goal is to build a resource for modern web developers
that’s as curated and thorough as developer.android.com or iOS Dev Center.

View the live site: https://developers.google.com/web/fundamentals/


Release status
--------------

The project was initiated in late March and soft launched to the public on
April 30th.  We're planning for a more polished 1.0 release in June.

Technology
----------

This is a Jekyll build.

```
/src
  /appengine - the server to host the static content
  /site - the documentation
    /getting-started - the getting started articles
    /multi-device-layouts - responsive design guide
    /introduction-to-media - the guide to using media
    /optimizing-performance - the perf articles
    /using-touch - managing touch
    /showcase - the case-studies
```

`/build` is never checked in but generated by Jekyll.

Installing Dependencies
=======================

Mac
---

1. Install [XCode Command Line Tools](https://developer.apple.com/xcode/downloads/)
1. Install [RVM](https://rvm.io/rubies/default)
    * `curl -sSL https://get.rvm.io | bash`
1. Set RVM Default to 2.0.0
    * `rvm install ruby-2.0.0-p451`
    * `rvm --default use 2.0.0`
1. Install [Pygments](http://pygments.org/)
    * `easy_install pygments`
1. Install [Kramdown](http://kramdown.gettalong.org/)
    * `gem install kramdown`
1. Install [Jekyll](http://jekyllrb.com/)
    * `gem install jekyll`


Using project-level meta data
=============================

The table of contents is generated from `src/site/_project.yaml`

To parse the `_project.yaml` file, include `{% injectdata content _project.yaml %}` in the page. You then have access to the variables in the page object.


Generating Table of Contents
----------------------------

The table of contents is generated from `src/site/_book.yaml`

To parse the `_book.yaml` include `{% injectdata content _book.yaml %}` in the page and then iterate as follows:

     {% for section in page.content.toc %}
        SOME MARKUP
     {% endfor %}

Jekyll Special elements
-----------------------

Code import:

    {% highlight javascript %} {% include sample1.js %} {% endhighlight %}

`{{ articles _category_}}` a list of articles in divs, ordered by the "order" preamble.
`{{ showcases _category_}}` a list of showcases
