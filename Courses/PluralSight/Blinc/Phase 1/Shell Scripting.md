## Introduction

* Bash shell scripts
    * Execute bash commands from a file
    * Automate sequences of shell commands
    * Run them later or at scheduled times
    * Take advantage of UNIX toolset
* Who needs it?
    * System administrators
    * Developers
    * Power users
* Bash scripts are very good at
    * File manipulation
    * Running programs
    * Processing text
* Sometimes other languages are better
    * Examples : mathematical calculations, binary data, graphics

## A First Look at Shell Scripts

* Creating a script
    * A text file containing code
    * To be run by an interpreter
    * In this course, the interpreter will be Bash
    * Will run each command in the file in order

* Choose a good text editor
    * Emacs, vi
    * Linux : Kate, gedit
    * Mac OS : TextWrangler

* Executable permissions
    * Use chmod command
        * "chmod u+x filename"
        * "chmod a+x filename" to make it executable for everyone
        * "chmod a+x filename" to remove the permission

* Calling the script
    * If the script is not on you PATH
        * Include the directory when calling it
        * ./hw
        * /home/reindert/hw
    * If the script is on you path
        * Just call it like a regular command
    * Tip : make a bin folder in your home
        * Put your scripts in there
        * Add it to you path
        * PATH="$PATH:~/bin"

* Shebang
    * Shebang line
        * First line of file
        * Starts with #!
        * Specifies which interpreter should run the code
        * Specify options for interpreter
    * Bash scripts
        * #!/bin/bash
    * Other systems than Linux or Mac OS
        * May have bash in a different location
        * #!/usr/bin/env bash
        * This will find bash on the user's PATH
        * Cannot give options
        * Result depends on the user's configuration

* Naming you script
    * Don't name your script "test", "if" or "ls"
        * Conflicts with existing commands
    * Does a command with the same name exist?
        * Use "type"

## Variables

* Variables
    * Used to store data by name
    * To create : just assign a value
        * x=10
        * If x already existed, it is assigned the new value
        * Values containing spaces : use quotes
        * Don't use whitespace around =
    * To get the value
        * Prefix with $
        * echo $x
    *  Bash variables have no data type
        * Basically just store a string
    * Names
        * Only letters, numbers and underscore are allowed
        * First character should be a letter or an underscore
        * Variable names are case-sensitive
    * Uppercase variables
        * Bash has many pre-defined variables
        * PATH, HOME, SECONDS, IFS, etc.
        * You don't override them by mistake
    * Good habit
        * Use lowercase names for you variables

* Using variables
    * Good habit : surround your variables with quotes
        * Use "$x" instead of $x
        * Prevent surprises when it contains spaces
        * Use double quotes : keep meaning of dollar sign intact
    * Braces:
        * echo "${foo}bar"
        * prints value of var "foo" followed by string "bar"
        * echo "$foobar" prints value of "foobar"
        * Using braces a lot is a good habit
    * Another good habit
        * Use $HOME instead of ~

* Reading input
    * Reads a line of input into a variable
    * read var
    * is a shell bulletin
    * "help read"
    * "man builtins"
    * read -p"Type your name:"name

## If, Then, Else

* If
    * if testcode; then
            #Code here gets executed
            #When testcode succeeds
        fi
    * if testcode; then
            #Code here gets executed
            #When testcode succeeds
        else
            #Code here gets executed
            #When testcode fails
        fi
    * if testcode; then successcode; else failcode; fi
    * Else if is written as elif
        * Can have multiple elifs

* Return codes
    * Return code or exit status
        * Value returned by program on exit
        * 0 to 255
    * 0 means success
        * other values are error codes
    * Shell script return values with exit
        * exit 0
    * Good habit : make sure your program exits with a correct value
        * ALways call exit with a value
    * If statement just looks at return code for "testcode"

* Conditional expressions
    * Conditional expressions
        * Tests on files and directories
        * Tests on strings
        * Arithmetic tests
    * [[ Expression]]
        * [[ $str ]]                  \\True if str is not empty
        * [[ $str = "something" ]]    \\True if str equals string "something"
        * [[ $str="something" ]]      \\True if always returns true!
        * [[ -e $filename ]]          \\True if file $filename exists
        * [[ -d $dirname ]]           \\True if $dirname is a directory
    * Spaces around the expression are very important!
    * Same for swithces (-e) and equals sign
    * Classical command: "test"
        * Also : [
        * Harder to use, easier to make mistakes
        * Only use for portability
    * [[...]] is a bash extension
        * Not a command but special syntax
        * No quotes needed around variables
        * Good habit : use [[..]] instead of [..]
    * Getting help
        * "help test" will show you most important info
        * "help [[" will tell you about the extension

* Arithmetic tests
    * For comparing integers Only
    * [[ arg1 OP arg2]]
    * Where OP is:
        * -eq: equality
        * -ne: not equal
        * -lt: less than
        * -gt: greater than
    * Special variables
        * $# contains number of script arguments
        * S? contains exit status for last command
    * To get the length of the string in a variable
        * Use ${#var}

* And, Or, Not
    * In a conditional expression
    * Use ! to negate a test
        * [[ ! -e $file ]]
        * Use spaces around !
    * Use && for "and"
        * [[ $# -eq 1 && $1 = "foo" ]]
        * True if there is exactly 1 argument with value foo
    * Use || for "or"
        * [[ $a || $b ]]
        * True if a or b contains a value (or both)
    * Dont even use -a, -o for and, or

## Input and Output

* echo
    * Prints its arguments to standard output followed by a newline
    * -n suppresses the newline
    * -e allows use of escape sequences
        * \t : tab
        * \b : backspace
    * These options are not portable to non-bash shells

* printf
    * Can do more sophisticated output than echo
    * Uses a format string for formatting
    * Will not append a newline by default

* read
    * Reads input into a variable
    * "read x"
    * No variable specified? will use REPLY
    * -n or -N specifies number of characters to read
    * -s will suppress output (useful for passwords)
    * -r disallows escape sequences, line continuation
    * Good habit : always use -r
    * Several more useful options

* read can read words in a line into multiple variables
    * read x y
    * input"1 2 3": x=1, y="2 3"
    * Uses IFS variable for delimiters

* Standard streams
    * Three standard streams
        * input, output, error
        * Represented by number (file descriptor), or special file
    * 0 : Standard Input (stdin)
        * /dev/stdin
    * 1 : Standard Output (stdout)
        * /dev/stdout
    * 2 : Standard Error (stderr)
        * /dev/stderr
        * Used for diagonistic or error message
    * /dev/null discards all data sent to it

* Redirection
    * Get input from somewhere else, send output or errors somewhere else
    * Input redirection : <
        * grep milk < shoppingnotes.txt
    * Output redirection : >
        * ls > listing.txt
        * Will overwrite existing files
        * Although this can be customized with the set command
        * >> appends to the end of a file
    * Pipes
        * ls | grep x
    * Redirect a specific stream with N>
        * "cmd 2> /dev/null" discards all errors
    * Redirect to a specific stream with >&N
        * >&2 sends output to stderr (Equivalent to 1>&2)
        * 2>&1 redirects stderr into stdout
    * Sending both error and output to a single file
        * cmd > logfile 2>&1
    * Allowed anywhere on the command line, but order matters
        * "cmd < inputfile > outputfile" is similar to ">outputfile cmd < inputfile"
        * cmd >logfile 2>&1 (Sends errors to the logfile)
        * 2>&1 >logfile cmd (Sends errors to stdout)

## Control Flows

* while
        while test; do
            ;; code to be repeated
        done

* until
        until test; do
            ;; code to be repeated
        done
    * Repeats code in the block
    * Continues as long as test returns false

* The classic for loop
        for VAR in WORDS; do
            ;; code to be repeated
        done
    * Assign each word in WORDS to var in turn
    * Will stop when no words are left
    * Do NOT quote words

* The C-style for loop
        for (( INIT; TEST; UPDATE )); do
            ;; loop code
        done
    * Use double parentheses
    * First expression : initialize your loop variables
    * Second expression : a test. The loop will run as long as this is true
    * Third expression : update the loop variables
    * Expression use syntax for arithmetic evaluation

* Break and Continue
    * break
        * quits the loop
    * continue
        * skips the rest of the current iteration
        * continues with the next iteration
    *  Both can be used in for, while and until

* case
        case WORD in
            PATTERN1)
                code for pattern 1;;
            PATTERN2)
                code for pattern 2;;
            ...
            PATTERNn)
                code for pattern n;;
        esac
    * Matches word with patterns
        * Pattern matching is the same as with matching filename patterns
        * Use 8, ?, []
    * Code for first pattern that mathes gets executed
    * End code with ;;
        * SO you can use multiple statements separated by ;
    * Multiple patterns separated by |

* Command groups
    * Group commands with {}
        * Will group them into a single statement
        * Can use I/O redirection for the whole group
        * Use the group in an if statement or while loop
        * Return status is that of the last command in the group
    * { cmd1;cmd2;cmd3 }
        * Separate the commands with newlines or semicolons
        * Use spaces around braces
        * Ending semicolon or newline not optional

* || and &&
    * Execute next statement depending on return status of previous statement
        * Basically : short for if
    * &&
        * Will execute next statement only if previous one succeeded
        * mkdir newdir && cd newdir
    * ||
        * Will execute next statement only if previous one failed
        * [[ $1 ]] || echo"missing argument">&2
    * [[ $1 ]] || echo"missing argument">&2&& exit 1
        * Dont do this: will always exit
        * [[ $1 ]] || {echo""missing argument">&2; exit 1;}

## Variables 2

* Variable attributes
    * Variables hold simple string values
        * But can also have extra attributes
    * Turn these on/off with declare
        * You can also use "typeset" (but that is deprecated)
    * Print attributes for a variable
        * declare -p var
    
* Integer Variables
    * Interger variable
        * declare -i num
        * Now $num can hold only numbers
        * Trying to set it to something else will NOT give an error
        * Instead, this will set a value of 0
    * Unset an attribute with +
        * declare +i num
    * Triggers arithmetic evaluation

* Arithmetic expressions
    * C-like syntax for doing calculations
    * let command
        * let n=100/2
    * (( .. ))
        * ((++x))
        * ((p=x/100))
        * (( p=$(ls |wc-1)*10 ))
        * This is a command equivalent to let
    * $(( .. ))
        * This is substitution, not a command
        * p=$((x / 100))
    * With a variable declared as an integer
        * num="30 % 8"
    * No need to quote variables
    * (( .. )) can be used in if, while
        * 0 is false, anything greater than 0 is true
        * (( 0 )) || echo "false"
    * Pitfall : numbers with leading zeroes are interpreted as octal
        * So 010 = 8
    * (( ..; ..; .. )) syntax in for loop is not an arithmetic expression
        * but the three expressions separated by ; are

* Read only variables
    * declare -r constant="some value"
    * Cannot give $constant another value
    * Bach will report an error

* Exporting variables
    * By default, variables are local to you script
        * Or terminal session
    * Export a variable
        * To make it available to subprocesses
        * You cannot pass a variable to the program that runs you script
    * export var
        * export var="value"
    * declare -x var
        * declare -x var="value"

* Arrays
    * An array can hold multiple values
        * Stored and retrieved by index
    * Storing a value
        * x[0] = "some"
        * x[1] = "word"
    * Retrieving a value
        * ${x[0]} : same
        * ${x[1]} : word
        * ${x[@]} or ${x[*]} retrieve all values (quoting works like $*, $@)
    * declare -a x
        * Or simply assign with an index like above
    * Intializing an array
        * ar = (1 2 3 a b c)
    * Count the number of elements in $array
        * ${#array[@]}
    * The indices in $array
        * ${!array[@]}
        * The can be gaps in the indices
    * You cannot export an array
    * Bash 4 supports associative Arrays
        * Where elements are stored and retrieved by a name, not an index
        * declare -A array

## Handling script parameters

* Special variables
    * Hold the n-th command line argument : $1, $2, etc.
    * Above 9 use braces : ${10}, ${25}
    * $0
        * Holds name of the script as it was called
    * $@ : All
        * Equivalent to $1 $2 $3 ... $N
        * But when double quoted : "$1" "$2" "$3" ... "$N"
        * So parameters containing multiple words stay intact
    * $*
        * Equivalent to $1 $2 $3 ... $N
        * But when double quoted : "$1 $2 $3 ... $N"
        * Dont use this, use $@ instead
    * $#
        * Holds the number of arguments passed to the script
* Shift
    * Removes the first argument
    * All positions paramters shift
        * $2 -> $1
        * $3 -> $2
        * $4 -> $3
        * etc.
    * $# lowered by 1
* Getopts
    * Utility to help parse argument lists
        * Expects options to start with a dash (-x)
        * Allows options that take an argument (-f file)
    * getopts optstring name
    * optstring
        * A list of expected options
        * "ab" will let your script handle an option -a and/or -b
        * Append : to options that take an argument
        * "a:b" will let a take an argument, but not b
    * name
        * The name of a variable
        * Every time you get getopts, it will place the next option into $name
    * getopts returns false when no more options are left
    * Any word not starting with a dash will end option processing
        * So anything after the options, you have to parse for yourself
        * An option "--" will be seen as the end of options as well
    * Arguments for options will be put in OPTARG
    * OPTIND holds the index of the next argument to be processed

## Shell Functions

* Functions
    * Define your own command
    * name () { ... }
        * You can run the code in the braces as a new command
        * Other equivalent syntax (not recommended)
            * function name () { ... }
            * function name { ... }
    * Execute it like any command
        * Give it arguments
        * Use redirection
    * Positional parameters are available for function arguments
        * $1, $2, ...
    * Naming your functions
        * Same rules as for naming scripts : don't override existing commands
    * Bash variables are globally visible
        * In a function, you can make a variable local to that function
        * Use declare or local
    * Exit a function with return
        * returns a status code, like exit
        * Without a return statement, function returns status of last statement
    * Returning any other value
        * Use a global variable
        * Or send the data to output and use command substitution
    * Exporting a function
        * export -f fun
* Miscellaneous
    * Functions and redirection
        * Redirection is allowed immediately after function definition
        * Will be executed when function is run
    * A command in a pipeline runs in a subshell
    * Here documents
        * Have a command read its input from the source file
        * << Tag
        * Tag defines end of input

## Fun with Strings

* Parameter Expansion
    * Allows powerful string manipulation
    * ${#var} : length of $var
* Removing a pattern
    * Removing part of a string
        * ${var#pattern} : Removes shortest match from begin of string
        * ${var##pattern} : Removes longest match from begin of string
        * ${var%pattern} : Removes shortest macth from end of string
        * ${var%%pattern} : Removes longest match from end of string
    * Pattern matching is like pathname matching with *, ? and []
    * Example : i="/Users/reindert/demo.txt"
            ${i#*/} returns "Users/reindert/demo.ext"
            ${i##*/} returns "demo.txt"
            ${i%.*} returns "/Users/reindert/demo"
            ${i%/*} returns "/Users/reindert"
* Search and replace
    * Search and replace
        * ${var/pattern/string} : Substitute first match with string
        * ${var//pattern/string} : Substitute all matches with string
    * Anchor your pattern
        * ${var/#pattern/string} : Matches beginning of the string
        * ${var/%pattern/string} : Matches end of the string
* Default values
    * Default value
        * ${var:-value} : Will evaluate to "value" if var is empty or unset
        * ${var-value} : Similar, but only if var is unset
    * Assign a default value
        * ${var:=value} : If var was empty or unset, this evaluates to "value" and assigns it to var
        * ${var=value} : Similar, but only if var is unset
* Conditional Expression Patterns
    * ==, != operators in [[ .. ]] do pattern matching
        * == is the same operator as =
        * [[ $var == pattern ]] : Returns true wehn $var matches the pattern
        * Pattern matching is like pathname matching with *, ? and []
    * Use quotes to force string matching
    * =~ does regular expression matching
        * Very powerful
        * Uses POSIX extended regular expressions
        * ? matches the token before it 0 or 1 times
            * [0-9]? will match a single digit or nothing at all
        * * matches the token before it for any number of times
            * [a-z]* will match any lowercase text or nothing at all
        * + matches the token before it for one or more times
            * [0-9]+ will match 1 or more digits
        * ^ matches start of string
        * $ macthes end of string
* End of options
    * Is denoted by --
        * Supported by many UNIX commands
        * Arguments after this will not be interpreted as options
    * Makes it safe when working with data that starts with a dash
    * Good habit :
        * When you use a variable as an argument for a command
        * And the contents of the variable are not under you Control
        * Use -- with the commands you call

## Many Ways to Run Your Scripts

* Running code from a file
    * Using hash-bang and running it as a command
        * Will start a bash subprocess
        * Executable permission has to be set
    * Or when it does not have a hash-bang
        * bash myscript
        * No permission necessary
        * bash -x myscript : Debugs myscript
    * TO import code in the current shell process
        * source myscript
        * .myscript
        * This is basically what happens with .bashrc
* Background and nohup
    * Put a command in the background with &
        * myscript &
        * It will be disconnected from the interactive session
        * Will be suspended if it tries to read input from the terminal
    * Long-running scripts
        * Keep your script running when you exit the terminal session
        * nohup myscript &
    * Run your script with a lower priority
        * nice myscript
* Redurecting with exec
    * Redirect I/O for the whole script
        * Useful for logging
* Running your script another time
    * At
        * Will execute your script at a specific time
    * Cron
        * Will execute your script according to a schedule
        * On Mac OS, use launchd
        * On Ubuntu, you may want to look at Upstart
* set and shopt
    * Customize bash behaviour with set and shopt
    * set
        * -x prints each command with its arguments as it is executed
        * -u gives an error when using an uninitialised variable and exits script
        * -n read commands but do not execute
        * -v print each command as it is read
        * -e exits script whenever a command fails
    * shopt
        * Can set many options with -s, unset with -u
        * shopt -s nocaseglob : Ignore case with pathname expansion
        * shopt -s extglob : Enable extended pattern matching
        * shopt -s dotglob : Include hidden files with pathname expansion
        * set -o noclobber : Don;t overwrite files on redirection operations