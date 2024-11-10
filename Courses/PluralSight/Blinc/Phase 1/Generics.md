
## The What and Why of Java Generics

* Introduction
    * Generics stop runtime errors at compile time

## Java's Generic Collections and Friends

* Interface -----> Implementation
    * Multiple Data Structure -----> Specific Data Structure
    * Functional Characteristics -----> Performance Characteristics
    * Prefer as Variable Type -----> Concrete and Instantiable
    * Often has a popular implementation

* Types of Collections
    * Lists
    * Sets
    * Maps

## Generics Classes and Interfaces

* Implementing a Generic Type
    * AgeComparator implements Comparator<Person>

* Passing a parameter to a generic Type
	* Reverser<T> implements Comparator<T>

* Type Bounds
	* SortedPair<T extends Comparable<T>>

## Generics on Methods

* public static <T> T min(List<T> values, Comparator<T> comparator)

## Wildcards

* Types of wildcards
    * Upper bounded (List<? extends Cls>)
    * Lower bounded (List<? super Cls>)
    * Unbounded (List<?>)