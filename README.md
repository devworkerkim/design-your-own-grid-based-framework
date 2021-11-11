# Design Your Own Grid Based Framework | The Odin Project

This is the repo for the Design Your Own Grid-Based Framework project in the HTML And CSS course of The Odin Project.  The objective is to create a CSS framework that incorporates a 12-column grid layout and use it to recreate a webpage of your choice.

## What I Learned

### A Classic Way To Do Grid
I am grateful CSS Grid came out, and from what I've learned and gathered developers agree.  I was tempted to cheat this project and just use CSS Grid, but I told myself that I needed to suffer through this project so I could appreciate the tools that I have now.  I thought about how developers first started using data tables to layout their pages.  And as CSS evolved, this method of a grid-based framework using classes was the progression.

### `:root`
I have used CSS variables before and thought this would be a good opportunity to continue using them.  After all, this is supposed to be a framework that is able to adapt to any viewing width.  I finally got curious with where I was putting my CSS variables.  I just followed the examples of putting it in [:root](https://developer.mozilla.org/en-US/docs/Web/CSS/:root) without understanding what `:root` was.  It is a pseudo-class element that *matches the root element of a tree representing the document*.  For the case of an HTML document, it is the \<html\> tag which basically covers the entire document.  This makes the variables accessible for everything.

### CSS Wildcard Selectors
I had never used [Wildcard Selectors](https://www.geeksforgeeks.org/wildcard-selectors-and-in-css-for-classes/), but after reading about it in this course I thought I would give it a try.  I had some common names across my classes, but in order to capture all of them I had to use a wildcard selector.  This saved a ton of code because I would have written up an instance for every single name variation.

### Space Inbetween Inline-Block Elements
When I stringing elements together in the same row, I noticed there was a small gap between my elements.  I know I had cleared out all the margins, so it was strange to me to find there was still a small gap.  I found this article on [Fighting The Space Between Inline-Block Elements](https://css-tricks.com/fighting-the-space-between-inline-block-elements/) which explained the phenomenon and offered some common solutions.  How strange that HTML could produce such a problem.

### 100% Is Relative To Parent Container
This was more of a reminder about how [<percentage>](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) is relative to the parent element.  There are so many different units and how they are connected together with the elements it can be hard to keep track.

### `@import`
I finally learned how to [import](https://developer.mozilla.org/en-US/docs/Web/CSS/@import) a CSS file into another CSS file.  I did this to import my grid-based framework that I created for the project into the CSS file that is specific for the website.  I probably would have just had two link tags in the \<head\> to make it work, but I thought I would try something different.

### All Inline Elements Have The Same Height
I was running into an issue where I had elements in the same row but had different heights.  The row would render the height of the tallest element, but anything with less height would not fill in but rather just sink to the bottom of the row and leave all white at the top.  For text, this gave the perceptions that the vertical alignment was at the bottom.  I found this article on [how to place two div side-by-side of the same height using CSS?](https://www.geeksforgeeks.org/how-to-place-two-div-side-by-side-of-the-same-height-using-css/), along with some other posts, that offered changing the display property to `table` and using this display property to create the same height across all elements in the row and vertically align them as needed.  I avoided using flexbox just to challenge myself and do it the old-fashioned way.

## A Shift In CSS Methodology
While I was working on this project, I was on the side researching CSS and ran into some podcasts that had or featured Adam Wathan.  He has been an influencer in using something called "Utility-First" CSS that makes our CSS code more reusable.  The idea behind it is instead of labeling our CSS classes based on the content of the element, like I've been taught given the examples I've seen across tutorials and lessons, we should be labeling our CSS classes based on what the how the element is being styled.  I've seen this in a lot of the modern CSS frameworks and this project was a slight glimpse of the same methodology.

I think this "Utility-First" CSS methodlogy makes a lot of sense and differs significantly from what I have been doing before which was more semantic.  As for reusability, I don't have to be confused about using CSS class for two different elements that are intended to be styled the same but the class names don't reflect the content.  A side effect is we can eliminate having to think of naming more things, especially if it's a duplicate styling.

The HTML does look a little bit messy, but what this method does is it allows me to port over my CSS file to another site and with a few adjustments I can reuse the code.  Some refactoring can be done for those specific cases where things can be combined and reused, but I basically created CSS classes that describe how I'm styling the element and that can be reused.  I found I had to move back and forth between my HTML file and my CSS file and my class lists became long.  I haven't gotten to the point where I have had to maintain the CSS, but a few adjustments to the class list of an element and the CSS file shouldn't be a problem.  It's a sacrifice for reusability, but it might be worth it.