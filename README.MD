# hella
A tiny, feature-rich responsive grid for desktop and mobile.

Works on all modern browsers *and* Internet Explorer 11.

At < 80 lines tall, you can't get any smaller than this. 

![image](https://i.imgur.com/TBojBgG.png)

#### Check out the [demo page](http://codezombie.github.com/hella).

### features
 1. column offsets
 2. fluid column height
 3. rows can be non-responsive
 4. column margins can be toggled
 5. infinitely nest rows within rows
 6. hide columns on different screen sizes
 7. graceful-degrading support for browsers with no media query support
 
### How to use it
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
 * If you want a non responsive row, add `non-responsive` to the row's class.
 * If you want to offset a column to the right, add `offset-*` to your column class, where `*` is the offset width between `one` and `eleven`.
 * If you want a column to only show on a certain screen size, add `large-only` or `small-only` to your column class.
 * If you want to remove a margin between two columns, add `no-margin` to the leftmost column.

## math
If you want to change the width of the margin between columns, or the number of columns, there's a bit of math to it, but this'll help you out:

 The verbose formula for calculating column width in percent, where `max columns` is the total number of columns, `column` is the current column who's width is being calculated, and `margin in percent` is the value of `.column{margin-right: %;}`, is:
 
`column width percent = (100 / (<max columns>/<column>)) - (( <margin in percent> * ((<max columns>/<column>)-1) ) / (<max columns>/<column>))` 

To calculate the `margin-left` of the `offset-*` class, just take the respective column `width`, and add the value of `.column` margin. For example, for offset-one, take 6.5(the width of `.column.one`) and add 2 (the `margin-left` of all `.column`s).
