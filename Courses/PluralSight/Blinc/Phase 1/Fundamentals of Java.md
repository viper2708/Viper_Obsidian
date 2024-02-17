# Fundamentals of Java

## Introduction and setting up the environment

* Creating and running Java Apps
    * Java file
        * Java Development kit tools
            * Java App
            * Java Runtime Environment
            * Host Environment

* Summary
    * Java is a language and a runtime environment
        * Specific environment features may vary (Java SE/ME/EE, JavaFX, Android)
        * Language remains pretty consistent
    * End-users require the Java Runtime Environment(JRE)
    * Developers require the Java Development Kit(JDK)
    * Many Integrated Development Environments(IDE) are available
        * Eclipse
        * IntelliJ
        * Netbeans

## Creating a Simple App

* Summary
    * Execute programs from the command line with the "java" command
        * Remember to use the full class name including the package name
        * On Windows must include the JRE bin folder in the Path environment variable
    * Programs are made up of statements
        * Statements end with a semicolon
        * Parts separated by zero or more whitespaces
    * Use comments to add notes and hide statements from the compiler
    * Packages provide organization
        * Assure uniqueness
        * Most IDEs tie source code file structure to package name

## Variables, Data types and Math Operator

* Variables
    * Named data storage
    * Strongly typed
    * Value can be modified

* Naming Variables
    * Variable naming is based on a combination of rules and conventions
        * Rules allow the use of letters, numbers, $ and _
            * By convention only letters and numbers are used
        * Rules require that first character is not a numbers
            * By convention it is always a letter
        * By convention follow the style often referred to as "Camel Case"
            * First letter is lower case
            * Start of each word after the first is upper case
            * All other letters are lower case

* Primitive data types
    * Built into the language
    * Foundation of all other types
    * Four categories of primitive types
        * Integer
        * Floating point
        * Character
        * Boolean

* Integer types
    * byte (8 bits)
    * short (16 bits)
    * int (32 bits)
    * long (64 bits)

* Floating point types
    * Implementation of IEEE 754 floating point standard
    * Stores values containing a fractional portion
    * Supports positive, negative and zero values
    * Types
        * Float (32 bits)
        * Double (64 bits)

* Character and Boolean Types
    * The char type stores a single Unicode character
        * Literal values placed between single quotes
        * For Unicode code points, use \u followed by 4-digit hex value
    * The boolean type stores true/false values
        * Literal values are true and false

* Arithmetic operators
    * Basic operators
        * Add (+)
        * Substract (-)
        * Multiply (*)
        * Divide (/)
        * Modulus (%)
    * Prefix/postfix operators
        * ++ increments value by 1
        * -- decrements value by 1
        * As prefix applies operation before returning value
        * As postfix applies operation after returning value
    * Compound assignment operators
        * Combines an operationand assignment
            * Applies result of right side to left side
            * Stores that result in variable on left side

* Operator precedence
    * Operators are evaluated in a well-defined order
        * Postfix
        * Prefix
        * Multiplicative
        * Additive
    * Operators of equal precedence are evaluated from left to right
    * Can override precedence with parenthesis
        * Nested parenthesis evaluated from the inside out

* Type conversion
    * Implicit type conversion
        * Conversions performed automatically by the compiler
        * Widening conversions are automatic
        * Mixed integer sizes
            * Uses largest integer in equation
        * Mixed floating point sizes
            * Uses double
        * Mixed integer and floating point
            * Uses largest floating point in equation
    * Explicit type conversion
        * Conversions performed explicitly in code with cast operator
        * Can perform widening and narrowing
        * Floating point to integer drops fraction
        * Use caution with narrowing conversions
        * Integer to floating point can lose precision

* Summary
    * Variables are stringly typed in Java
    * Primitive types
        * Integer types, floating point types, char type, boolean type
    * Math operators
        * Basic operators, postfix/prefix operators, compound assignment operators
    * Math operators follow a well-defined order of precedence
    * Type conversions
        * Compiler can automatically apply widening type conversions
        * Use type casting to explicitly perform type conversions

## Conditional Logic, Looping and Arrays

* Adding conditional logic
    * Relational operators
    * Conditional assignments
    * The if statement
    * Logical operators

* Relational operators
    * Greater than (>)
    * Greater than or equal to (>=)
    * Less than (<)
    * Less than or equal to (<=)
    * Equal to (==)
    * Not equal to (!=)

* Conditional assignment
    * Assign a value to a variable based on the result of a condition
        * result = condition ? true-value : false-value ;

* If-else Statement
    * An if statement conditionally executes a statement
```
            if (condition)
                true-statement;
            else
                false-statement;
```

   * The optional else clause executes a statement when the if condition is false
   * If-else statements chained together are evaluated in order until one is true

```
            if (condition-1)
                true-statement;
            else if (condition-2)
                true-statement;
                .
                .
                .
            else if (condition-N)
                true-statement;
            else
                false-statement;
```


* Block statement
    * A block statement groups statements into a compound statement
            {
                statement-1;
                statement-2;
                .
                .
                .
                statement-N;
            }

* Block statements and Variable Scope
    * A variable declared within a block is not visible outside of the block
        * A variable's range of visibility is known as the variable's scope

* Logical operators
    * And (&)
    * Or (|)
    * Exclusive or (XOR) (^)
    * Negation (!)

* Conditional logical operators
        * Conditional and (&&)
        * Conditional or (||)
    * Resolve following conceptually similar rules as non-conditional and/or
    * Only execute the right-side if needed to determine the result
        * && only executes right-side if left-side is true
        * || only executes right-side if left-side is false

* While Loop
    * Repeatedly executes a statement as long as the condition is true
        * Condition checked at loop Start
        * Statement may never execute
                while (condition)
                    statement;

* Do-while Loop
    * Repeatedly executes a statement as long as the condition is true
        * Condition checked at loop end
        * Statement always executes at least once
                do
                    statement;
                while (condition);

* For Loop
    * Repeatedly executes a statement as long as the condition is true
        * Condition checked at loop start
        * Provides simplified notation for loop control values
                for(initialize; condition; update)
                    statement;

* Arrays
    * Provides an ordered collection of elements
        * Each element accessed via an index
        * Indexes range from 0 to number-of-elemets minus 1
        * Number of elements can be found via array's length value

* For-each Loop
    * Executes a statement once for each member in an array
        * Handles getting collection length
        * Handles accessing each value
                for (loop-variable-declaration : array)
                    statement ;

* Switch
    * Transfers control to a statement based on a value
        * Simplifies testing against multiple possible matches
        * Only primitive types supported are char and integers
        * A match can execute more than one statement
        * Use break to avoid "falling through"
        * Can optionally include default to handle any unmatches values

```
                switch (test-value) {
                    case value-1:
                        statements
                    case value-2:
                        statements
                        .
                        .
                        .
                    case value-n:
                        statements
                }
```


* Summary
    * Use the if-else statement to provide conditional logic
        * If-else statements can be chained together
    * Block statements use brackets to group statements
        * Variables declared within a block are not visible outside of the block
    * Both while and do-while loops execute as long as a condition is true
        * The do-while loop body always executes at least once
    * The for loop provides simplified notation for loop initialization and control
    * For-each statement handles details of executing once for each array member
    * Switch statement simplifies notation of testing against multiple matches

## Representing Complex Types with Classes

* Classes in Java
    * Java is an object-orientated language
    * Objects encapsulates data, operations, and usage semantics
        * Allows storage and manipulation details to be hidden
        * Separates "what" is to be done from "how" it is done
    * Classes provide a structure for describing and creating Objects
    * A class is a template for creating an object
        * Declared with the class keyword followed by the class name
        * Java source file name nornally has same name as the class
        * Body of the class is contained within brackets
    * A class is made up of both state and executable code
        * Fields
            * Store object state
        * Methods
            * Executable code that manipulates state and performs operations
        * Constructors
            * Executable code used during object creation to set the initial state

* Using Classes
    * Use the new keyword to create a class instance (a.k.a an object)
        * Allocates the memory described by the class
        * Returns a reference to the allocated memory

* Encapsulation and Access Modifiers
    * The internal representation of an object is generally hidden
    * This concept is known as encapsulation
    * Java uses access modifiers to achieve encapsulation
    * Basic access modifiers
        * Public
        * Private
        * Protected
        * Default

* Naming classes
    * Class names follow the same rules as variable names
    * Class name conventions are similar to variables with some differences
        * Use only letters and numbers
        * First character is always a letter
        * Follow the style often referred to as "Pascal Case"
            * Start of each word, including the first, is upper case
            * All other letters are lower case
        * Use simple, descriptive nouns
        * Avoid abbreviations unless abbreviation's use is more common than full name

* Method basics
    * Executable code that manipulates state and performs operations
        * Name    
            * Same rules and conventions as variables
            * Should be a verb or action
        * Return type
            * Use void when no value returned
        * Types parameter list
            * Can be empty
        * Body contained with brackets
                return-type name (typwd-parameter-list){
                    statements
                }

* Exiting from a Method
    * A method exits for one of the three reasons
        * The end of the method is reached
        * A return statement is encountered
        * An error occuers
    * Unless there's an error, control returns to the method caller

* Methods return values
    * A method returns a single value
        * A primitive value
        * A reference to an object
        * A reference to an array
            * Arrays are objects

* Special references : this and null
    * Java provides special references with predefined meanings
        * this is an implicit reference to the current object
            * Useful for reducing ambiguity
            * Allows an object to pass itself as a parameter
        * null is a reference literal
            * Represents an uncreated object
            * Can be assigned to any reference variable

* Field encapsulation
    * In most cases, a class fields should not be directly accessible outside of the class
        * Helps to hide implementation details
        * Use methods to control field access
    * Accessors and Mutators
        * Use the accessor/mutator pattern to control field access
            * Accessor retrieves field value
                * Also called getter
                * Method name : getFieldName
            * Mutator modifies field value
                * Also called setter
                * Method name : setFieldName

* Summary
    * A class is a template for creating an object
        * Declared wuth class keyword
        * Class instances (a.k.a objects) allocated with new keyword
    * Classes are reference types
    * Use access modifiers to control encapsulation
    * Methods manipulates state and performs operations
        * Use return keyword to exit and/or return a value
    * Fields store object state
        * Interaction normally controlled through accessors(getters) and mutators(setters)

## Class Initializers and Constructors

* Establishing Initial State
    * When an object is created, it is expected to be in a useful state
        * Often the default state established by Java is not enough
        * The object may need to set values or execute code

* Mechanisms for Establishing Initial State
    * Java provides 3 mechanisms for establishing initial state
        * Field initializers
        * Constructors
        * Initialization blocks

* Field Initial State
    * A field's initial state is established as part of object construction
        * Fields receive a "zero" value by default

* Field initializers
    * Allow us to specify a field's initial value as part of its declaration
        * Can be a simple assignment
        * Can be an equation
        * Can reference other fields
        * Can be a method call

* Constructors
    * Executable code used during object creation to set the initial state
        * Have no return type
        * Every class has at least one constructor
            * If no explicit constructors, Java provides one
        * A class can have multiple constructors
            * Each with a different parameter list

* Chaining constructors
    * One constructor can call another
        * Use the this keyword followed by parameter list
        * Must be the first line

* Constructor visibility
    * Use access modifiers to control constructor visibility
        * Limits what code can perform specific creations

* Initialization blocks
    * Initilization blocks shared across all constructors
        * Executed as if the code were placed at the start of each constructor
        * Enclose statements in brackets outside of any method or constructor

* Initialization and Construction Order
    * Field Initilization * Initilization Block * Constructor

* Summary
    * Objects should be created in some useful state
    * Field initializers provide an initial value as part of the declaration
    * Every class has at least one constructor
        * If no explicit constructor, Java provides one with no arguments
        * You can provide multiple constructors with different argument lists
    * One constructor can call another
        * Call must be first line
    * Initilization blocks share code across constructors
    * Keep the initialization and construction order in mind

## A Closer Look at Parameters

* Parameter Immutability
    * Parameters are passed by making a copy of the value
        * Known as passing "by-value"
    * Changes made to passed value are not visible outside of method
    * Changes made to members of passed class instances are visible outside of method

* Overloading
    * A class may have multiple versions of its constructor or methods
        * Known as "overloading"
    * Each constructor and method must have a unique signature
        * Signature is made up of 3 parts
            * Affected by number of parameters
            * Affected by type of each parameter
            * Affected by name

* Variable Number of Parameters
    * A method can be declared to accept a varying number of parameter values
        * Place an ellipse after parameter type
        * Can only be the last parameter
        * Method receives values as an array

* Summary
    * Parameters are immutable
        * Changes made to passed value are not visible outside of method
        * Changes made to members os passed class instances are visible outside of method
    * A class may have multiple versions of its constructor or methods
        * Each must have a unique signature
        * Sugnature includes name, number of parameters, type of each parameter
    * A method can be declared to accept varying number of parameter values
        * Values received as an array
        * Must be last parameter

## Class Inheritance

* Class Inheritance
    * A class can be declared to inherit from another class
        * Use the "extends" keyword
    * Derived class has the characteristics of basic class
        * Can add specialization
            * Can be assigned to base class types references
            * Fields hide base class fields with same name
            * Methods can override base class methods with same signature

* Object class
    * The object class is the rootof the Java class hierarchy
        * Every class has the characteristics of the Object class
    * Useful for declaring variables, fields and parameters that can reference any class or array instance
    * Defines a number of methods that are inherited by al objects
    * Every class inherits directly or indeirectly from the Object class

* Object class methods
    * clone
        * Create a new object instance that duplicates the current instance
    * hashCode
        * Get a hash code for the current instance
    * getClass
        * Return type information for the current instance
    * finalize
        * Handle special resource cleanup scenarios
    * toString
        * Return string of characters representing the current instance
    * equals
        * Compare another object to the current instancec for equality

* Special reference : super
    * Similar to this, super is an implicit reference to the current object
        * super treats the object as if it is an instance of its base class
        * Useful for accessing base class members that have been overridden

* Control inheritance and overriding
    * By default all classes can be extended and derived classes have the option to use or override inherited methods
        * A class can change these defaults
            * Use final to prevent inheriting and/or overriding
            * Use abstract to require inheriting and/or overriding

* Inheritance and Constructors
    * Constructors are not inherited
        * A base class constructor must always be called
            *  By default, base class' no-argument constructor is called
            * Can explicitly call a base class constructor using super followed by parameter list
                * Must be first line of constructor

* Summary
    * Inheritance allows a new class to be defined with the characteristics of another
        * Use the extend keyword
    * Derived class can override base class methods
        * Optionally use @Override annotation
    * All classes derive from Object class either directly or indirectly
    * By default, object references are only equal when referencing the same instance
        * Can override Object.equals to provide new behavior
    * super accesses current object as if instance of base class
    * final and abstract provide control over class inheritance and method overriding
    * Constructors are not inherited

## More About Data Types

* String class
    * The string class stores a sequence of Unicode characters
        * Stored using UTF-16 encoding
            * Literals are enclosed in double quotes (" ")
            * Values can be concatenated using + and +=
            * String objects are immutable
    * String class methods
        * Length 
            * length
        * String for non-string
            * valueof
        * Create new strings from existing
            * concat
            * replace
            * toLowerCase
            * toUpperCase
            * trim
            * split
        * Formatting
            * format
        * Extract substring
            * chatAt
            * substring
        * Test substring
            * contains
            * endsWith
            * startWith
            * indexOf
            * lastIndexOf
        * Comparison
            * compareTo
            * compareToIgnoreCase
            * isEmpty
            * equals
            * equalsIgnoreCase

* Converting non-string types to strings
    * We often need to convert non-string types into strings
        * String.valueOf provides overrides to handle most types
        * Conversions often happen implicitly
        * Class conversions controlled by the class' toString method

* StringBuilder
    * StringBuilder provides mutable string buffer
        * For best performance pre-size buffer
            * Will automatically grow if needed
        * Most common methods
            * append
            * insert

* Classes vs Primitives
    * Classes provide convenience
        * Common interaction through Object class
        * Fields and methods specific to the type
        * Incurs an overhead cost
    * Primitives provide efficiency
        * Cannot be treated as Object
        * Cannot expose fields or methods
        * Lightweight

* Primitive wrapper classes
    * Capabilities and overhead of classes
    * Hold primitive values
    * All wrapper classes are immutable

* Primitive wrapper class hierarchy
    * Object
        * Boolean
        * Number
            * Byte
            * Short
            * Integer
            * Long
            * Float
            * Double
        * Character

* Wrapper class and primitive conversion
    * Java provides a number of ways to handle conversions
        * Common conversions handled automatically
    * Wrapper classes provide methods for explicit conversions
        * Primitive to wrapper (Boxing)
        * Wrapper to primitive (Unboxing)
        * String to primitive (Parse)

* Wrapper class members
    * Byte, Short, Integer, Long
        * MIN_VALUE
        * MAX_VALUE
        * bitCount
        * toBinaryString
    * Float, Double
        * MIN_VALUE
        * MAX_VALUE
        * isInfinite
        * isNaN
    * Character
        * MIN_VALUE
        * MAX_VALUE
        * isDigit
        * isLetter
    * Boolean
        * TRUE
        * FALSE

* Wrapper class equality
    * Boxing conversions that always return the same wrapper class instance

* Final fields
    * Marking a field as final prevents it from being changed once assigned
        * A simple final field must be set during creation of an object instance
            * Can be set with field initializer, initialization block, or constructor
        * Adding the static modifier makes a final field a named constant
            * Cannot be set by an object instance

* Enumeration types
    * Enumeration types useful for defining a type with a finite list of valid values
        * Declare with enum keyword
        * Provide a comma-separated value list

* Summary
    * String class stores an immutable sequence of Unicode characters
        * Implement toString method to provide conversion to a string
    * StringBuilder class provides an efficient way to manipulate string values
    * Primitive wrapper classes bring class capabilities to primitive values
        * Wrapper classes much less efficient than primitive types
    * Final fields prevent a value from being changed once assigned
        * Simple final fields must be set during object instance creation
        * Static final fields act as named constants
    * Enumeration types useful for defining a type with a finite list of values

## Exceptions and Error Handling

* Error handling with Exceptions
    * Error handling needs to be implicit in application development
        * The traditional approach of checking error codes/ flags is too intursive
    * Exceptions provide a non-intursive way to signal errors
        * try/catch/finally provides a structured way to handle exceptions
            * The try block contains the "normal" code to execute
                * Block executes to completion unless an exception is thrown
            * The catch block contains the error handling code
                * Block executes only if matching exception is thrown
            * The finally block contains cleanup code if needed
                * Runs in all cases following try or catch block

* Exception class hierarchy
    * Object
        * Throwable
            * Error (Virtual machine related errors)
            * Exception
                * Runtime exception (Unchecked exception)
                * Checked exception

* Types exceptions
    * Exceptions can be handled by type
        * Each exception type can have a separate catch block
        * Each catch is tested in order from top to bottom
        * First assignable catch is selected
    * Start catch blocks with most specific exception types

* Exceptions and methods
    * Exceptions propagate up the call stack
        * Can cross method boundaries
    * Exceptions are part of a methods's contract
        * Method is responsible for any checked exceptions that might occur
            * Catch the exception
            * Document that the exception might occur
                * use the throws clause

* Exceptions and method overriding
    * The throws clause of an overriding method must be compatible with the throws clause of the overriden method
        * Can exclude exceptions
        * Can have the same exception
        * Can have a derived exception

* Throwing exceptions
    * Our code can throw exceptions (Using the throw keyword)
        * Must create exception instance before throwing
            * Most exception classes provide a constructor that accepts a String message or other detail
            * When caused by another exception, include originating exception
                * All exception classes support initCause method
                * Many provide a constructor that accepts the originating exception

* Creating a custom exception type
    * In most cases better to use esisting exception type
    * Normally inherit directly from Exception class
        * Makes them checked exceptions
        * Constructors are often their only members
            * Mostly required functionality is inherited
            * Constructor that accepts required detail
            * Constructor that accepts required detaila and originating exception

* Summary
    * Exceptions provide a non-intrusive way to signal errors
    * try/catch/finally provide a structured way to handle exceptions
    * Exceptions are caught by type
        * Can have separate vatch statement for differing exception types
        * Catch from most specific type to least specific
    * Raise exceptions using throw
    * Methods must declare any unhandled checked exceptions using throws
    * Can create custom exception types
        * Normally inherit from Exception

## Working with Packages

* What is a Package?
    * A package is a group of related types
        * Create a namespace
        *  Provide an access boundary
        * Act as a unit of distribution

* Declaring packages
    * Each source file identifies the associated package
        * Use the package keyword
        * Package declaration must appear before any type declarations
        * Applies to all types within that source file

* Package creates a Namespace
    * Package name is part of the type-name
        * Convention creates unique package name
            * Follows reverse domain name structure
        * Type name is qualified by package name

* Detemnining a Type's Package
    * Compiler needs to know each type's package
        * Explicitly qualifying each type is impractical
        * Java offers several alternatives to explicitly qualifying types
            * Allows use of a type's simple name in code
            * Types in current package do not need to be qualified
            * Types in the java.lang package do no need to be qualified
            * Use type imports

* Type imports
    * Type imports guide compiler to map simple names to qualified names (use import keyword)
        * Single type import
            * Provides mapping for a single type
                * Preferred way to import types
                * Most modern IDEs will add automatically
        * Import on demand
            * Provides mapping for all types in a package
                * Use with caution
                * Exposes code to potential breakage from changes in referenced packages

* Limiting access to Package Content
    * Packages can serve as an access boundary
        * Often referred to as package private
        * Useful for creatingtypes and features to support functionality provided by the package
            * Types and features are not meant to be used stand-alone
            * Can apply to a type
                * Entire type is inaccessible outside of the package
            * Can apply to type members
                * Specific members of an otherwise accessible type are inaccessible outside of the package

* Access modifiers
    * public
    * private
    * protected

* Packages provide a Unit of distribution
    * packages provide a predictable software structure
        * Class files organized in hierarchical folders reflecting the package name
            * Each part of the package name is a separate folder

* Archive files
    * Package folder structure can be placed into an acrhive file (jar file)
        * Places package fo,der structure into a single file
            * Optionally includes a manifest providing information regarding archive content
                * List of name-vale pairs
                * Commonly used to define startup class

* Summary
    * A package is a group of related types
        * Package declaration must appear in source file before any type declarations
    * Type name qualified by package name
        * Use import statements to map simple names to qualified names
    * Packages serve as an access boundary
    * Packages simplify distribution
        * Types organized hierarchically according to the package name
        * Archive files store package hierarchy in a single file

## Creating abstract relationships with Interfaces

* What is an interface
    * An interface defines a contract and provides no implementation
        * Classes implement interfaces
            * Express that the class conforms to the contract
            * Interfaces dont limit other aspects of the class implementation
            * Some interfaces require additional type information (like generics)
            * Classes are free to implement multiple interfaces

* Summary
    * An interface defines a contract
        * Provides no implementation
        * Can include methods and constants
    * Classes implement interfaces
        * Classes are able to implement multiple interfaces
    * Interfaces are able to extend other interfaces
        * Implementing an extended interface implicitly implements the base

## Stitic members, nested types, and anonymous classes

* Static members
    * Static members are shared class-wide
    * Declared using the static keyword
    * Field
        * A value not associated with a specific instance
        * All instance access the same value
    * Method
        * Performs an action not tied to a specific instance
        * Can access static fields only
    * Static import
        * Provides short hand for accessing static members

* Statuc initialization blocks
    * Static initialization blocks perform one-time type initialization
    * Statements enclosed in brackets outside of any method or constructor
        * Cannot access instance members
        * Must handle all checked exceptions

* Nested types
    * A nested type is a type declared within another type
        * Classes can be declared within classes and interfaces
        * Interfaces can be declared within classes and interfaces
    * Nested types are members od the enclosing type
        * private members of the enclosing type are visible to the nested type
    * Nested types support all member access modifiers
        * public
        * package private
        * protected
        * private
    * Nested types serve differing purposes
        * Structure and scoping
            * Static classes nested within classes
            * All classes nested within interfaces
            * All nested interfaces
        * Inner classes
            * Non-static classes nested within classes

* Anonymous classes
    * Anonymous classes are declared as part of the creation
    * Anonymous classes are inner classes
    * Create as if you are constructing an instance of the interface or base class
        * Place opening and closing brackets after the interface or base class
        * place implementation code within brackets

* Summary
    * Static methods and fields are shared class-wide
        * Not associated with an individual instance
    * Static initialization blocks provide one-time type declaration
    * A nested tpe is a type declared within another type
        * Can be used to provide structure and scoping
        * Inner classes create an association between nested and enclosing instances
    * Anonymous classes are declared as part of their creation
        * Useful for simple interface implementations and class extensions