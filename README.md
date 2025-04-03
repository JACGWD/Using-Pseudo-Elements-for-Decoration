#  Using Pseudo-Elements for Decoration
 
This responsive web design demo showcases the use of CSS pseudo-elements used to decorate a design once the viewport reaches a certain width.

[Please download the entire repo](https://github.com/JACGWD/Using-Pseudo-Elements-for-Decoration/archive/refs/heads/main.zip), and open the demo/index.html file in your web browser.

In your web inspector, expand the \<section> tags, and select the **::before** pseudo-element to see its styling.

## Creating Pseudo-Elements

A Pseudo-Element is a "virtual div" that you can add before and/or after any HTML element. It can hold text, or be used to add background images. 


### Step 1: Select the element you want to add decoration to 

A pseudo-element is created as a "virtual box" attached to any HTML tag of your choice. It could be: div, section, h1, p, ul, etc. These elements can also be identified by class (div.classname) or id (div#idname).

The trick however, is in order to attach a pseudo-element to a tag, **the tag must have a positioning rule**. This lets the pseudo-element follow along with the parent if the parent is moved.



    .parent-tag {
        position: relative;
        /* forces absolutely positioned child elements to be placed relative 
        to the top/left corner of this element by default */
    }

### Step 2: Create the pseudo-element


    .parent-tag::before {
        
        content: " "; 
        /* content cannot be empty, otherwise box collapses to no height */


        position: absolute;   
        /* position anywhere you like, on a layer */
        /* could also be "relative" for different behaviour */

        z-index: -1;
        /* control stacking like "send to back" */
        /* can be any negative (send to back) or positive (send to front) number, 
        ex: 99 is the 99th layer above the background */

        display: block;
        /* behave as normal block level element */

        background-image: url(img/bg.jpg);
        /* select image: path points from the css file to the image file */

        background-repeat: no-repeat;
        /* by default, backgrounds repeat to fill up the entire space */

        background-size: cover; 
        /* or "contain", or a size expressed in em, rem, %, px, etc */
        
        width: 100%;
        height: 5rem;
        /* control size explicitly in em, rem, %, px, etc */

        top: -5rem; 
        /* match height of pseudo-element to move it above top edge of parent */

        left: 0;
        /* align left */
    }