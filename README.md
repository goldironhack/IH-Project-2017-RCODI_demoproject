## Demoproject 1 — HTML Content styled with CSS

### Steps

#### Getting content in the page

 1. We copied generated content from https://jaspervdj.be/lorem-markdownum/
 2. We pasted the content in the HTML file (in the element having `class="container"`.
 
    `class="container"` tells us that the element should contain some elements (in our case some text)
    
    `<!DOCTYPE html>` is a declarative line telling the browser we are loading a piece of HTML. Most browser work even without this line.
    
    Here we used the following tags:
    
     - `<html>`—The root element (second and last lines)
     - `<head>`—A special element which contains some elements setting up the page properties (e.g. the `<title>` which sets the title)
     
        `<meta charset="UTF-8">` sets up the encoding of the content (UTF-8) which allows us to use a wider range of characters.
        Without this tag, some browsers would display strange characters if we would use them.
        
     - `<body>`—Which holds the *visible* part of the page.
     - `<div>`—Used to group elements together.
     — `<h1>`, `<h2>`, ..., `<h7>`—Headings (titles)
     — `<p>`—Paragraphs
     — `<strong>`—Bold text
     — `<em>`—Italic text

#### Styling

Using the `<link>` tag we can load the CSS files. Those CSS files are used for styling the page.
The browser does provide some default CSS for our elements (e.g. bigger font size for the headings, and smaller for the paragraphs etc), but if we want to change the color of a specific title, we want to use CSS for that.

The following line of code, put in the `<head>` element will tell the browser (e.g. Google Chrome) to load `style.css` and to interpret it as a stylesheet.

```html
<link rel="stylesheet" href="style.css">
```
 
Once the browser loads and interpret the styles from our file, it will know how to *paint* the page (e.g. making our title red).
 
#### Selectors
In CSS, the syntax looks like this:

```css
/* This is a comment */
selector {
    property: value;
}
```

The `selector` will *select* the HTML elements you want to style. It will take different forms:

 - `tag` if we want to select a `<tag>` (e.g. `h1 {...}` to select all the headings 1)
 - `.myClass` if we want to select all the elements having `class="myClass"`
 - `#myId` if we want to select the element having `id="myId"`

`property: value` is the way we style those elements. You will find the property names and the values they accept by searching on the internet, but here a couple of them:

```css
.myAwesomeElementClass {
    /* Make the text color red */
    color: red;
    
    /* ...width black background */
    background: black;
    
    /* Set the text font-size */
    font-size: 14px;
}
```

#### Fonts

Some fonts come with the operating system. But we cannot assume that all people have the font *we* want.
Also, it happens that the default fonts from the browsers are often very minimal and quite ugly.

[Google Fonts](https://fonts.google.com/) helps us in choosing among hundreds of fonts free to use.

In this example we will use two fonts: one for the headings, and another for the paragraphs.
From this point you can be creative. 

  1. For the headings, let's say we want a thick one: https://fonts.google.com/?thickness=7
  
     For the sake of example, we will choose [`Rye`](https://fonts.google.com/specimen/Rye).
     Click `Select this font`.
     
  2. In the left side, you will see some other font suggestions. We will choose *Raleway* for the paragraphs, by clicking the `+` button.
  
  3. In the right bottom side, you click the small bar and a widget will appear providing the HTML and CSS to load and use those fonts:
  
    Let's put the following line in our `<head>` element (this will load the fonts):
    
     ```html
     <link href="https://fonts.googleapis.com/css?family=Raleway|Rye" rel="stylesheet">
     ```
  
  4. Then, in the `style.css` file we set up the minimal code to use them:
  
     ```css
     body {
        /* The general font */
        font-family: 'Raleway', sans-serif;
     }
     h1, h2, h3, h4, h5 {
        font-family: 'Rye', cursive;
     }
     ```
     
Once we did that, the fonts are on the page and we have a bunch of text displayed with fancy fonts.

#### Colors

Let's make the headings red. We will use [Flat UI Colors](http://flatuicolors.com/) to get a *nice* red: `#c0392b`.

We need to add `color: #c0392b;` in the place where we set the styles for the headings.

### Images

Let's add an image. We will use images from the internet. `imgur.com` is a site which can store your own images without authentication if you want to upload one from your computer.

```html
<img src="the url of the image" />
```

It's very common to restrict the width of the `<img>` tag:

```css
img {
    /* Don't allow images to be wider than the page */
    max-width: 100%;
}
```