# Converting to .ml to .re with Makefile
## DOESNT WORK

This example doesnt work. Filed this [issue](https://github.com/facebook/reason/issues/2568#issue-606547422).

Use the `-n` flag to see what the `Makefile` is trying to do without actually doing it. Known as a `dry-run`.

This our `MakeHello` makefile. Since we didn't call it `Makefile` we will use the `-f` flag to indicate which `Makefile` we want to run.

Let us see what the dry run gets us. 
```sh
~/Github/ocaml_ppx_extension_simple_tutorial/reason-ppx master* ⇡
❯ make -n -f MakePpx.makefile
refmt -p ml ppx_test_simple.re > ppx_test_simple.ml
# Create the executable ppx_test_simple
ocamlc -I +compiler-libs ocamlcommon.cma ppx_test_simple ppx_test_simple.ml
# Output the original source
cat sample_input.ml
# Output the modified source
ocamlc -dsource -ppx ./ppx_test_simple sample_input.ml -c
# Compile with ppx extension
ocamlc -ppx ./ppx_test_simple sample_input.ml -o test
# Run the program
./test

```