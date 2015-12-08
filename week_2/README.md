#Day 2 of FEWD 39!

##Today's Objectives

By the end of this lesson, you will be able to:

- Identify the syntax of CSS. 
- Link your CSS to your HTML. 
- Demonstrate ability to build an HTML document with a linked stylesheet. 

##Using CSS with HTML
- There are three main ways to use CSS - inline styles, the style tag in the head(internal), and a separate .css file that is linked to the HTML.
- Linking a stylesheet to the HTML document is the best-practice way to use CSS styles.
- Here is the syntax for the link tag:

` <link rel="stylesheet" href="style.css" /> `

##CSS Breakdown
- Each CSS style set starts with a selector.
- Selectors allow you to identify which elements you want to apply styles to.
- Here is an example of a selector with a couple rules:

```
p {
    color: red;
    font-weight: bold;
    background-color: blue;
}

```
- This example selects all paragraph tags on the page and applies the below styles to them.

##CSS Colors
- Colors in CSS can be defined in a few different ways.
- The first we have already seen - calling them out by their name semantically (red, green, blue, etc.)
- The second way is by using HEX colors. HEX codes represent shades of red, green, and blue.

![HEX Colors](img/hex_colors.png)


- You can find color codes on a number of websites and other programs like Photoshop. [Colorpicker.com](http://www.colorpicker.com/) is a good example.
- Another way of defining CSS colors is via `rgba()`. Rgba accepts values for red, green, and blue as well as an alpha value for transparency.
- Each RGB value is from 0 to 255. Alpha values are from 0 to 1.

##CSS Selectors
- There are three common basic selectors in CSS.
- The first is the element selector. This is not a very specific selector:

```
div {
	color: red;
}

table {
	color: red;
}

p {
	color: red;
}
```

- The second is the id selector. By convention id's should not be used more than once per page:

```
#my-div {
	background-color: #990000;
}
```

- The third is the class selector. Classes by convention can be used multiple times throughout the page:

```
.my-divs {
	background-color: #EBEBEB;
}
```


##CSS Review
- Where should CSS styles go?
- How does the CSS syntax work?
- What is the difference between an id and a class?


##About Me Lab
- We will now work on adding CSS to the about me page built for homework.

![Betty White Resume](img/WendyBite_AboutMe.png)

- Once you complete this, work on creating this page below. Link the about me page to the resume page. 

![Wendy G. Bite Resume](img/WendyBite_Resume.png)

##Floats
- Floating elements allows us to create a nearly unlimited number of layouts using all types of block elements.
- Floating an element essentially removes it from the standard "flow" and places it to the left or right side of its container.
- Elements can have fixed width, which will wrap underneath each other if the container is smaller than the combined widths.
- You can also used percentage width, which will have the columns respond to the screen size.
- You can tell already that the calculations can get out of hand really fast...

##Element Alignment
- To determine how we can align an element we have to first know what kind of element it is.
- Inline elements can be aligned as text, so with the `text-align` CSS property.
- Block elements can be aligned using the space around them - margin. A margin set to auto for both left and right will center the element in a container.

##The Grid Layout
- Most modern layouts operate on a standard 12-column grid system.
- If you break down any of the websites you know and love you will notice many variations on the 12 column grid.
- Each column in the grid can contain nested grids itself.
- If you want a larger box, you need to have a greater column offset.
- Here is a good pictorial to help you break it down:

![Grid Pictorial](img/grid.jpg)

##Group Exercise
- In groups of two, look up one website of your choice.
- Think about the layout they chose in terms of the grid system.
- Write down which column "offsets" were likely used, and where nested grids may be present.
- Review the mockup of the fashion blog located [here](img/fashion_blog_2.png) and do the same thing.

##Code-Along: Let's Create Our Own Grid
- We will create a 2, 4, and 6 column grid.
- We will try nesting a grid inside another grid.


##CSS Positioning
- There are four main types of positioning that you will see most often - static, relative, absolute, and fixed.
- Static positioning is what all elements have by default. 
- Relative and absolute work together - elements can be positioned absolutely relative to their container.
- Fixed position elements are essentially absolute relative to the window no matter where they are in the DOM. A.K.A. the window is always the relative parent.

##Positioning Exercise
- Try to replicate the following mockups using what we've talked about in this class so far.
- Utilize margins, padding, floats, positioning, etc.

1. Stackers!

![Stackers!](img/stackers.png)

2. The Mirror

![The Mirror](img/the_mirror.png)

3. The Skinny

![The Skinny](img/the_skinny.png)

4. The Absolute

![The Absolute](img/the_absolute.png)

##In-Class Lab / Homework
- For homework you will be creating the fashion blog using your knowledge of layouts.
- The mockup of what you will be creating can be found [here](img/fashion_blog_2.png).
- Bonus: Implement your own grid system to use in layout.
- Extra Reading: Have a look through the documentation for popular frontend frameworks such as Twitter Bootstrap or Zurb Foundation. Pay attention to how they implement the grid system.
	- [Twitter Bootstrap](http://getbootstrap.com/)
	- [Zurb Foundation](http://foundation.zurb.com/)