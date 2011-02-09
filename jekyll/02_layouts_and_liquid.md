!SLIDE

# Layouts #

!SLIDE bullets

* Found in your _layouts directory
* "Partial templates" mimicked by having layouts use other layouts
* Uses liquid for easy templating

!SLIDE code smaller

    @@@ html
    <html>
      <head>
        <title>All About Badgers</title>
      </head>
      <body>
        <h1>All About Badgers</h1>

        {{ content }}

      </body>
    </html>

!SLIDE

# Liquid #

!SLIDE bullets incremental

# Liquid Template Engine #

* Part of Shopify
* [http://www.liquidmarkup.org/](http://www.liquidmarkup.org/)
* Simple, beautiful, non-evaling, secure
* Great for designers

!SLIDE code smaller

    Hello {{name}}

    {% if user %}
      Hello, {{user.name}}
    {% endif %}

    {% for item in array %}
      Found: {{item}}
    {% endfor %}
