!SLIDE

# Jekyll #

!SLIDE code

# Installation #

    $ gem install jekyll

!SLIDE code

# The Common Layout #

    |-- _config.yml
    |-- _layouts
    |   |-- default.html
    |   `-- post.html
    |-- _posts
    |   |-- 2011-01-29-first-post.textile
    |   `-- 2011-02-10-jekyll-rules.markdown
    |-- _site
    `-- index.html

!SLIDE bullets incremental

# Blog feature: Posts #

* Posts are flat text files in the *_posts* directory
* Format is: YYYY-MM-DD-title-of-the-post.FORMAT
* Can use: Markdown, Textitle, HTML, or define your own
* Metadata is set by YAML front-matter

!SLIDE code

# Sample Markdown Post

    ---
    layout: post
    title: Like a boss
    ---
    This post is brought to you 
    by the power of love.

!SLIDE full-explanation

Any jekyll-recognized file \(i.e. .html, .markdown, .textile\) in your
project will be parsed by jekyll if it contains the YAML front-matter.

!SLIDE bullets incremental

# Other Features #

* Comments: Disqus
* Categories: YAML front-matter
* Tags: See http://www.justkez.com/generating-a-tag-cloud-in-jekyll
* Syndication?

!SLIDE bullets

# Syndication #

* Generate your own Atom/RSS feed
* Create an xml file and use Liquid to loop over the posts
* For example, Geek Writer's feed/index.xml file:

!SLIDE code smaller

    @@@ xml
    ---
    layout: nil
    ---
    <?xml version="1.0" encoding="utf-8"?>
    <feed xmlns="http://www.w3.org/2005/Atom">
      
      <title>Geek Writers</title>
      <link href="http://www.geekwriters.net/feed/" rel="self" />
      <link href="http://www.geekwriters.net/" />
      <updated>{{ site.time | date_to_xmlschema }}</updated>
      <id>http://www.geekwriters.net/</id>
      <author>
        <name>Tim Gourley</name>
        <email>tgourley@gmail.com</email>
      </author>
      
      {% for post in site.posts %}
      <entry>
        <title>{{ post.title }}</title>
        <link href="http://www.geekwriters.net{{ post.url }}" />
        <updated>{{ post.date | date_to_xmlschema }}</updated>
        <id>http://www.geekwriters.net{{ post.id }}</id>
        <content type="html">{{ post.content | xml_escape }}</content>
      </entry>
      {% endfor %}
      
    </feed>
