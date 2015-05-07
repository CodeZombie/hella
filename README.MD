#hella
A tiny, feature-rich responsive grid for desktop and mobile

At 1.25kb *un-minified*, and 50 lines high, you can't get any smaller than this. 

####Check out the [demo page](http://codezombie.github.com/hella).

###features
 1. offsets
 2. allows columns to not respond to screen size
 3. mixing non-responsive with responsive elements works as expected
 4. infinite column nesting
 5. graceful support for browsers with no media query support
 
###How to use it
```
<div class="grid">
	<div class="row">
		<div class="column six">
			hella.
		</div>
	</div>
</div>
```

You can choose a colum width between `one` and `twelve` (if no width is specified, the default is `twelve`).

If you want a non responsive column, add `non-responsive` to your column class.

If you want an offset, add `offset-*` to your column class, where `*` is the offset width between `one` and `eleven`.

##math
If you want to change the width of the margin between columns, or the number of columns, there's a bit of math to it, but this'll help you out:

 The verbose formula for calculating column width without margins in percent is:
 
`(100 / (<max columns>/<column>)) - (( <margin> * ((<max columns>/<column>)-1) ) / (<max columns>/<column>))` 

To calculate offsets, just take the column width, and add one margin width. So, for offset-one, take 6.5 and add 2.
