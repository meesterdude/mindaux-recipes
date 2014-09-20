# List Presentations

You can use the header and footer sections (found on the list edit page) to theme your items in the slideshow. This could be as simple as some text, or CSS and Javascript. This example can be modified, expanded on and improved.

For this example, we assume you have a list with items that mainly look like this:

```
# Title
### Descriptive one line sentence
```

And we want to style these items as slides to achieve the following:

 * centered on the page
 * have the company logo in the corner
 * have a header title for all slides
 * have a background color
 * descriptive one line sentence fades in after a delay on every page

## Header Changes

Add the following to the "header" of the list (found on the list edit page)

```
<style>
.item-content h3{margin-top:40px;}
h4.cust-title{text-decoration:underline;}
div.item-content{background-color:#def !important;}


@-webkit-keyframes fadeIn { from { opacity:0; } to { opacity:1; } }
@-moz-keyframes fadeIn { from { opacity:0; } to { opacity:1; } }
@keyframes fadeIn { from { opacity:0; } to { opacity:1; } }
.item-content h3 {
    opacity:0;
    -webkit-animation:fadeIn ease-in 1;
    -moz-animation:fadeIn ease-in 1;
    animation:fadeIn ease-in 1;
    -webkit-animation-fill-mode:forwards;
    -moz-animation-fill-mode:forwards;
    animation-fill-mode:forwards;
    -webkit-animation-duration:0.5s;
    -moz-animation-duration:0.5s;
    animation-duration:0.5s;
    -webkit-animation-delay: 1s;
    -moz-animation-delay: 1s;
    animation-delay: 1s;
}
.item-content img.cust-logo{width:80px!important;float:right;margin-right:10px;}
.item-content center.custom{min-height:450px !important;margin-top:200px;}
</style>

<h4 class='cust-title'>List Presentations With MindAUX</h4>
<center class='custom'>
```

This gives us some styling rules for our presentation, such as setting the background to a light blue and defining how the footer image will look. The interesting bit is the second part, which is what handles the fade in of the "descriptive one line sentence" these items have. All it's doing though is changing the opacity of the h3 after a second.

Then it goes on to define our header title, and starts the centering that will apply to all items content.

## Footer Changes

```
</center>
<img src="company.com/our_logo.png" class='cust-logo'></img>
```

All this does is close the center tag we opened in the header, and add a footer image that we defined styling for in the header.

With these changes, now all items will be styled the same.