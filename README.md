Modified GO v.1.2 COMPILER
====

I changed three of the files in the directory go/src/cmd/gc so that I can now run Go code with the option of disabling errors due to unused variables. The changed files are walk.c, lex.c and go.h. To see specific changes, search for comments containing "DTNEWMAN" in these files.

One might argue that these changes technically break the the Go language's specifications, even though it is just a compiler option. See http://weekly.golang.org/doc/faq#unused_variables_and_imports for a discussion of why a compiler option like this is not included in the official golang compiler.

Nonetheless, I don't love the workaround that they suggest there, so I made some changes to my compiler. I have not tested these changes extensively, so implement them at your own risk. See http://golang.org/doc/install/source for more information about installing from source.
