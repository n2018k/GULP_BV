Step 1: Get cif file of Li2O from MP mp-1960
Step 2: run softbv command to get softbv parameters for geometry optimization using the command below
./softBV.x --gen-gin-lib Li2O.cif 
Step 3: using information in Li2O.cif.lib, make input file for GULP called softbv_gulp.in
Step 4: optimize Li2O structure with GULP
gulp-6.4/Src/gulp < softbv_gulp.gin
Step 5: copy softbv_gulp.in to directory called MINES_BV
Step 6: edit Li O morse potential values using R0 and b values from previous work; Specifically, we change D0 and alpha value but keep Rmin same.
Step 7: optimize Li2O structure again with GULP using new input

And compare lattice parameters. 


Note: morse_gulp.in is the minimum input file we need to optimize Li2O structure with GULP. I have modified only the 
potential parameters for Li2O example above keeping everything else same.

Note: we always must use conp tag in input file with GULP for geometry optimization. conv tag in morse_gulp.in file is just for example. conv tag
does not optimize cell shape, size and volume. 

