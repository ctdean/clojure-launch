
Quick do-what-I-mean clojure launcher.

This is a a ruby script that creates a class path and uses java to
launch clojure under screen and rlwrap.  Ruby, Java, screen, rlwrap,
and clojure must be installed.

Chris Dean ctdean@sokitomi.com

    Usage: clojure [options] [args]

    Construct and run clojure under Java.

    By default we just run clojure.main and start a repl

    All additional args are passed on the java command line.
    If no additional args are given the default startup
    sequence is used.

        --help                       Show this message
        --dir dir                    The top dir of the program.  
                                     Turns on --find
        --[no-]ensure-classes        Ensure the classes dir exists
        --[no-]find                  Walk the dir tree looking for jars, 
                                     classes, and properties files.
                                     Turning on --find turns off --clojure
        --clojure JAR                The location of clojure.jar or false.
                                     Defaults to /usr/local/lib/clojure.jar
        --[no-]rlwrap                Run clojure under rlwrap (default: on)
        --[no-]screen                Run clojure under screen (default: off)
        --name SCREEN-NAME           Set the session name for screen
        --[no-]verbose               Print the command run
        --[no-]heap SIZE             Set maximum Java heap size.
                                     Defaults to 1G
        --jar FILE                   Add FILE to the classpath
        --require PACKAGE            Require this during the default startup
        --eval EXPRESSION            Eval this during the default startup
        --java-arg ARG               Add ARG to the end of the java options
        --[no-]user-init             Add ~/.clojure to the class path if
                                     it exists
        --version                    Show version
