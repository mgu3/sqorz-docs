## About

The documentation for the Sqorz system is maintained in [Markdown](https://en.wikipedia.org/wiki/Markdown). 
Markdown is a very simple language
that can be used to generate nice looking HTML for use as a static website for documentation.

HTML is very powerful but can be fiddly to write. Using Markdown achieves the same output but allows
you to focus on the content rather than the presentation.

### Markdown Example

=== "Markdown"

    ```markdown
    
    ## Big News!
    
    - Easy to write
    - Easy to maintain
    
    ![sqorz.png](../sqorz.png)
    
    ```

=== "HTML"

    ```html
    
        <div class="tabbed-block">
        <h2 id="big-news">Big News!</h2>
        <ul>
        <li>Easy to write</li>
        <li>Easy to maintain</li>
        </ul>
        <p><a class="glightbox" href="../../sqorz.png" data-type="image" data-width="auto" data-height="auto" data-desc-position="bottom"><img alt="sqorz.png" src="../../sqorz.png"></a></p>
        </div>
    
    ```

=== "Appearance"

    \## Big News!
    
    - Easy to write
      - Easy to maintain
    
    ![sqorz.png](../sqorz.png)

There are lots of references for Markdown(e.g. 
[https://www.markdownguide.org/cheat-sheet/](https://www.markdownguide.org/cheat-sheet/), 
but we will also cover the basics that you need further down on
this page.

As well as Markdown we use [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/). This 
is a Python wrapper for Markdown and gives us
some nice styles and some useful add-ons such as support for tags.

## Set Up

In order to make changes to the documentation, you first need to set a few things up.

### Python

If you don't already have Python installed on your computer then you can install it 
from [https://www.python.org/downloads/](https://www.python.org/downloads/). Some things don't work well on earlier
versions of Python. Python 3.12 was used to build this.

It is recommended, but not essential, that you use a virtual environment which separates the Python packages
needed for the Sqorz documentation from any other Python activity on your computer.

Open a command prompt (Terminal on a Mac or cmd on Windows).

Check that Python is installed.

```commandline

python -V
Python 3.12.3

```

Now create a new directory for your work:

```commandline

mkdir sqorz-docs
cd sqorz-docs

```

If you want to use a virtual environment, then also run:

=== "Mac"

    ```commandline
    
    python -m venv myenv
    . ./myenv/bin/activate
    
    ```

=== "Windows"

    ```commandline
    
    python -m venv myenv
    . .\myenv\bin\activate
    
    ```

### Source Code

!!!Move this Later
    This should be moved to a new location.

The documentation lives in Github. You can access it 
at [https://github.com/mgu3/sqorz-docs](https://github.com/mgu3/sqorz-docs).

```commandline
mkdir docs
cd docs
git init
git remote add origin https://github.com/mgu3/sqorz-docs
git pull origin main

```

### Material for MkDocs

```commandline

pip install -r requirements.txt

```

### Local Web Server

You can start a local web server to help you while editing the documentation:

```commandline

mkdocs serve

```

Now you can open a browser to view your documentation at [http://127.0.0.1:8000/](http://127.0.0.1:8000/)

### Changing Documentation

The documentation is in text files so you can use any text editor to make changes. The changes will immediately
be updated by the local web server (including any pages you already have open).

### Publishing Documentation

!!!Move Later

    This should be moved to a proper location.

You can publish the documentation:

```commandline

./publish

```

## Documentation Structure

### General Approach

We use the ??? approach of classifying documents into four categories:

- Tutorials
- How Tos
- Discussion
- Reference

You will find the document structure has these as directory names.

### Lower Level

Each page consists of a single file in Markdown format which has the extension `.md`.

Many pages also have images. These can be found in a directory in the same location
as the Markdown file with the same name but with `-assets` on the end.