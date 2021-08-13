# DOM Editing Lab

## Learning Goals

1. Identify that DOM nodes are written as HTML

## Introduction

We've started looking at the DOM and its structure. Now it's time to see what we
can do with it.

### Identify That DOM Nodes Are Written As HTML

![Syntax](https://media.giphy.com/media/3o6MbkZSYy4mI3gLYc/giphy.gif)

When viewing the DOM (through DevTools' **Elements** tab) we see HTML that is a
clone of the HTML found in the source HTML file. DOM nodes represent all
components that make up a web page.

DOM nodes most often have a starting tag and an ending tag. Because of this,
something else could nest inside. This inner node is called a child node.
The outer node is called a parent node.

An example of a normal tag is a paragraph:

```html
<p>I am a paragraph.</p>
```

Another normal tag is a main section:

```html
<main></main>
```

To nest items in a normal tag, we simply add the child node HTML element
content between its parent's starting and ending tags:

```html
<body>
  <main>
    <p>I am a nested paragraph, inside the main element, inside the body!</p>
  </main>
</body>
```

Some nodes only have a starting tag. Those are called self-closing elements.
These elements do not have any content nested inside of them. More technically,
they are called void elements. Void elements cannot be parent nodes.

An example of a self-closing tag is an image:

```html
<img
  src="https://media.giphy.com/media/3o6MbkZSYy4mI3gLYc/giphy.gif"
  alt="A policeman"
/>
```

In self-closing tags, the trailing `/` is optional. This is valid too:

```html
<img
  src="https://media.giphy.com/media/3o6MbkZSYy4mI3gLYc/giphy.gif"
  alt="A policeman"
/>
```

Every HTML element has a `display` value. Since these are known by modern
browsers, you don't have to worry about specifying the value unless you want to
change it. This value can be many things (including `none`, which hides the
elements), but the default value for most elements is either
[`block`][html-block-elements] or [`inline`][html-inline-elements]. For the
images above, the value is `inline`.

## Instructions

Enough chit-chat, let's write some HTML!

First, we need a way to view the results of our HTML in a browser.

If you're working on your own machine, from the terminal in the directory you're
working in, run `open index.html` to open up a copy of the file in your browser. Or, run `explorer.exe index.html` if you are using a WSL/Ubuntu local environment.

If you are working in the in-browser IDE, type `httpserver` from the console to
start up a temporary web server, and copy the URL provided into the browser's URL
bar to view `index.html`.

Just to speed things up a bit, paste the following code into `index.html`:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Introduction to the DOM Lab</title>
  </head>
  <body>
    <!--All our work for this lesson will go here-->
  </body>
</html>
```

Refresh the page to see the changes.

Open the Google Developer Tools. Click on the "Elements" tab. Here we have the
DOM representation of the HTML source the browser loaded. Use the "Elements"
window to see that the `body` node is, temporarily, child-less.

First, let's add a title to our page:

```html
<h1>My HTML adventure</h1>
```

Refresh the page and view the Elements tab again. You should see that a new
child-node has appeared underneath `body`. You can use the
[disclosure triangle](https://en.wikipedia.org/wiki/Disclosure_widget) to see
which children are wrapped or nested within the `body` tag.

![Image of Recommendation](https://curriculum-content.s3.amazonaws.com/phase-1/dom-editing-lab/disclosure-triangle.png)

Next, we'll add a paragraph below the title. We'll also add some highlighted
bits of text to the paragraph to make it stand out a little.

```html
<p>
  We're writing HTML markup to display in our <strong>browser</strong>. We're
  basically telling computers what to do. <em>Neat!</em>
</p>
```

Save the file and check out the page in the 'Elements' tab. What's happening
above is that we added some inline elements, `<strong>` and `<em>` to our
paragraph to style things a little. The `<strong>` tag makes any text within
look **important**. It's usually bold in browsers by default. The `<em>` tag
allows us to _emphasize_ certain text. This text is typically rendered as
italic in browsers.

Let's add a link to MDN to define HTML. We'll use the`<a>` tag for this. Add
this to our existing `<p>`:

```html
We're writing
<a href="https://developer.mozilla.org/en-US/docs/Web/HTML">HTML</a> markup to
display in our <strong>browser</strong>.
```

Notice that HTML attributes are shown alongside their opening tag e.g. the
`href` attribute.

Lastly, we'll add a table below the paragraph to recap some of the stuff in
this lesson:

```html
<table>
  <thead>
    <tr>
      <th>Element name</th>
      <th>Display value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>h1</td>
      <td>block</td>
    </tr>
    <tr>
      <td>p</td>
      <td>block</td>
    </tr>
    <tr>
      <td>strong</td>
      <td>inline</td>
    </tr>
    <tr>
      <td>em</td>
      <td>inline</td>
    </tr>
  </tbody>
</table>
```

Woah. That's a **lot** of markup! If you take a look at the result though,
you'll see that it's a fairly complex visual — it's a table! Our table consists
of a header and a body. The header allows us to give the columns a name, and
the table body contains the rows of content. Both `<thead>` and `<tbody>` tags
contains rows, which are represented as `<tr>` (table row). These rows then
contain columns (or cells). In the `<thead>` row, cells are represented as
`<th>`, while cells in `<tbody>` have their content in `<td>` tags.

That's a _lot_ of nesting.

Look again at the Elements tab. Expand out all the children of the `table`.
This is the DOM tree!

## Saving Your Work Remotely

Currently, the work you've done on this assignment is only on your local
machine. To preserve your solution on your GitHub fork, you will need to stage the
changes you've made, commit them, and push the commit up to GitHub. Use
the following commands to do this:

```sh
git add .
git commit -m "Completed assignment"
git push
```

If you visit your fork on GitHub, you should now see that _you've_ made the most
recent commit, and your code will be present in the files.

## Conclusion

We reviewed DOM nodes and their HTML sources, and we reviewed how the DOM is
structured. We also looked at block and inline elements and their behaviors.
Finally, we practiced working directly with the DOM.

## Resources

- [HTML Block Elements][html-block-elements]
- [HTML Inline Elements][html-inline-elements]

[html-block-elements]: https://developer.mozilla.org/en/docs/Web/HTML/Block-level_elements
[html-inline-elements]: https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements
