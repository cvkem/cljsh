# cljsh

This function allows you to use clojure as a shell (scipted operations).
Programs written for cljsh can be used as a (powerfull) replacement
of shell-scipt, but can also be used within shell-script. It is even 
possible to use these programs as a stage of a pipeline.

The current version is only available for linux. 

## Installation 
Put the script/cljsh in your /bin/ folder and make it executable.

If you don't have privileges to do this put it in your home-folder and
adjust the header line in you programs  '#!/bin/cljsh'  to '#!<absolute-path>/cljsh'.

## Usage
The first line of your program should be:

 #!/bin/cljsh'  
 
followed by zero or more optional cljsh commands (that all start with an #).
If you put cljsh in another location, for example in your home-folder, you
should set the path accordingly.

If you also need some libaries you can add them via by adding a
leiningen like depency, a relative path (pointing within your maven
repository) or an absolute path.

  #DEP [groupId/artifactId "version"] 
  #DEP /<absolute-path>
  #DEP <relative-path>

It is also possible to set a function that will be passed all arguments.
However, note the programmer/users responsibility to pass the right
number of arguments, or check for arguments. Use 

  #RUN <name-of-function-to-run>

You can start a REPL if you want by adding the clsh-command:

  #REPL

The cljsh will launch a repl. The #RUN function can be used to 
run some initializing steps
See the examples folder for a few examples.

## License

Copyright 2014 © Vinzi/C. van Kemenade.

Licensed under the EPL (see the file epl.html), same as clojure.
