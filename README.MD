 The verbose formula for calculating column width without margins in percent is:
`(100 / (<max columns>/<column>)) - (( <margin> * ((<max columns>/<column>)-1) ) / (<max columns>/<column>))  
`(100 / (12/x)) - (( 2 * ((12/x)-1) ) / (12/x))
to calculate offsets, just take the column, and add one margin.
so, for offset-one, take 6.5 and add 2.