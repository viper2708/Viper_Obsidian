## Introducing the Java Platform

* The Java Platform
	* Java
		* Programming language
		* Runtime environment
		* Standard library
		
## Adopting Java

* Philosophy of Java
	* Portability
		* Write once run anywhere
	* Optimized for readability
		* Reading code is more important than writing code
		* Understandable code over clever code
	* Conservative of new features
		* Planning for the next 20 years
		* 'First do no harm'
		* Developer productivity
		* Maintaining simplicity
	* Backward compatibility
		* Existing code on new JVMs
		-> Controlled deprecation
	* Openness : Specification process
		* Java Community Process(JCP) specifies the platform
		* Vendor and community participation
		* Many non-Oracle implementations : IBM, Eclipse
	* Openness : Open source
		* OpenJDK project
		* GPL2 licensed
		* Experimental subprojects
	
* Choosing Java - When and Why
	* Popularity
		* Estimated 10 million Java developers
			* Web applications
			* Backend services
			* Data-intensive applications
	* Scalable developement
		* Hierarchical and structured codebases
		* Established coding practices
		* String tooling
		* Wealth of libraries
	* Productivity
		* Type system
			* Catch bugs early
		* Managed runtime
			* Automatic memory management
			* Garbage collection
			* Multi-threading
	* Performance
		* Just-in-time compilztion
		* Specialized to underlying hardware
		* Based on actual execution of code
		
* Choosing Java - When is Java not the right choice?
	* Real-time systems
	* Tight operating system integration
	* Quick prototyping
	* For developers who want cutting-edge languages
	
* Comparing Java : C#/.Net
	* Similarity
		* Common language runtime
		* Managed language
		* Open source
	* Difference
		* Faster moving language
		* Only recently cross-platform
		* Ecosystem dominated by Microsoft
		
* Comparing Java : C/C++
	* Similarity
		* Java syntax inspired by C
		* C++ also Object-oriented
	* Difference
		* Unmanaged language
		* More language features
		* Compiled to native code
		
* Comparing Java : Python
	-> Similarity
		* High-level managed language
		* Open ecosystem
	* Difference
		* Interpreted language
		* Not statically typed
		* Python 2/3 split
		
* Comparing Java : JavaScript
	* Similarity
		* Managed runtime : NodeJS
		* Somewhat syntactically similar
	* Difference
		* Interpreted language
		* Not statically typed
		* Single-threaded
		
## From Desktop to Enterprise Java to the Cloud

* Desktop java
	* Single machine, interactive applications
	* AWT
		* Abstract Windowing Toolkit
		* native OS Controls
		* Simple graphics primitives
	* Swing
		* Pue Java GUI
		* Cross-platform look and feels
		* Model-view-controller
	* JavaFX
		* Declarative UIs: FXML
		* Advanced components
		* Skinnable with CSS
		* 3D graphics
		
* Enterprise Java
	* APIs
		* Data persistence
		* Web applications
		* Security
		* Messaging
		* JSON/XML handling
	* Java EE application servers
		* Wildfly (RedHat)
		* WebSphere (IBM)
		* WebLogic (Oracle)
		* Tomcat (Apache)
	* Future of Java EE
		* Java EE 8 last release
		* Move to Eclipse Foundation (is now Jakarta EE)
		* Is being replaced by Spring Framework
		
* Java In The Cloud
	* Microframeworks
		* Spring Boot
		* MicroProfile
		* Vert.x
		* Play Framework
		
* Android
	* Java Bytecode is converted to DEX (Dalvik Executable Format)
	* JVM is replaced by Dalvik Virtual Machine
	
## Popular Java Libraries

* Spring Framework
	* J2EE Developement without EJB
	* Dependency injection
		* Decoupling of classes
		* Flexible composition
		* Cross-cutting concerns
	* Dependency injection container
	* Integration with data-access technologies
	* Integration with Java EE technologies
	* Spring WebFlux
	
* Commonly used Java libraries
	* Utility libraries
		* Google Guava
			* Additional collections
			* Caching
			* IO helpers
		* Apache Commons
			* Collections
			* CSV
			* IO (and many more)
		* Apache Log4J
			* Structured application logging
	* Distributed System Libraries
		* Netty
			* High-performance networking
		* Akka
			* Actor model for concurrency
			* Clustering and distribution
		* RxJava
			* Reactive programming
			* Async and event-based model
		* Apache Camel
			* Enterprise application integration
			* Many transports and connectors
	* Data-access libraries
		* JDBC
			* MySQL driver
			* postGres driver
			* Oracle driver
			* H2 driver
		* ORMs
			* Hibernate
			* EclipseLink
		* SQL DSLs
			* jOOQ
			* QueryDSL
			
* Java-based data processing
	* Big Data : Processing
		* Apache Hadoop
		* Apache Spark
		* DL4J : Deep Learning for Java
	* Big Data : Storage
		* Cassandra
		* Neo4J
		* ElastiSearch
		* Hadoop Distributed File System
		
## Practices and Common Tools

* IDEs
	* Code completion
	* Inline documentation
	* Debugging
	* Examples of IDEs
		* Eclipse
		* IntelliJ

* Unit Testing
	* Write code to test code
	* Individual classes and methods (JUnit)
	* Isolate dependencies : mocking (Mockito)
	
* Build Tools
	* Repeatable builds
	* Managing multiple modules
	* Managing external dependencies
	* Running tests
	* Example of build tools
		* Maven
		* Gradle
			* Define builds with Groovy scripts
			* Incremental builds
			* Maven default source layout
			* Can use Maven Central

* Continuouos integration and Quality Controls
	* CI Server
		* Build Code
		* Run tests
		* Analyse code
		* Deploy
	* CI server examples
		* Jenkins
	* Static code analysis
		* Checkstyle
		* Spotbugs
		* PMD
		* SonarQube : Continuous inspection
		
## Examining alternative JVM languages

* Why?
	* Productive
	* Familiarity
	* Different paradigms

* Groovy
	* Dynamic scripting language for the JVM
	* Interpreted or compiled
	* Opt-in type system
	* Concise but still close to Java

* Scala
	* Combines OO programming with Functional programming
	* Compiled language
	* Extensive type system
	* Akka, Spark written in Scala
	
* Kotlin
	* A 'better Java'
	* Seamless Java interop
	* Endorsed by Google for Android developement
	* Also runs in the browser