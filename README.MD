#hella
A tiny, feature-rich responsive grid for desktop and mobile

At 1.25kb *un-minified*, and 50 lines high, you can't get any smaller than this. 

####Check out the [demo page](http://codezombie.github.com/hella).

###features
 1. column offsets
 2. optionally allow columns to be non-responsive
 3. mixing non-responsive with responsive elements works as expected
 4. infinite column nesting
 5. graceful-degrading support for browsers with no media query support
 6. supports responsive columns *outside* of the grid. Just ommit the `grid` div.
 
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

 * You can choose a column width between `one` and `twelve` (if no width is specified, the default is `twelve`).
 * If you want a non responsive column, add `non-responsive` to your column class.
 * If you want to offset a column to the right, add `offset-*` to your column class, where `*` is the offset width between `one` and `eleven`.

##math
If you want to change the width of the margin between columns, or the number of columns, there's a bit of math to it, but this'll help you out:

 The verbose formula for calculating column width in percent, where `max columns` is the total number of columns, `column` is the current column who's width is being calculated, and `margin in percent` is the value of `.column{margin-right: %;}`, is:
 
`column width percent = (100 / (<max columns>/<column>)) - (( <margin in percent> * ((<max columns>/<column>)-1) ) / (<max columns>/<column>))` 

To calculate the `margin-left` of the `offset-*` class, just take the respective column `width`, and add the value of `.column` margin. For example, for offset-one, take 6.5(the width of `.column.one`) and add 2 (the `margin-left` of all `.column`s).
