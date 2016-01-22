#Day 6 of FEWD39
=============
#Introduction to Objects and DOM Manipulation

##Today's Objectives:
**By the end of this lesson, you will:**
* Understand what are Javascript Objects
* Understand how to manipulate the DOM 
* Understand how Javascript makes a dynamic website


###Quick Review of Javascript ####JS Language rules: 	* lines end with a semicolon ; * some words are reserve words (ie: var, return, for )
####Variables
* What are variables?  
* variables should be “camelCase” 
* examples of variable names (can't start with a number)
* names must begin with a letter (can also start with $ and _ ) and are case sensitive
* reserved words (like JavaScript keywords) cannot be used as names####Functions * How do we define a function?
* How do we call a function? 
* What are parameters, arguments, return?
* Examples of built in functions (ex: alert, prompt, parseInt)### Quick Review of Javascript Console and Homework
####Javascript Console
* What is it for? 
[https://developer.chrome.com/devtools/docs/console](http://)

#### Students: demo homework solutions#### In-Class Lab #1: Formulas/Functions 
__Given:__

* You'll see an index.html file. That's where your code will go. There's actually a place at the bottom that shows you exactly where to put your code.

__Assignment:__

* Your task is to write four functions that will make three calculators work:
	* Celcius to fahrenheit: celcius * (9/5) + 32
	* Fahrenheit to celcius: (fahrenheit - 32) * 5/9
	* Radius to circumference: 2 * Math.PI * radius
	* Pythagorean theorem: Math.sqrt((a * a) + (b * b))
	
* You have to use your developer tools to complete this assignment.
* The four functions you're writing can't just be called anything. They must be "called" certain things. 
* __*hint:__ In which file are your FOUR new functions that you are creating being called from?
* When declaring these functions, be sure to include the appropriate parameters. That's what you need to figure out.

	* They also must each return a number.

	* Once they return the right number, you'll see that number appear in the interface (we practiced seeing things in your console, but when done correctly, it will return it into your interface)
========================
## Javascript Objects
###Everything in Javascript is an Object!
**What is an object?** 

* A collection of properties, and a property is an association between a name (key) and value.  A property's value can be a function, in which case, the property is known as a method. 
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects](http://)
###Categories of objects
There are three categories of objects: **Native, Host, and User.**
#####Native objects
* These objects are part of the programming language itself and make up the core data types. They are: **Undefined, Null, Boolean, String, Number, and Object.**
 
#####Host objects
* These objects are part of what the web browser gives you. The main ones are **window** and **document**. And everything within these two.

#####User objects
* While not an officially sanctioned category, this is basically any object you create yourself.####In-Class Lab #2: Creating Javascript Objects (in console, in JS files, in Snippets)
![image](/Users/sama/Documents/FEWD39/imagesForNotes/objects.png)
=====================
## DOM Manipulation - Creating Elements
###How do we currently create elements?
**In the web pages that we have built so far: **

* Elements were created when the page was first loaded.* Every element was put into the DOM tree in the order that the browser parsed it from our HTML file.
* We create the HTML page, so we we added these elements to the document.
**How do you make these things appear on the page? **
* How would you comment on a great photo?
* How do you add a new item to a to-do list?
* How do you pin something on Pinterest?How would you add these HTML elements to a page __*DYNAMICALLY?*__
###Using Javascript to create elements dynamically
####There are three steps to adding new elments on the page:
	1.) Create the element
	2.) Decorate the element
	3.) Insert the element

==========
###1.) Create the element
* The Document is responsible for creating new elements.
* Let's learn this new function: (best named function ever!)

		.createElement() 
	
	You call this new function like this (on the document object):
	
		document.createElement("li")
		
	Using this function, you can create any kind of Element you want!	
	
		<span>, <li>, <div>, <img> 
		
![image](/Users/sama/Documents/FEWD39/imagesForNotes/createElement.png)


Once you determine which element you want to create, assign it to variable:
	
		var li = document.createElement("li")
		
================
### 2.) Decorate the element
After creating the element, you can do these things to it:

* add a CSS class
* add text content
* give it an event listener (in future class lesson)

		li.textContent = "item #3: buy chocolate"
		result:  <li>item #3: buy chocolate </li>
		
		li.className = "bold"
		result: <li class = "bold"></li>
		
		li.addEventListener()
		
		
	
=============
### 3.) Insert the element (into the DOM)
To add the element to the DOM, you first have to get its parent element.  

* We use another new function to "query" for this parent element (or any element)

		.querySelector()
	You call this new function like this: 

		document.querySelector("ul")
		
	You can also assign that element to a variable:

		var ul = document.querySelector("ul")
	
* Once you have determined which **parent** element to use, you can **append** the newly created **child** element to it!  Use this new function : 

		.appendChild()

* From the notes above, we created a new element ("li") and decorated it with text content. Use __.appendChild()__ to append the new "child" element __li__ to the "parent" element __ul__

		var li = document.createElement("li")
		li.textContent = "item #3: buy chocolate"
		
		var ul = document.querySelector("ul")
		
		ul.appendChild(li)
		

![image](/Users/sama/Documents/FEWD39/imagesForNotes/Element.png)


=================

#### How do we add an image element into our DOM?
* What does an image element contain? (recall your HTML knowledge)
* What methods on the ELEMENT object would allow us to add necessary "attributes" to the <img> element?
* How would you place this newly created element onto the DOM?

In English: 

* We first locate our parent element
* We create a new image element (child)
* Then we decorate this image element with necessary attributes
* We append this image (child) element to our parent element

####Now, let's do that in Javascript!
===============


 
####In-Class Lab #3: Creating and Appending Elements (in the console, in the JS file)

####In-Class Lab #4: DOM Manipulation Exercise
 
==============
 
## Introduction to Event Handling
* Elements in a web page emit all kinds of "events", for example when a button is clicked it "fires" a "click" event. We can use these events to do things with special javascript functions called event handlers.

* Event handlers, which are just javascript functions to be called on some event, can be connected to events using a function on element objects called addEventListener.

* For example, you can create an event handler for button clicks that alerts a message like so:

  
    // get the button element

    	var button = document.querySelector('button');


    // create an event handler

    	function buttonClicked() {

        alert('Hello World!');

    	}


    // add your event listener

    	button.addEventListener('click', buttonClicked);

#### In-Class Lab #5/Homework: Calculator
In this exercise:

* user will enter in numbers in the first two input boxes
* user then "clicks" on one the math signs ( +, -, *, /)
* result of the calculation will appear after the " = " sign 
* __*hint__ the "input" element does not have a property called "textContent", it has a property called "value"

#### In-Class Lab #6/Homework: To-do List
In this exercise:

* user will enter something into the input field
* once user "clicks" on the "Create Todo" button, whatever was entered dynamically appears in the screen as a list item
* create two functions to make this functionality successful (createItem and formSubmitted)
* be sure to add an "event listener" to your form upon "submit"
* __*hint__ when you are submitting information and the "form" tag is used, you will need to use "event.preventDefault()"  Read up on this to see if you can figure out how to use this function:  [http://www.w3schools.com/jsref/event_preventdefault.asp](http://)

##### Homework - Cash Register
In this assignment: 

* user will enter a number and in the "item cost" field and this number populate into the un-ordered list
* be sure to increment the total value as the user enters more numerical data into the "item cost" field 
* comments in the js file are suggestions/hints. If you want to tackle it from a different order, feel free to try to code it in a different order.


