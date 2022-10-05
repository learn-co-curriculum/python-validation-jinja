# Jinja Templates

## Learning Goals

- Learn about Jinja templates.
- Learn how to use Jinja variables, loops and conditionals.

***

## Key Vocab

- **HTML**: The HyperText Markup Language or HTML is the standard markup language for documents designed to be displayed in a web browser.
- **Validation**: Validation is an automatic check to ensure that data entered is sensible and feasible.
- **Form**: An HTML form is used to collect user input. The user input is most often sent to a server for processing.

***

## Introduction

A Jinja template contains variables and expressions which can be replaced values
when the template is rendered. A Jinja template file is a file that does not have a particular extension. We want to infuse the template with html therefore we will use the `.html` file extension. Jinja can work with other extensions such as XML.

Here is an example of a Jinja template

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Webpage</title>
</head>
<body>
    <ul id="navigation">
    {% for item in navigation %}
        <li><a href="{{ item.href }}">{{ item.caption }}</a></li>
    {% endfor %}
    </ul>

    <h1>My Webpage</h1>
    {{ a_variable }}

    {# a comment #}
</body>
</html>
```

There are a few kinds of delimiters. The default Jinja delimiters are:

- {% ... %} for Statements
- {{ ... }} for Expressions to print to the template output
- {# ... #} for Comments not included in the template output

***

## Variables

We can pass Python objects into Jinja templates, these objects can be referred to inside of the template
using the Jinja syntax we saw in the previous example.

Here is an example of how we would render a template in Flask

```py
return render_template("index.html", obj = some_object)
```

We can use the `{{ obj }}` in the jinja template to access the `obj` variable.

***

## Loops

An example of a for loop. You have to use the `{% endfor %}` to end the for loop

```html
{% for val in some_list %}
    ...
{% endfor %}
```

***

## Conditionals

An example of an if statement. You have to use the `{% endif %}` to end the for loop

```html
{% if true %}
{% endif %}
```

Here is an example of a more complex conditional.

```html
{% if ... %}
{% elif ... %}
{% else %}
{% endif %}
```

## Conclusion

Now that we know the basics of Jinja, we will use these templates in the following lesson to
create dynamic forms with Flask and FLASK-WTF.

***

## Resources

- [Jinja template](https://jinja.palletsprojects.com/en/3.1.x/templates/)
