

Quick do-what-I-mean clojure launcher.

Usage: clojure-launch [options]
    -h, --help                       Show this message
        --dir dir                    The top dir of the program.  
                                     Turns on --find
        --[no-]ensure-classes        Ensure the classes dir exists
        --[no-]find                  Walk the dir tree looking for jars, 
                                     classes, and properties files.
                                     Turning on --find turns off --clojure
        --clojure JAR                The location of clojure.jar or false.
                                     Defaults to /usr/local/lib/clojure.jar
        --[no-]rlwrap                Run clojure under rlwrap
        --[no-]heap SIZE             Set maximum Java heap size.
                                     Defaults to 1G
        --version                    Show version
