Modified GO v.1.2 Compiler
====

I changed three of the files in the directory go/src/cmd/gc so that I can now run Go code with the option of disabling errors due to unused variables. The changed files are walk.c, lex.c and go.h. To see specific changes, search for comments containing "DTNEWMAN" in these files.

One might argue that these changes technically break the the Go language's specifications, even though it is just a compiler option. See http://weekly.golang.org/doc/faq#unused_variables_and_imports for a discussion of why a compiler option like this is not included in the official golang compiler. The people making these decisions are very accomplished computer scientists who most likely gave this much more thought than myself. So I certainly don't want to suggest that my small changes are an improvement to the language, but I do find them useful when writing code for my personal use.  

I made these changes to my compiler since I found myself constantly needing to deal with unused variables when testing out new code. I have not tested these changes extensively, so implement them at your own risk. See http://golang.org/doc/install/source for more information about installing from source. To install with my modifications, you can follow the instructions there, but simply replace the three files mentioned above.

Once installed, you can run the code in two ways:

1) <b>go run test.go</b> will use the default compiler and will throw errors for unused variables

2) <b>go run -gcflags '-unused_vars' test.go</b> will ignore errors for unused variables
