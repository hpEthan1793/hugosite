---
title: "Html Intro"
date: 2021-02-27T20:21:52+02:00
draft: false
toc: false
images:
tags:
  - html
  - webdev
---

## What is HTML5

Hyper-Text-Markup-Language is a markup language that is used for creating websites and web documents. It contains elements that can tell a specific browser how to display certain content such as images, text, shapes or logos. An HTML document has a certain structure with certain elements describing what the browser should display.

## How can I write HTML code?

You can write HTML is pretty much any sort of text editor such as Notepad on Windows, or a IDE such as Atom or Sublime, or on linux you can use Nano, Vim or Emacs. The list goes on and on and pretty much comes down to personal preference.<br>(Keep and eye out my upcoming post about different IDE's and text editors coming soon.)

Below is an example of a basic HTML5 template and an explanation of what each element does.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>This is the Title of the WebPage</title>
  </head>
  <body>
    <h1>This is a big heading</h1>
    <p>This is a paragraph</p>
  </body>
</html>
```

<table class="table table-dark table-responsive">
  <thead>
    <tr>
      <th scope="col">Element</th>
      <th scope="col">Definiton</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>!DOCTYPE html</td>
      <td>Means that we are defining that this document is a HTML5 document</td>
    </tr>
    <tr>
      <td>&lt;html&gt;</td>
      <td>The beginning of the HTML page</td>
    </tr>
    <tr>
      <td>&lt;head&gt;</td>
      <td>All the meta data and information about the webpage such as the Title, Author or a Descripton</td>
    </tr>
    <tr>
      <td>&lt;title&gt;</td>
      <td>Tells the browser what name to display as the title for the webpage</td>
    </tr>
    <tr>
      <td>&lt;body&gt;</td>
      <td>The main body section of the webpage where all the content will go</td>
    </tr>
    <tr>
      <td>&lt;h1&gt;</td>
      <td>Type of heading, H1 being the largest and H6 the smallest</td>
    </tr>
    <tr>
      <td>&lt;p&gt;</td>
      <td>Paragraph tag. Defines a paragraph or section of text</td>
    </tr>
  </tbody>
</table>

## Important note about closing off HTML tags

Whenever you use a HTML tag, it is important to close it off by putting in a </>. This tells the browser that it is the end of the tag we used. Below are examples of closing off HTML tags.

```html
<p>I closed off the p tag</p>
<h1>I closed off the h5 tag</h1>
<b>I closed off the bold tag</b>
<i>I closed off the Italics tag</i>
<--! The List goes on and on --!>
```

## Here are some of the basic elements used in HTML5

### The heading (h) tag

The heading tag goes from h1-h6. Below is an example of the different heading sizes. The bigger the heading the smaller it actually is (h1 being the largest heading).

<h1>h1</h1>
<h2>h2</h2>
<h3>h3</h3>
<h4>h4</h4>
<h5>h5</h5>
<h6>h6</h6>

### The paragraph (p) tag

The paragraph tag is used to define a certain piece of text as a paragraph. Below is an example.

```html
<p>This is a paragraph.</p>
```

#### Output:

<p> This is a paragraph.</p>

### How to make text bold

To make text bold, use the b tag. Example below.

```html
<p>I want to make this <b>bold</b></p>
```

#### Output:

<p>I want to make this <b>bold</b></p>

### How to make text italic

To make a piece of text italic, use the i tag. Example below.

```html
<p>I want this to be <i>Italic</i></p>
```

#### Output:

<p>I want this to be <i>Italic</i></p>

### How to change the colour of text

To change the colour of a piece of text, use the color tag. Example below.

```html
<p>I want this to be <font color="red">red</font></p>
```

#### Output:

<p> I want this to be <font color="red">red</font></p>

You can also change the entire paragraph colour by using an attribute. Example below.

```html
<p style="color: blue">This sentence is blue</p>
<p style="color: red">This sentence is red</p>
<p style="color: yellow">This sentence is yellow</p>
```

#### Output:

<p style="color: blue">This sentence is blue</p>
<p style="color: red">This sentence is red</p>
<p style="color: yellow">This sentence is yellow</p>

### The link (a) tag

The link tag is specified by a href attribute. An attribute is used to describe information about an HTML element. Below is an example of a link.

```html
<a href="https://google.com">Click me to go to Google.com</a>
```

#### Output:

<a href="https://google.com">Click me to go to Google.com</a>

## Combining everything we have learnt into one

```html
<!DOCTYPE html>
<html>
  <head>
    <title>This is the Title of the WebPage</title>
  </head>
  <body>
    <h1>This is a big heading</h1>
    <h2>This is a smaller heading</h2>
    <p>This is a paragraph</p>
    <p style="color: red">
      This is a red sentence with <b>bold</b> and <i>Italic</i> words.
      <a href="https://ethansmegawebsite.co.za"
        >Here is a link to a place where you can find tutorials like this one</a
      >
    </p>

    <p>Below is an image of Rio</p>
    <img src="https://www.imagesource.com/wp-content/uploads/2019/06/Rio.jpg" />
    <p>Below is a smaller image of Rio</p>
  </body>
</html>
```

## Conclusion:

So that about wraps up the basics of HTML5. In one of my next posts I will be going over the basics of CSS3 and how you can use it style your HTML and make it look a bit more "stylish".
