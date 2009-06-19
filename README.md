
Quick do-what-I-mean clojure launcher.

This is a a ruby script that creates a class path and uses java to
launch clojure under screen and rlwrap.  Ruby, Java, screen, rlwrap,
and clojure must be installed.

    Usage: /Users/ctdean/bin/clojure [options] [args]

    Construct and run clojure under Java.

    All additional args are passed on the java command line.
    If no additional args are given clojure.main is used.

            --help                       Show this message
            --dir dir                    The top dir of the program.  
                                         Turns on --find
            --[no-]ensure-classes        Ensure the classes dir exists
            --[no-]find                  Walk the dir tree looking for jars, 
                                         classes, and properties files.
                                         Turning on --find turns off --clojure
            --clojure JAR                The location of clojure.jar or false.
                                         Defaults to /usr/local/lib/clojure.jar
            --[no-]rlwrap                Run clojure under rlwrap
            --[no-]verbose               Print the command run
            --[no-]heap SIZE             Set maximum Java heap size.
                                         Defaults to 1G
            --jar FILE                   Add FILE to the classpath
            --java-arg ARG               Add ARG to the end of the java options
            --version                    Show version


Chris Dean ctdean@sokitomi.com
