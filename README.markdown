# jQuery HTML truncator

[jQuery](http://jquery.com/) (JavaScript) plugin to truncate HTML text with "more"/"less" links.

For example, you might see

    Lorem ipsum do (…more)
    
Clicking "…more" shows

    Lorem ipsum dolor sit amet. (less)
    
Clicking "less" goes back to the truncated text.

There is also [a live example](http://henrik.nyh.se/examples/truncator/) (or try the provided `example.html` locally).

## Graceful HTML handling

While there are many JavaScript truncators, this one is unique in handling HTML gracefully. That means you can truncate an element containing paragraphs, links, other markup and HTML entities without strange results.

`<b>a &amp; b</b>` is considered to be 5 (not 16) characters long during truncation, and truncation will never cause start tags to be missing their end tags, entities or tags to be broken apart, and so on.


## Usage

As shown in the provided `example.html`, just do e.g.

    $(function() {
      $('.example').truncate({max_length: 24});
    });
    
The selector and options can, of course, be changed.

The available options are:


 * **`more`**

   The text shown inside parentheses after the truncated text.
 
   Defaults to `…more`.


 * **`less`**

   The text shown inside parentheses after the full text.

   Defaults to `less`.


 * **`max_length`**

   Defaults to `100`.
   
   Note that the `" (…more)"` bit counts towards the max length – so a max length of 10 would truncate `1234567890` to `12 (…more)`.

## Credits

By [Henrik Nyh](http://henrik.nyh.se/).
