After finishing this homework, you should know:

- how to add an external stylesheet to an HTML file
- Text formatting with CSS
  - color, font-family, font-size, font-style, font-weight, vertical-alighn
- how to style a tag (e.g. apply a style to body, h1, p)
- how to style a specific group (class) of tags (e.g. tr.highlight)
- how to style a specific tag identified by ID

# _Write down your answers on a bond paper and submit on Tuesday, August 8_

This homework will take approximately 30-60 minutes. You can test your code on your computer using Visual Studio Code and Edge/Chrome/Firefox. You get +30% credit if you upload your code to Github.com and configure GitHub pages on your project.

# Preliminaries

Extra Credit: Create a new GitHub project named "homework3". Create an HTML file named "index.html". Configure the project to use GitHub Pages.

```
HINT: To setup a new Github project and configure it to use Github Pages, follow https://github.com/JBRC-ph/EmpowermentTechnologies/blob/master/github-pages-howto.md
```

Put the following HTML code into index.html. If you recall this is similar to exercises 1, 2 and 5 of [Homework 2](https://github.com/JBRC-ph/EmpowermentTechnologies/blob/master/Homework2.pdf)

```
<html>
  <body>
    <h1>Title</h1>
    <!-- First paragraph -->
    <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam porta, turpis vitae mollis accumsan, diam lorem imperdiet tellus, at porttitor ipsum nibh eu elit. Donec tempor metus nunc, ac rhoncus enim convallis quis. Morbi nec nunc ultrices, porta diam vel, consequat felis. Morbi sagittis consequat vulputate. Phasellus faucibus iaculis porttitor. Sed maximus mattis sapien ut fringilla. Mauris venenatis efficitur dui nec scelerisque. Aenean id elit et dui aliquet rhoncus. Nam elementum, lectus non varius viverra, tortor nulla tristique nulla, non tristique massa odio efficitur mauris. Ut sollicitudin erat nec interdum maximus. Praesent sodales arcu in massa varius, vehicula molestie eros tempus. Mauris dignissim molestie felis id gravida.
    </p>

    <!-- Second paragraph -->
    <p>
        Morbi ac dui ut lacus laoreet malesuada. Ut tempor lorem ac eros laoreet, sit amet pellentesque dui vehicula. Nunc lacinia ullamcorper nulla nec congue. Sed vel massa at dolor tempus elementum eu et felis. Duis eget condimentum mi. Morbi vehicula erat ac augue convallis rutrum. Donec tempus volutpat pellentesque. Pellentesque bibendum dapibus ex ut convallis. Nunc efficitur orci vel augue aliquam feugiat. Aenean porttitor leo justo, ac accumsan lorem sollicitudin eu. Sed vel ante sed dolor congue placerat. Aliquam nec convallis nibh. Nam a lorem vitae lacus vulputate pretium a nec lorem.
    </p>
    
    <!-- Third paragraph -->
    <p>
        Pellentesque hendrerit vehicula sodales. Aliquam a faucibus mi. Curabitur sed elit eget elit gravida viverra. Sed pulvinar a massa porta lobortis. Sed varius malesuada ante et lacinia. Phasellus et congue lorem. Nam viverra, elit vitae efficitur blandit, ex ex finibus magna, ac aliquam ante elit non sem. Sed in augue scelerisque, ornare magna non, laoreet dolor. Mauris fermentum eros ut eros luctus lobortis. In vel diam pulvinar, aliquam lectus at, pellentesque erat. Sed et urna in erat dapibus rutrum. Donec vitae nisl elementum, pulvinar massa ac, tincidunt ante. Fusce sit amet sem nibh.
    </p>
    
    <!-- Form -->
    <p>
        <form>
        <label>First Name</label>
        <input type="text" name="first_name" />
        <br/>
        <label>Last Name</label>
        <input type="text" name="last_name" />
        <br/>
        <input type="submit" value="Submit" />
        </form>
    </p>

    <!-- Table -->
    <p>
        <table border="1">
        <tr>
            <th>
            Superhero
            </th>  
            <th>
            Civil War
            </th>
            <th>
            Infinity War
            </th>
        </tr>
        <tr>
            <td>
            Captain America
            </td>  
            <td>
            Yes
            </td>
            <td>
            Yes
            </td>
        </tr>
        <tr>
            <td>
            Iron Man
            </td>  
            <td>
            Yes
            </td>
            <td>
            Yes
            </td>
        </tr>
        <tr>
            <td>
            Hulk
            </td>  
            <td>
            No
            </td>
            <td>
            Yes
            </td>
        </tr>      
        </table>
    </p>
  </body>
</html>
```

Save the file and open it on your browser.

# Getting Started with Styling HTML

Add an external stylesheet to the HTML above:

```
  <head>
      <link rel="stylesheet" type="text/css" href="./style.css" />
  </head>
```

_Question 1: Where should you put the code - before or after the <body> tag?_

After adding the external stylesheet, reload index.html on your browser. Do NOT yet create style.css. 

_Question 2: Were there any changes in the layout or look of index.html?_

Change the <body> tag in the HTML to:

```
<body style="background: #A0A0A0;">
```

then reload index.html in the browser. Congratulations! You just added an inline stylesheet.

Reload the page in the browser. What changed?

Remove the style attribute from the body tag:

```
<body>
```

Put the style in style.css:

```
body {
  background: #A0A0A0;
}
```

You've just styled index.html with an external stylesheet.

_Question 3: There are three ways to incorporate CSS into HTML. In this exercise, you did two: (1) use inline styling, and (2) use an external stylesheet. What is the third way?_

# HTML Colors

Change the background color to #B0C4DE.

_Question 4: What is the HTML color name for #B0C4DE?_

_Question 5: In #B0C4DE, which two characters stand for the red component of the RGB color? Which two characters stand for green? For blue?_

_Question 6: As the background color values for red, green and blue approach FF, what happens to the color - does it become lighter or darker? As the color values approach 00, does the color become ligher or darker?_

Modify style.css to change the background color back to white.

# CSS Class Selectors

In the previous sections you learned how to add a style to all instances of an HTML tag by adding a `background` style to the `body` tag. There is only one `body` tag in the HTML document, but the same principle applies to other HTML tags like `p`.

Add the following to `style.css` to change the text font in index.html:

```
p {
  font-family: sans-serif;
}
```

Save `style.css` and reload `index.html` in the browser.

_Question 7: What changed in the page?_

Change `index.html` and `style.css` so that only the three Lorem Ipsum paragraphs get the sans-serif font styling. These are the <p> tags preceded by the HTML comments "First paragraph", "Second paragraph", and "Third paragraph".

_Question 8: Write down the new HTML code for the first three <p> tags._

_Question 9: Write down the new CSS code for `style.css`_

```
HINT: Read about CSS Class Selectors: https://www.w3schools.com/cssref/sel_class.asp
```

Following the same principles, modify your code to highlight the row for Captain America with a gray background.

_Question 10: Write down the new HTML code for the Captain America `<tr>` block_:

```
        <tr>
            <td>
            Captain America
            </td>  
            <td>
            Yes
            </td>
            <td>
            Yes
            </td>
        </tr>
```

_Question 11: Write down the new CSS code for `style.css`._

# CSS ID Selectors

If you want to style one specific HTML tag, put an ID attribute on the tag and apply a CSS selector for that ID.

```
HINT: Read about CSS ID Selectors: https://www.w3schools.com/cssref/sel_id.asp
```

_Question 12: Write down the HTML and CSS changes needed to change the color of the second paragraph to green._

_Question 13 (Extra Credit, +30%): If you haven't yet done so, create a new GitHub project named homework3, configure GitHub Pages on the project, and upload your HTML and CSS into the project. You get the full +30% if http://yourusername.github.io/homework3 renders correctly on a browser._

You're done. Congratulations! 
