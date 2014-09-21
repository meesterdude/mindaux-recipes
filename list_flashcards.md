# List Flashcards

With this recipe, you'll be able to use the slideshow as a flashcard system. The Answer will fade in when you click on the page.

This assumes you have items with content structured like this:

```
   # How many ouzes in a pound?
   ## 16
```

## Header Changes

Add the following to the "header" of the list (found on the list edit page)

    <script>
        $('.slideshow .item-content').on("click", function(){
            $('.slideshow .item-content h2').fadeIn()
        })
    </script>
    <style>
        .slideshow .item-content h2{display:none;margin-top:40px;}
    </style>


