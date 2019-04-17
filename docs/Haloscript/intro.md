title:      HaloScript Intro
desc:       Introduction to haloscript
template:   document
nav:        HaloScript>Intro__-1__
percent:    70
date:       2019/04/17
authors:    Num0005

Haloscript (also called BlamScript) is a custom scripting language used in Halo and other games running on the Blam engine. It uses a syntax heavily based on [Lisp](https://en.wikipedia.org/wiki/Lisp_(programming_language)).

For instance a "script" (a function defined by the user) that prints `Hello World` to the debug output on startup would be:
```Lisp
(script startup welcome
			;this is a comment, this line will be ignored
            (print "Hello World")
)
```

To break down what individual parts of that mean:

* `script` marks the start of a script function.
* `startup` is the type of script, it tells the scripting system to start run the script on startup 
* `welcome` is just the name of the script
* `print` is a "command" (function built into the scripting language) that outputs a message of type string to the debug output.

Using the word "script" when talking about a user-defined function and "command" when talking about a function that is built into the language is a convention that will be used in the rest of this documentation.
{: .info}

## Function calls

In the example above we see the function `print` is being called with the argument "Hello World". Only certain type of functions can be called, all commands can be called but only "static" and "stub" scripts can be called. 
See [Script types] for more.