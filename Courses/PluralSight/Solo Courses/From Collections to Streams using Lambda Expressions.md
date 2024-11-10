## Lambda Expressions and Functional Interfaces

* What we normally do in Java
	* We wrote code in an anonymous class
	* And we passed it to another piece of code
	* That executed it later
	* And in another context (thread)
	* We passed code as a parameter
	* And we used anonymous class, because it is the only way to do it in Java
	
* Converting legacy code to lambda
	* Example 1:
		* Comparator in legacy code
```
        Comparator<String> comparator = new Comparator<String> {
            	public int compare(String s1, String s2){
                		return Integer.compare(s1.length(), s2.length());
            	}
    	}
```
		* In Lambda expressions
```
        Comparator<String> comparator =
            	(String s1, String s2) ->
                		Integer.compare(s1.length(), s2.length());
```
						
* Some remarks
	* One can put modifiers on the parameters of a lambda expressions
		* The final keyword
		* Annotations
	* It is not possible to specify the returned type of a lambda expression
	* The types of the parameters can also be omitted
	
* Method references
	* Alternate syntax for lambda expressions
	* Example 1
		* Function<Person,Integer> f = person -> person.getAge();
		* Function<Person,Integer> f = Person::getAge ;
	* Example 2
		* BinaryOperator<Integer> sum = (i1,i2) -> Integer.sum(i1,i2);
		* BinaryOperator<Integer> sum = Integer::sum;
	* Example 3
		* Consumer<String> printer = s -> System.out.println(s);
		* Consumer<String> printer = System.out::println ;
		
* How to create new API
	* Lambdas + default methods + static methods
	
## Writing data processing functions with lambda expressions

* Functional interface
	* A lambda expression is an instance of a functional interface
		* Example :
				public interface Predicate<T> {
					boolean test(T t);
				}
	* At this point, a functional interface is an interface with only one method.
	
* How does it work under the hood?
	* The Java 8 compiler is smart!
		* The interface is functional, so there is only one method to implement.
		* The type of the variable gives the type of the lambda expression
		* The parameters and return types must be compatible.
		* The same for exceptions, if any.

* Functional interface : Definition
	* A functional interface is an interface:
		* With only one abstract method
		* Default methods do not count
		* Static methods do not count
		* Methods from the Object class do not count
	* A functional interface may be annotated with @FunctionalInterface
		* It is not mandatory, for legacy reasons
		* The compiler will tell us if an annotated interface is functional or not
		
* The java.util.function.Package
	* The functional interface toolbox
		* A new package from Java 8, with the most useful functional interfaces
		* There are 43 fo them.
		* Four categories:
			* The Consumers
			* The Supplier
			* The Functions
			* The Predicates
	* The Consumers
		* A consumer consumes an object, and does not return anything.
	* The Supplier
		* A supplier provides and object, takes no parameter
	* The Functions
		* A function takes an object and returns another object
	* The Predicates
		* A predicate takes an object ans returns a boolean
		
* Functional interfaces for Primitive types
	* Other functional interfaces have been defined, for instance
		* IntPredicate
		* IntFunction
		* IntToDoubleFunction
		
## Data Processing using Lambdas and the Collection Framework

* Iterable, Collection, List
	* On iterable
		* forEach
	* On collection
		* removeIf
	* On List interface
		* replaceAll
		* sort

* Map interface
	* forEach
	* getOrDefault
	* putIfAbsent
	* replace
	* replaceAll
	* remove
	* compute
		* Computes a value from:
			* the key passed as a parameter, that may not be in the map
			* the value that may be associated with that key, or null
			* the lambda that will compute the remapping
	* computeIfAbsent
	* computeIfPresent
	* merge
		* If the passed key is not in the map: adds the key/ value pair to the map
		* If the passed key is in the map
			* merge the existing value with the passed value using the lambda expression
			* note that the remapping takes a pair of values and return a new value
			
## Implementing Map Filter Reduce using Lambdas and Collections

* Contains 3 parts:
	* Map
	* Filter
	* Reduce
	
* Parallelization
	* The algorithm for sum of array of integers can be easily computed in parallel
	* But there is a condition:
			Red(a,Red(b,c)) = Red(Red(a,b),c)
	* It is called associativity
	* If a lambda is passed as a parameter is not associative, then the following is going to happen?
		* The code will compile properly
		* It will execute properly
		* A result will be returned
		* But it will be false
		
* Reduction of singletons
	* The reduction should have an identity element
	* Not all operations have one (max)
	
* Conclusion on the Reduction step
	* The reduction is critical
	* It is very easy to write a non-associative reduction
	* It is very easy to write a reduction with no identity element
	
## The Stream API

* Stream - definitions
	* A stream does not hold any data
		* It pulls the data it processes from a source
	* A stream does not modify the data it processes
		* Because we want to process the data in parallel with no visibility issues
	* The source may be unbounded
		* But most of the time, it only means that the size of this source is not known at build time
		
* How to build streams
	* There are many patterns for that
		* Stream.empty()	// an empty Stream
		* Stream.of("one")	// a singleton Stream
		* Stream.of("one", "two", "three")	// a Stream with several elements
		* Stream.generate(() -> "one");	// a constant Stream
		* Stream.iterate("+", s -> s + "+");	// 	a growing Stream
		* ThreadLocalRandom.current().ints();	//	a random Stream
		* IntStream stream = "hello".chars();	//	a Stream on the letters of a String
		* Stream<String> words = Pattern.compile("[^\\p{javaLetter}]").splitAsStream(book);	// a Stream on a regular expression
		* Stream<String> lines = Files.lines(path);	//	a Stream of the lines of a text file
	* The StreamBuilder patterns
		* Stream.Builder<String> builder = Stream.builder();
			builder.add("one).add("two").add("three");
			builder.accept("four");
			Stream<String> stream = builder.build();

* First patterns
	* Map/filter/reduce on a stream of people
		* //	a first way of writing it
```			
        persons.stream()							//	Stream<Person>
			.map(p -> p.getAge())				//	Stream<Integer>
			.filter(age -> age > 20)			//	Stream<Integer>
			.forEach(System.out::println);
```


		*  A map() call can change the type of a stream
		*  A filter() call does not change the type of a stream

* Intermediate and Terminal calls
	* The peek() call can be used for logging purposes
	* peek() is an intermediate operation
	* forEach() is a terminal operation
	* A terminal operation must be called to trigger the processing of a Stream
		* No terminal operation = no data is ever processed
		
* How to recognise a terminal call?
	* A call that returns a Stream is an intermediate call
	* A call that returns something else, or void is a terminal call that triggers the processing
	
* Select ranges of data in a Stream
	* skip()
	* limit()
	
* Reduction
	* Match reduction
		* Three types of matchers : anyMatch(), allMatch(), noneMatch()
		* They are terminal operations that return a boolean
		* These three matchers may not evaluate the predicate for all the elementa
		* They are called short-circuiting terminal operations
	* Find reduction
		* There are two types of find reductions : findFirst(), findAny()
		* They might have nothing to return:
			* If the stream is empty
			* Or if there is no value that matches the predicate
		* So they both return an Optional, that can be empty
	* Reduce reduction
		* There are three types of reduce reduction
		* If no identity element is provided, then an Optional is returned
		* Associativity is assumed for the reduction function, but not enforced