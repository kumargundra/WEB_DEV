# Lab 01 | Home Page Prototype  

## Overview

In this project, you will make use of your knowledge of CSS to create a sample home 
page with navigation, large hero image, and three “card” boxes.

The goal of this lab will be to practice using CSS and HTML to create a simple home page. You will 
be using the HTML and CSS files provided in the Replit classroom. You will be editing the CSS file to 
style the HTML file. You will be using the browser to test your work.

_Note_ You should be able to complete this lab without making changes to the `index.html` file. 

![Figure 4.43](./assets/figure-4.43.jpg "Figure 4.43 - Completed Project")

## Instructions

1. Open the Replit classroom for this lab. You will see two files: `index.html` and `style.css`.
2. Examine the `index.html` file. You can use the WebView browser in Replit, or view the page in an external browser tab/window.
3. Examine the `style.css` file. You will be adding CSS rules to this file to style the HTML file.
4. First, let's style the `<header>` element. Set the background-image to the image in the `images` folder. Set the background-size to cover. Set the width of the `<header>` to 100% and its min-height to 500px.
5. Next, add the logo in the top-left corner as a background-image to the `<nav>` element. Set its size to about 60px. The padding and height of the `<nav>` will also have to be set based on the size of the logo. Also make sure the logo image does not repeat.
```css
nav {
  background-image: url(images/logo.svg);
  background-size: 60px;
  background-repeat: no-repeat;
  background-position: 10px 5px;
  padding: 20px;
  height: 100px;
}
```
6. Now, style the navigation links. For each list item in the `<nav>` element, remove the list bullets by setting the list-style-type to none. Make the list horizontal by setting the display property of each `<li>` to inline-block. Set the link, visited, and hover colors of the navigation links.
```css
nav li {
  display: inline-block;
  list-style-type: none;
}
```

7. Set the margin of the `ul` within the `<nav>` to move the `ul` left of the logo, so it's elements do not overlap the logo.
```css
nav ul {
  margin-left: 80px;
}
```

8. We'll also need to make sure the links are styled correctly. We can do this by using the `a` selector. We can also use the `:visited`, and `:hover` pseudo-classes to style the links when they are in different states. We can also use the `:active` pseudo-class to style the link when it is being clicked.
```css
nav a {
  color: #51279b;
  text-decoration: none;
  padding: 10px;
  font-weight: 600;
}

nav a:visited {
  color: #8662c7;
}

nav a:hover {
  color: #8662c7;
  text-decoration: underline;
}
```
9. Now, we can move on to the text in the center of the hero. Set the margin of the `<div>` within the `<header>` to position it roughly in the vertical middle of the big photo. Set its left margin so it is aligned with the navigation.
```css
header div {
  margin: 100px 0 0 80px;
}
```
10. Then we need to style the hero text. Per the mockup, it should be white, and the font size should be 48px for the `<h2>` element and 24px for the `<p>` element.
```css
header div {
    margin: 100px 0 0 80px;
    color: white; /* we can use the cascading nature of CSS to set the color for all the elements within the div */
}
header h2 {
  font-size: 48px;
  margin-bottom: 0.5rem;
}
header p {
  font-size: 24px;
  margin-bottom: 1.5rem;
}
```
11. There is a button in the hero, so we need to style that next. The button is nothing more than an anchor tag with a background color, and some padding. We can also use the `:hover` pseudo-class to style the button when the user hovers over it.
```css
/* We can to target header.div.a because if we taget simply a, then these styles will affect our navigation links as well */
header div a {
  background-color: #51279b;
  color: white;
  padding: 10px 20px;
  text-decoration: none;
  border-radius: 5px;
}

header div a:hover {
    background-color: #8662c7;
}
```
12. Now we need to style the cards. The card `<div>` elements need to be on a single line, so set the display property of each card to float left. For the `<div>` within the card (and its contents), set their padding and margins to get a similar appearance as Figure 4.43.
```css
/* Note we can use the .card class selector here, as a class has been assigned to the <section> elements. */
.card {
  float: left;
  display: inline-block;
  width: calc(33% - 10px);
  margin: 10px 5px;
  background-color: white;
}
```
13. Now we can style the card content. The card content should be left aligned, but we need to add a bit of padding around it. The image also needs to be full width, to expand to the width of it's parent container. The `div.description` element needs to have a font size of 12px, and the `h3` element needs to have a font size of 14px.
```css
.card div {
    padding: 20px 5px;
}

.card img {
    width: 100%;
}

.card div.description {
    font-size: 12px;
}

.card h3 {
    font-size: 14px;
}
```
14. Lastly, let's add the icons for the comments and favorites. First, target the `.social` class selector. We'll add a margin top of 1rem, and set the font size to 12px per the mockup. 
Next, let's target both of the `.social span` elements. The styles between the comment and the heart icon are very similar, so we save some keystrokes by targeting the most generic selector. The only difference between the `.heart` and `.comment` elements are their background images.
We'll need to set the background image size for the `.social span` to contain, and ensure the image does not repeat. We should also add a small padding to the left of the icons, so they are not right up against the text, and some small margin to the right of the icons, so they are not right up against each other.
```css
.social {
  margin-top: 1rem;
  font-size: 12px;
}

.social span {
  background-size: contain;
  background-repeat: no-repeat;
  padding-left: 25px;
  margin-right: 10px; /* we could use use 1em here, but 10px is a bit more precise */
}

.social .heart {
  background-image: url(./images/heart.png);
}

.social .comment {
  background-image: url(./images/comment.png);
}
```


![Figure 4.43](./assets/figure-4.43.jpg "Figure 4.43 - Completed Project")

#### Figure 4.43
-----

## On Your Own
We've guided you through the completion of the frist few steps, the steps below should be completed on your own. 

1. Refactor the card to use flexbox instead of floats. Because the cards are using precentage widths, there is a small gap between the cards on the right. Can you figure out how to remove the gap using flexbox? Additionaly the cards have varying heights. Can you figure out how to make the cards all the same height?

## Guidance and Testing

1. The steps above should walk you through creating the layout to match the mockup. You can review the video walkthrough for further guidance.


## Submission

Once you have completed the lab, please use the Invite button at the top right to collect a "Private Invite" link. Please copy that link into your Canvas submission and submit your assignment via Canvas for your instructor to grade.