#hella
A tiny, feature-rich responsive grid for desktop and mobile

At 1kb expanded, and less than 50 lines high, you can't get any smaller than this. 

###features
 1. offsets
 2. allows columns to not respond to screen size
 3. mixing non-responsive with resposnive elements works as expected
 4. infinite column nesting
 
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

If you want a non responsive column, add `non-responsive` to your column class.

If you want an offset, add `six-offset` to your column class, where `six` is whatever you want between `one` and `eleven`

##math
If you want to change the width of the margin between columns, or the number of columns, there's a bit of math to it, but this'll help you out:

 The verbose formula for calculating column width without margins in percent is:
 
`(100 / (<max columns>/<column>)) - (( <margin> * ((<max columns>/<column>)-1) ) / (<max columns>/<column>))` 

To calculate offsets, just take the column width, and add one margin width. So, for offset-one, take 6.5 and add 2.
