
Quick do-what-I-mean clojure launcher.

This is a a ruby script that creates a class path and uses java to
launch clojure under screen and rlwrap.  Ruby, Java, screen, rlwrap,
and clojure must be installed.

The main trick is to create a correct classpath.  As far as this
program is concerned, a proper classpath contains all the .jar files
and all the directories that might contain .clj, .class, or
.properties files.

There are three use cases that I mostly run:

1. Just run clojure on the command line.

    clojure
    
This will create a classpath with ~/.clojure (if it exists),
/usr/local/lib/clojure.jar, and any src, classes, or properties in the
current directory.  Then java will be run with the arguments to create
a clojure repl.

2. Run clojure with the --project option

    clojure --project MY-PROJECT
    
This will create a classpath with ~/.clojure (if it exists), all the
.jar files that exists in the directory tree starting at MY-PROJECT.
The classpath will also have any src, classes, or properties
directories that exists under the MY-PROJECT tree.  Then java will be
run with the proper arguments to create a clojure repl.

3. Run clojure in an init.d script.

    su -l $PROJECT_USER -c \
        $CLOJURE --screen --name $PROJECT \
        --project $PROJECT_DIR \
        --require $PROJECT_REQUIRE \
        --eval $PROJECT_STARTUP

This will create the classpath as before and then run a clojure repl
under screen.  It will also require the given namespace and eval the
startup code.

-- Chris Dean ctdean@sokitomi.com

    Usage: clojure [options] [args]

    Construct and run clojure under Java.

    By default we just run clojure.main and start a repl

    All additional args are passed on the java command line.
    If no additional args are given the default startup
    sequence is used.

        --help                       Show this message
        --project dir                Sets the top project dir of the program.  
                                     Turns on --find and sets --clojure to false
        --dir dir                    Sets top dir of the program.  
                                     Defaults to '.'
        --[no-]ensure-classes        Ensure the classes dir exists
        --[no-]find                  Walk the dir tree looking for jars, 
                                     classes, and properties files.
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
