# Seatwork 1

At the end of this exercise, you should learn: 

- How to design the typical header and footer of a web page
- How to use the following CSS properties:
  - margin
  - padding
  - list-style-none
  - float
  - display
  - text-decoration
  - background-color
- How to use the following CSS selectors:
  - hover
  
### Step 0. Plan ahead.

You will spend the last 10 minutes of the class writing your reflection about this activity. Plan to finish coding at 7:50 AM.

### Step 1. Fork the boilerplate project 

To get up to speed quickly, we'll start with a boilerplate HTML. Feel free to replace this with your own content if you prefer (and have the time). 

Log in to Github, open this repository: https://github.com/JBRC-ph/css-seatwork-1, and click the Fork link at the upper right portion of the page.

NOTE: You can work by directly editing the HTML and CSS file from Github.com. However, changes on your code can take a few minutes to propagate to Github Pages. I recommend cloning the repository locally and edit the web page using Visual Studio Code. After each CSS change, reload index.html in your browser to see how the CSS change affects the layout of the page.

### Step 2. Enable Github Pages for the project

This will let you open the HTML code in your browser as a web page, and not just as HTML code. For instructions on how to do this, see https://github.com/JBRC-ph/EmpowermentTechnologies/blob/master/github-pages-howto.md#5-enable-github-pages-for-the-project

### Step 3. Remove the bullet points for the header items

Create style.css and add this code:

```
header ul {
  list-style-type: none;
}
```

The `list-style-type` property is used to configure the bullets in a `<ul>`.

### Step 4. Layout the header items horizontally

Add this to style.css:

```
header li {
  float: left;
}
```

_What happens if you use `float: right`?_

You'll notice that after adding this style, the `What is Lorem Ipsum` title is now next to our menu. Let's fix that. Add the `overflow`  property to `header ul`:

```
header ul {
  list-style-type: none;
  overflow: hidden;
}
```

### Step 5. Add spacing between the header items

Add this to `style.css`:

```
header li a {
  padding: 14px;
}
```

### Step 6. Modify the header to use a gray background and white text

Add this property to `header ul`:

```
  background-color: gray;
```

And add this property to `header li a`:

```
  color: white;
```

### Step 7. Change the default link styling for the header links

Add this property to `header li a`:

```
  text-decoration: none;
```

### Step 8. Add a hover effect to the header items

Add a new CSS selector to specify what `header li a` links should look like when the mouse is over it:

```
header li a:hover {
  background-color: green;
}
```

### Step 9. Style the footer

Give the footer a gray background and white text just like the header:

```
footer {
  background-color: gray;
  color: white;
}
```

### Step 10. Set margins.

Finally, set a zero margin for the header and footer, while setting a different margin for the body.

Add these to `style.css`:

```
body {
  margin: 0;
}

#body {
  margin: 10px;
}
```

And put everything inside `<body>` in a `<div id="body">` tag.

### Step 11. Upload to Github.

If you worked locally, upload your work to Github and view your work in https://yourusername.github.io/css-seatwork-1/index.html

Write your reflection.

Congratulations, you're done!

Further study: Read about the CSS properties you used today (e.g. Google "css float mdn" or "css float w3schools"):
  - margin
  - padding
  - list-style-none
  - float
  - display
  - text-decoration
  - background-color
  - hover

