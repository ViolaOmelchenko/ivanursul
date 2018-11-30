---
title: "Open Source Collections in Java"
date: 2018-11-21 00:00:00
---

### <a href="#openSourceCollectionsInJava" name="openSourceCollectionsInJava"><i class="fa fa-link anchor" aria-hidden="true"></i></a> Open Source Collections in Java

Welcome to the blog about *Collections* in Java. In this article, I'm going to introduce a concept of *Apache Commons, Guava, Fastutil, Trove, and Goldman Sachs Collections libraries*, as well as their Interfaces, Classes, and Methods supported by examples. I hope you will enjoy the content and gain some new experience.

The Collection in Java provides an architecture to manipulate with the group of objects. The collections provide:
* All the operations that are performed on data, such as searching, sorting, insertion, and deletion
* Interfaces such as <a href="https://programiranjepro.github.io/ivanursul/articles/java/lists">Lists</a>, <a href="https://programiranjepro.github.io/ivanursul/articles/java/sets">Sets</a>, <a href="https://programiranjepro.github.io/ivanursul/articles/java/queues">Queues</a>, and <a href="https://programiranjepro.github.io/ivanursul/articles/java/deques">Deques</a>
* Classes such as <a href="https://programiranjepro.github.io/ivanursul/articles/java/lists">ArrayList<a/>, <a href="https://programiranjepro.github.io/ivanursul/articles/java/lists">LinkedList</a>, <a href="https://programiranjepro.github.io/ivanursul/articles/java/lists">Vector</a>, <a href="https://programiranjepro.github.io/ivanursul/articles/java/lists">Stack</a>, <a href="https://programiranjepro.github.io/ivanursul/articles/java/queues">PriorityQueue</a>, <a href="https://programiranjepro.github.io/ivanursul/articles/java/sets">HashSet</a>, <a href="https://programiranjepro.github.io/ivanursul/articles/java/sets">LinkedHashSet</a>, and <a href="https://programiranjepro.github.io/ivanursul/articles/java/sets"> TreeSet</a>

More about these points I'll explain below, and they will be categorized by different libraries.

### <a href="#apacheCommonsCollections" name="apacheCommonsCollections"><i class="fa fa-link anchor" aria-hidden="true"></i></a> Apache Commons Collections

<a href="https://commons.apache.org/proper/commons-collections/">Apache Commons Collections</a> provide the following features:
* <a href="https://commons.apache.org/proper/commons-collections/javadocs/api-4.2/org/apache/commons/collections4/Bag.html">Bag</a> Interface with a number of copies of each object
* <a href="https://commons.apache.org/proper/commons-collections/javadocs/api-4.2/org/apache/commons/collections4/BidiMap.html">BidiMap</a> Interface provides Bi-Directional Maps that can be looked up both, from value to a key, likewise a key to value
* <a href="https://commons.apache.org/proper/commons-collections/javadocs/api-4.2/org/apache/commons/collections4/MapIterator.html">MapIterator</a> Interface provides iteration over maps
* *Transforming Decorators* modify each object when it's added to the collection
* *Composite Collections* make multiple collections look alike (uniformly)
* *Ordered Maps* and *Sets* retain the order, in which the elements are added in
* *Reference Map* allows keys and/or values to be garbage collected under a close control

**How to use a library:**
To use this library, all you have to do is to insert *dependency* code into your project. Assuming that you know how to use Maven, you can find the code on the <a href="https://mvnrepository.com/artifact/org.apache.commons/commons-collections4/4.1">official website</a>:
```
<!-- https://mvnrepository.com/artifact/org.apache.commons/commons-collections4 -->
<dependency>
    <groupId>org.apache.commons</groupId>
    <artifactId>commons-collections4</artifactId>
    <version>4.1</version>
</dependency>
```

More information about Maven, and how to use it, you can find in this <a href="https://ivanursul.com/articles/java/maven">article</a>.

The other way you can apply *Apache Commons Collections* is throught downloading the library from the <a href="https://commons.apache.org/proper/commons-collections/javadocs/api-4.2/index.html">official website</a>. When applying this one, you need to extract your commons-collections4-4.2-bin.tar.gz with <a href="https://www.win-rar.com/start.html?&L=0">WinRar</a> and open your environment (Eclipse). After you create a project, go to the Build Path - Configure Build Path... - choose Libraries - click Add External JARs... - finally, locate your extracted folder and import all the jars.

**Synchronization:**
*Apache Commons Collections* and Java collections have a similar synchronization solution. The bulk of the various implementations of Collections, Maps and Bags are not thread safe without additional synchronization, therefore **synchronizeXXX** method on Collections is recommended for these implementations in order to be synchronized in a multithreaded application use.

Below, you can find some Interfaces from Package org.apache.commons.collections4, supported by *Apache Commons Collections*. For further information feel free to check the <a href="https://commons.apache.org/proper/commons-collections/javadocs/api-4.2/index.html">official website</a>:
<table>
  <tr>
    <th>Interfaces</th>
    <th>Description</th> 
  </tr>
  <tr>
    <td>Bag<&#xfeff;E></td>
    <td>A Collection that counts the number of times an object appears in the collection</td>
  </tr>
  <tr>
    <td>SortedBag<&#xfeff;E></td>
    <td>Type of Bag that maintains a sorted order among its unique representative members</td>
  </tr>
  <tr>
    <td>BidiMap<&#xfeff;K, V></td>
    <td>A Map that allows Bi-Directional lookup between key and values</td> 
  </tr>
  <tr>
    <td>OrderedBidiMap<&#xfeff;K, V></td>
    <td>A Map that allows Bi-Directional lookup between key and values and retains and provides access to an ordering</td>
  </tr>  
  <tr>
    <td>SortedBidiMap<&#xfeff;K, V></td>
    <td>A Map that allows bidirectional lookup between key and values and retains both keys and values in sorted order</td>
  </tr>
  <tr>
    <td>Equator<&#xfeff;T></td>
    <td>A function which determines equality between objects of type T</td>
  </tr>
  <tr>
    <td>Get<&#xfeff;K, V></td>
    <td>The "read" subset of the Map interface</td>
  </tr>
  <tr>
    <td>IterableGet<&#xfeff;K, V></td>
    <td>The "read" subset of the Map interface</td>
  </tr>
  <tr>
    <td>IterableMap<&#xfeff;K, V></td>
    <td>A Map that can be iterated directly without creating an entry set</td>
  </tr>
  <tr>
    <td>KeyValue<&#xfeff;K, V></td>
    <td>A key-value pair</td>
  </tr>
  <tr>
    <td>ListValuedMap<&#xfeff;K, V></td>
    <td>A Map that holds a list of values against each key</td>
  </tr>
  <tr>
    <td>MultiValuedMap<&#xfeff;K, V></td>
    <td>A Map that holds a collection of values against each key</td>
  </tr>
  <tr>
    <td>MultiSet<&#xfeff;E></td>
    <td>A Collection that counts the number of times an object appears in the collection</td>
  </tr> 
  <tr>
    <td>Unmodifiable</td>
    <td>Marker interface for collections, maps, and iterators that are unmodifiable</td>
  </tr>            
</table>

Below, presented some Classes from Package org.apache.commons.collections4 supported by *Apache Commons Collections*. For further information feel free to check the <a href="https://docs.oracle.com/javase/9/docs/api/java/util/List.html">official website</a>:
<table>
  <tr>
    <th>Classes</th>
    <th>Description</th> 
  </tr>
  <tr>
    <td>BagUtils</td>
    <td>Provides utility methods and decorators for Bag and SortedBag instances</td>
  </tr> 
  <tr>
    <td>CollectionUtils</td>
    <td>Provides utility methods and decorators for Collection instances</td>
  </tr>
  <tr>
    <td>EnumerationUtils</td>
    <td>Provides utility methods for Enumeration instances</td>
  </tr>
  <tr>
    <td>ListUtils</td>
    <td>Provides utility methods and decorators for List instances</td>
  </tr>
  <tr>
    <td>MapUtils</td>
    <td>Provides utility methods and decorators for Map and SortedMap instances</td>
  </tr>
  <tr>
    <td>QueueUtils</td>
    <td>Provides utility methods and decorators for Queue instances</td>
  </tr>
  <tr>
    <td>SetUtils</td>
    <td>Provides utility methods and decorators for Set and SortedSet instances</td>
  </tr>
</table>

In *Apache Commons Collections* exist 19 Packages with diverse Interfaces, Classes, and Methods. We shared only a few Interfaces and Classes from one Package and encourage you to check the others on the <a href="https://docs.oracle.com/javase/9/docs/api/java/util/List.html">official website</a>, therefore we can focus more on the practical examples.

**Example - Ignore Null values**
```
      List<String> list = new LinkedList<String>();
		
      list.add("Apple");
      CollectionUtils.addIgnoreNull(list, "Avocado");
      list.add("Orange");
      CollectionUtils.addIgnoreNull(list, null);
      list.add("Banana");
	    
      System.out.println(list);

      if(list.contains(null)) {
         System.out.println("Null value is present");
      } else {
         System.out.println("Null value is not present");
      }
       /*
      	As you can see at the end, in the list NULL value does not exist.
	Method addIgnoreNull is very useful if you want to forbid NULL values in your lists.
      */
```

**Example - Merging lists**
```
	List<String> list1 = new LinkedList<String>();
   	List<String> list2 = new LinkedList<String>();
	   		
	list1.add("Banana");
	list1.add("Apple");
	  		
	list2.add("Orange");
	   
	List<String> sortedList = CollectionUtils.collate(list1, list2);
	    
	System.out.println(sortedList);
			
	//This method makes it easier to combine multiple lists	
```

**Example - Bags usage**
```
      //Create Bag
      Bag<String> bag = new HashBag<>();

      //Add "Banana" five times to the bag
      bag.add("Banana", 5);
      
      //Add "Orange" one time to the bag
      bag.add("Orange");
      
      //Add "Apple" two times to the bag
      bag.add("Apple", 2);
      
      //Show content of the Bag
      System.out.println("Bag content: " + bag);
      
      //Show the set of unique values in the bag
      System.out.println("Unique values: " + bag.uniqueSet());
      
      //Show the number of "Apple" present in bag
      System.out.println("Apple is presented " + bag.getCount("Apple") + " times.");
      
      //Remove 2 appearances of "Banana" from the bag
      bag.remove("Banana", 2);
      
      //Show content of the Bag
      System.out.println("Content of the bag after removed 2 appearances of Banana: " + bag);
      
      //Show the number of "Banana" present in bag
      System.out.println("Banana is present " + bag.getCount("Banana") + " times.");
```

**Example - BidiMap usage**
```
      //Create BidiMap
      BidiMap<String, String> bidiMap = new TreeBidiMap<>();

      //Add keys and values
      bidiMap.put("Banana", "fruit");
      bidiMap.put("BMW", "car");
      bidiMap.put("Red", "color");
      
      //Show BidiMap content
      System.out.println("Content of bidiMap: " + bidiMap);
      
      //Show the value of Banana key
      System.out.println("The value of Banana key is: " + bidiMap.get("Banana")); 
      
      //Show the key of fruit value
      System.out.println("The key of fruit value is: " + bidiMap.getKey("fruit"));
  
      //Remove by value fruit
      bidiMap.removeValue("fruit");
      System.out.println("BidiMap content after removed value: " + bidiMap);
      
      //Remove by key BMW
      bidiMap.remove("BMW");
      System.out.println("BidiMap content after removed key: " + bidiMap);
        
      bidiMap.put("Banana", "fruit");
      bidiMap.put("BMW", "car");
      System.out.println(bidiMap);
      
      //Create new BidiMap to show method used to replace the site of key/value
      BidiMap<String, String> inversedBidiMap = bidiMap.inverseBidiMap();  
      System.out.println("Inversed BidiMap: " + inversedBidiMap);
```

**Example - MapIterator usage**
```
        //Create IterableMap
	IterableMap<String, String> iterableMap = new HashedMap<>();

	//Add keys and values
	iterableMap.put("Banana", "fruit");
	iterableMap.put("BMW", "car");
	iterableMap.put("Red", "color");

	//Create MapIterator
	MapIterator<String, String> mapIterator = iterableMap.mapIterator();
	      
	//Go through MapIterator
	while (mapIterator.hasNext()) {
	    	  
		//Put a key in variable key with type Object
	        Object key = mapIterator.next();
	          
	        //Put value in variable value with type Object
	        Object value = mapIterator.getValue();
	
	        //Show content of key and value in this iteration
	        System.out.println("Key is: " + key + ", and value is: " + value);
	}
      
	//Show IterableMap content
	System.out.println("Content of the IterableMap is: " + iterableMap);
	      
	//Remove key "Banana"
	iterableMap.remove("Banana");
	System.out.println("Content of the IterableMap after change is: " + iterableMap);
	      
	//Change the value of key "BMW"
	iterableMap.replace("BMW", "color");
	System.out.println("Content of the IterableMap after change is: " + iterableMap);
```

### <a href="#guava" name="guava"><i class="fa fa-link anchor" aria-hidden="true"></i></a> Guava - Google's Collections

As well as Apache Commons Collections, *Guava* represents an open source set of libraries. *Guava* is created by Google and provides the following benefits:
* It helps in reducing coding errors and makes it easy to maintain the code,
* It is reliable, fast, and efficient,
* Collections include immutable Collections, Bidirectional Maps, Multisets, Multimaps, Tables, and many more,
* Strings provides Classes like <a href="https://github.com/google/guava/wiki/StringsExplained">Splitter</a>, <a href="https://github.com/google/guava/wiki/StringsExplained">Joiner</a> <a href="https://github.com/google/guava/wiki/StringsExplained">CharMatcher</a>, etc.,
* <a href="https://github.com/google/guava/wiki/OrderingExplained">Comparator</a> Class for ordering,
* Graphs, Caching, operations on primitive types, that are not provided by JDK, simplified I/O and more.

*Guava* provides static methods to facilitate the declaration of a variable like it's mentioned below:
```
List<String> list = new ArrayList<String>();
list.add("Banana");
list.add("Apple");
list.add("Avocado");
list.add("Orange");

OR

List<String> list2 = Lists.newArrayList("Banana", "Apple", "Avocado", "Orange");
```
```
List<Map<String, String>> map = new LinkedList<Map<String, String>>();

OR

List<Map<String, String>> map2 = Lists.newLinkedList();
```
Now you can sum up all the information and conclude, that writing a code is much easier with *Guava*.

**How to use a library:**
*Dependancy* for Maven's library importation is listed hereafter:
```
<!-- https://mvnrepository.com/artifact/com.google.guava/guava -->
<dependency>
    <groupId>com.google.guava</groupId>
    <artifactId>guava</artifactId>
    <version>19.0</version>
</dependency>
```

The information about Maven, and how to use it, you can read in this <a href="https://ivanursul.com/articles/java/maven">article</a>.

Below, you can find some Interfaces from Package com.google.common.collect, supported by *Guava*. For further information feel free to check the <a href="https://google.github.io/guava/releases/snapshot-jre/api/docs/">official website</a>:
<table>
  <tr>
    <th>Interfaces</th>
    <th>Description</th> 
  </tr>
  <tr>
    <td>BiMap<&#xfeff;K, V></td>
    <td>A Bidirectional Map that preserves the uniqueness of its values and keys</td>
  </tr>
  <tr>
    <td>ListMultimap<&#xfeff;K, V></td>
    <td>A Multimap that can hold duplicate key-value pairs and maintains the insertion ordering of values for a given key</td>
  </tr>
  <tr>
    <td>Multimap<&#xfeff;K, V></td>
    <td>A Collection that maps keys to values, similar to Map, but each key may be associated with multiple values</td> 
  </tr>
  <tr>
    <td>Multiset<&#xfeff;E></td>
    <td>A Collection that supports order-independent equality, like Set, but may have duplicate elements</td>
  </tr>  
  <tr>
    <td>Table<&#xfeff;R, C, V></td>
    <td>A Collection that associates an ordered pair of keys, called a row key and a column key, with a single value</td>
  </tr>           
</table>

Below, you can find some Classes from Package com.google.common.collect supported by *Guava*. For further information feel free to check the <a href="https://google.github.io/guava/releases/snapshot-jre/api/docs/">official website</a>:
<table>
  <tr>
    <th>Classes</th>
    <th>Description</th> 
  </tr>
  <tr>
    <td>ArrayListMultimap<&#xfeff;K, V></td>
    <td>A Multimap that uses an ArrayList to store the values for a given key</td>
  </tr> 
  <tr>
    <td>ArrayTable<&#xfeff;R, C, V></td>
    <td>Fixed-size Table implementation backed by a two-dimensional array</td>
  </tr>
  <tr>
    <td>ImmutableBiMap<&#xfeff;K, V></td>
    <td>A BiMap whose content will never change</td>
  </tr>
  <tr>
    <td>ImmutableList<&#xfeff;E></td>
    <td>A List whose content will never change</td>
  </tr>
  <tr>
    <td>LinkedListMultimap<&#xfeff;K, V></td>
    <td>A ListMultimap that supports deterministic iteration order for both keys and values</td>
  </tr>
  <tr>
    <td>Ordering<&#xfeff;T></td>
    <td>A Comparator with additional methods to support common operations</td>
  </tr>  
</table>

In *Guava* exist 16 Packages with numerous Interfaces, Classes, and Methods. We shared only a few Interfaces and Classes from one Package and encourage you to check the others on the <a href="https://google.github.io/guava/releases/snapshot-jre/api/docs/">official website</a>.

**Example - MultiSet**
```
/*
A Multiset is not a Set, it represents a bag which contains sets of elements.
*/

   // Create Multiset
   Multiset<String> multiSet = HashMultiset.create();
	   
   // Add values
   multiSet.add("Banana");
   multiSet.add("Apple");
   multiSet.add("Orange");
   multiSet.add("Avocado");
   multiSet.add("Banana");
	   
   System.out.println("Number of elements in multiSet: " + multiSet.size());

   System.out.println("Number of Banana in multiSet: " + multiSet.count("Banana"));
	   
   // Delete element Banana
   multiSet.remove("Banana");
   System.out.println("Number of elements in multiSet: " + multiSet.size());
   System.out.println("Number of Banana in multiSet: " + multiSet.count("Banana"));
```

**Example - MultiMap**
```
/*
A MultiMap is just like a Map, although it may contain duplicate keys and provides an easy way to handle mapping from keys to a collection of values.
*/

       //Create MultiMap
       Multimap<String,String> multiMap = ArrayListMultimap.create();
	       
       //Add values
       multiMap.put("fruit", "Banana");
       multiMap.put("fruit", "Apple");
       multiMap.put("fruit", "Banana");
       multiMap.put("fruit", "Avocado");
       multiMap.put("fruit", "Orange");
	        
       multiMap.put("car", "BMW");
       multiMap.put("car", "BMW");
       multiMap.put("car", "Opel");
       multiMap.put("car", "Fiat");
	 
       System.out.println("Total items in multiMap: " + multiMap.size());
       System.out.println("Total fruits in multiMap: " + multiMap.get("fruit").size());
       System.out.println("fruits in multiMap: " + multiMap.get("fruit"));
	       
       //Remove value Banana with key fruit
       multiMap.remove("fruit", "Banana");
	       
       //There is still 1 Banana
       System.out.println("Total items in multiMap: " + multiMap.size());
       System.out.println("Total fruits in multiMap: " + multiMap.get("fruit").size());
       System.out.println("fruits in multiMap: " + multiMap.get("fruit"));	        
       System.out.println("Total items in car: " + multiMap.get("car").size());
       System.out.println("car Items: " + multiMap.get("car"));	
```

**Example - Optional usage**
```
/*
The Optional object is used to represent null with absent value.
*/

      OptionalDemo optionalDemo = new OptionalDemo();

      Integer value =  null;
      Integer value2 =  new Integer(11);
      Integer value3 =  new Integer(5);
      Integer value4 =  null;
      Integer value5 =  null;
      
      //Allows NULL value
      Optional<Integer> x = Optional.fromNullable(value);
      
      //Does not allow NULL value
      Optional<Integer> y = Optional.of(value2);
      
      //Does not allow NULL value
      Optional<Integer> z = Optional.of(value3);

      //Does not allow NULL value
      //Optional<Integer> v = Optional.of(value4); This throws NullPointerException

      //Allows NULL value
      Optional<Integer> w = Optional.fromNullable(value5);

      System.out.println(optionalDemo.calculation(x, y, z, w));
   }

   public Integer calculation(Optional<Integer> x, Optional<Integer> y, Optional<Integer> z, Optional<Integer> w) {
	         
      System.out.println("x is present: " + x.isPresent());
      System.out.println("y is present: " + y.isPresent());
      System.out.println("z is present: " + z.isPresent());
      System.out.println("w is present: " + w.isPresent());

      //Returns the value if present otherwise returns the default value passed
      Integer value1 = x.or(new Integer(0));	
      System.out.println(value1);

      //Gets the value, value should be present
      Integer value2 = y.get();
      System.out.println(value2);
      
      Integer value3 = z.get();
      System.out.println(value3);
      
      //Integer value5 = w.get(); Can't be called because of an absent value

      return value1 + value2 - value3;
  }
}
```

**Example - Ordering**
```
      // Create Lists
      List<Integer> numbers = Lists.newArrayList(1,7,4,22,1,-13,222);
      List<String> fruits = Lists.newArrayList("Banana","Avocado","Banana","Orange","Apple");

      // Create Ordering
      Ordering ordering = Ordering.natural();
      System.out.println("Numbers: " + numbers);      
      System.out.println("Fruits: " + fruits);
        
      // Sort elements
      Collections.sort(numbers,ordering);
      Collections.sort(fruits,ordering);
      System.out.println("Sorted numbers: " + numbers);      
      System.out.println("Sorted numbers: " + fruits);
       
      // Sort descending
      Collections.sort(fruits,ordering.reverse());
      System.out.println("Reverse: " + fruits);

      numbers.add(null);
      System.out.println("Null added to Sorted numbers: " + numbers);	

      Collections.sort(numbers,ordering.nullsFirst());
      System.out.println("Null at first position: " + numbers);
   }
}
```

### <a href="#fastUtil" name="fastUtil"><i class="fa fa-link anchor" aria-hidden="true"></i></a> FastUtil Collections

*FastUtil* characterizes high performance and the fastest implementations available. Some benefits it provides are listed below:
* Classes that support very large collections (64-bit),
* Classes for fast and practical access to binary and text files,
* Provides structure-specific and type-specific Maps, Sets, Lists and PriorityQueues,
* In terms of memory, it's space-efficient

**Speed test:**
According to the benchmarks, *FastUtil* has the title of the "fastest" implementation. The title is justified with the following benefits:
* In int-int map testing, there is a fact that states that the fewer memory accesses an implementation makes to access an entry, the faster it would be, and *FastUtil* has a great advantage because of the highly optimized code. This is highly important for large Maps.
* In int-Object testing, again, highly optimized code get's *FastUtil* to the top positions. That's because once the underlying storage becomes identical, the second order optimizations start to make the difference.
* In Object-int testing, the most important thing is a minimum possible numbers of underlying arrays. *FastUtil*, one more time, proved to be extremely excellent with a convincing first place.
* In Object-Object testing, it takes one of the satisfactory top positions, but not the first, because of less efficient memory access pattern.

For further information, feel free to check this <a href="http://java-performance.info/hashmap-overview-jdk-fastutil-goldman-sachs-hppc-koloboke-trove-january-2015/">website</a>, and we highly recommend you to try to do your own tests.

In addition to the advantages *FastUtil* provides, you need to pay attention to the following shortcomings. For extra information, feel free to check the <a href="http://fastutil.di.unimi.it/docs/overview-summary.html">official website</a>:
* Automatic boxing and unboxing can drive you to choose the wrong method. A suggestion is to set the environment to mark boxing/unboxing as a warning or as an error,
* Classes are not synchronized, that means that for multiple threads it must be synchronized externally,
* Reference-based classes violate the Map contract and do not use the equals() method. Instead of doing this, they compare objects by a reference and should be used only when the reference-based equality is desired,
* Linked classes provide methods to get the first and the last element in iteration order and start a bidirectional iterator from any element, but any submap or subset method will cause an UnsupportedOperationException,
* Maps that have objects as keys, the get() and remove() methods do not admit polymorphic versions. Instead, new methods are introduced - getvaluetype() and removevaluetype()

Another characteristic is a huge jar file, because of numerous Classes. Thus, you can customize it and use the alternative way of selecting specific Classes.

**How to use a library:**
*Dependancy* for Maven’s library importation is listed hereafter:
```
<!-- https://mvnrepository.com/artifact/it.unimi.dsi/fastutil -->
<dependency>
    <groupId>it.unimi.dsi</groupId>
    <artifactId>fastutil</artifactId>
    <version>8.1.0</version>
</dependency>
```

More information about Maven, and how to use it, you can find in this <a href="https://ivanursul.com/articles/java/maven">article</a>.

Below, you can find some Interfaces from Package it.unimi.dsi.fastutil, supported by *FastUtil*. For further information feel free to check the <a href="http://fastutil.di.unimi.it/docs/overview-summary.html">official website</a>:
<table>
  <tr>
    <th>Interfaces</th>
    <th>Description</th> 
  </tr>
  <tr>
    <td>BidirectionalIterator<&#xfeff;K></td>
    <td>A Bidirectional Iterator</td>
  </tr>
  <tr>
    <td>BigList<&#xfeff;K></td>
    <td>A list with big indices (64-bit)</td>
  </tr>
  <tr>
    <td>BigSwapper</td>
    <td>An object that can swap elements whose positions are specified by longs</td> 
  </tr>
  <tr>
    <td>Function<&#xfeff;K, V></td>
    <td>A function mapping keys into values</td>
  </tr>  
  <tr>
    <td>PriorityQueue<&#xfeff;K></td>
    <td>A Priority Queue</td>
  </tr>           
</table>

Below, you can find some Classes from Package it.unimi.dsi.fastutil.ints supported by *FastUtil*. For further information feel free to check the <a href="http://fastutil.di.unimi.it/docs/overview-summary.html">official website</a>:
<table>
  <tr>
    <th>Classes</th>
    <th>Description</th> 
  </tr>
  <tr>
    <td>Int2BooleanFunctions.Singleton</td>
    <td>An immutable class representing a type-specific singleton function</td>
  </tr> 
  <tr>
    <td>Int2ByteFunctions.SynchronizedFunction</td>
    <td>A synchronized wrapper class for functions</td>
  </tr>
  <tr>
    <td>Int2CharMaps.Singleton</td>
    <td>An immutable class representing a type-specific singleton map</td>
  </tr>
  <tr>
    <td>Int2DoubleSortedMaps</td>
    <td>A class providing static methods and objects that do useful things with type-specific sorted maps</td>
  </tr>
  <tr>
    <td>Int2FloatSortedMaps.Singleton</td>
    <td>An immutable class representing a type-specific singleton sorted map</td>
  </tr>
  <tr>
    <td>Int2IntMaps.UnmodifiableMap</td>
    <td>An unmodifiable wrapper class for maps</td>
  </tr>  
</table>

In *FastUtil* exist 11 Packages with numerous Interfaces, Classes, and Methods. We shared only a few Interfaces and Classes and encourage you to check the others on the <a href="https://google.github.io/guava/releases/snapshot-jre/api/docs/">official website</a>.

**Example - DoubleArrayList**
```
	// Create DoubleArrayList
	DoubleArrayList dal = new DoubleArrayList();  
			
	// Add values - Note that there are 2 ways of adding values push and add
	dal.push(11);  
	dal.push(2.5);  
	dal.push(13.5);  
	dal.add(7.5);  
	dal.add(22.5);
	dal.add(11);
			
	System.out.println(dal);
			
	// Check if there is element with value 11
	System.out.println(dal.contains(11));
			
	// Show element on 0th position
	// Note that there are 2 ways of showing values on position 0 peek and get
	System.out.println(dal.peek(0)); 
			
	// Remove element with value 11
	dal.rem(11);
	System.out.println(dal);
			
	// Show element on 0th position
	System.out.println(dal.get(0));
      
	// Remove element - There are few ways of removing elements pop, rem, remove
	dal.pop();
	System.out.println(dal);
			
	// Show the last element in dal
	System.out.println(dal.get(dal.size() - 1));
```

**Example - Long2IntArrayMap**
```
	// Create Long2IntArrayMap
	Long2IntArrayMap map = new Long2IntArrayMap();
		
	// Add values
	map.put(1, 25512);
	map.put(22, 21231);
	map.put(15, 123124);
	map.put(10L, 11231123);
		
	// Remove value
	map.remove(10L);
		
	// Show element with key 22
	System.out.println(map.get(22));
		
	// Set default value to show if key is not found
	map.defaultReturnValue(-1);
	System.out.println(map.get(14));
		
	System.out.println(map);
	
	// Delete all values from map
	map.clear();
	System.out.println(map);
```

**Example - Read-Only and Sorted Maps**
```
	// Create Int2IntMap
	Int2IntMap map = new Int2IntArrayMap();
		
	// Add elements
	map.put(1, 12);
	map.put(12, 4);
	map.put(3, 8);
	map.put(4, 4);
		
	System.out.println(map);
	
	// Create read-only Map, which prohibits the entry of new elements or any changes on the map
	Int2IntMap map2 = Int2IntMaps.unmodifiable(map);
	// map2.put(5, 5); Throws an Exception
	// map2.remove(1); Throws an Exception
	
	// Create Int2IntSortedMap
	Int2IntSortedMap map3 = new Int2IntAVLTreeMap();
		
	// Add elements
	map3.put(1, 12);
	map3.put(12, 4);
	map3.put(3, 8);
	map3.put(4, 4);
	System.out.println(map3);
	
	// Create read-only sorted Map
	Int2IntSortedMap sortedMap = Int2IntSortedMaps.unmodifiable(map3);
```

### <a href="#troveLibrary" name="troveLibrary"><i class="fa fa-link anchor" aria-hidden="true"></i></a> Trove Library

*Trove*, in contrast to FastUtil, is significantly smaller. The advantages of this library are high speed regular and primitive Collections and reduced memory consumption. A fascinating feature is that almost all the Classes and Interfaces start with "T". *Trove* allows storing primitive data types in Collections, which is especially useful if there is a large ArrayList/Set/Map with keys or values that could be of a primitive type.

The most important Collections here are ArrayLists, Sets, and Maps, whereas SortedMaps and Maps (with a fixed iteration order) do not exist. To conclude from the text, the Trove Maps and Sets use open addressing instead of the chaining approach.

**How to use a library:**
To use this library, all you have to do is to insert Maven's *dependency* code to your project.
```
<!-- https://mvnrepository.com/artifact/net.sf.trove4j/trove4j -->
<dependency>
    <groupId>net.sf.trove4j</groupId>
    <artifactId>trove4j</artifactId>
    <version>3.0.3</version>
</dependency>
```

More information about Maven, and how to use it, you can find in this <a href="https://ivanursul.com/articles/java/maven">article</a>.

Below, you can find some Interfaces supported by *Trove*. For further information feel free to check the <a href="http://trove4j.sourceforge.net/javadocs/">official website</a>:
<table>
  <tr>
    <th>Interfaces</th>
    <th>Description</th> 
  </tr>
  <tr>
    <td>TDoubleDoubleMap</td>
    <td>A primitive Map of double keys and values</td>
  </tr>
  <tr>
    <td>TFloatIntMap</td>
    <td>A primitive Map of float keys and int values</td>
  </tr>
  <tr>
    <td>TIntFloatMap</td>
    <td>A primitive Map of int keys and float values</td> 
  </tr>
  <tr>
    <td>TDoubleSet</td>
    <td>A Set that uses an open-addressed hash table to store its contents</td>
  </tr>  
  <tr>
    <td>TIntSet</td>
    <td>A Set that uses an open-addressed hash table to store its contents</td>
  </tr>           
</table>

Below, you can find some Classes supported by *Trove*. For further information feel free to check the <a href="http://trove4j.sourceforge.net/javadocs/">official website</a>:
<table>
  <tr>
    <th>Classes</th>
    <th>Description</th> 
  </tr>
  <tr>
    <td>TCollections</td>
    <td>Trove equivalent of the Collections Class</td>
  </tr> 
  <tr>
    <td>TDoubleArrayList</td>
    <td>A resizable ArrayList of double primitives</td>
  </tr>
  <tr>
    <td>TLongArrayList</td>
    <td>A resizable ArrayList of long primitives</td>
  </tr> 
</table> 

**Example - ArrayList**
```
    	// Create ArrayList
    	TIntArrayList x = new TIntArrayList();
    	
    	// Add values
    	x.add(new int[]{11,2,14,7,22,2});
    	System.out.println(x);
    	
    	// Remove element with value 2
    	x.remove(2);
    	
    	// Sort x - it is must for binarySearch method
    	x.sort();
    	System.out.println(x);
    	
    	// Show element position in x, by value
    	// If method did not find value, returns -1
    	System.out.println(x.binarySearch(1)); 
    	System.out.println(x.binarySearch(11));
    	
    	System.out.println("Max value is: " + x.max() + ", and min value is: " + x.min());
    	
    	// Reverse elements on positions 2, 3 and 4
    	x.reverse(2, 5);
    	
    	// Show x if procedure is true
    	System.out.println(x.grep(new TIntProcedure() {
			
		public boolean execute(int value) {
			// TODO Auto-generated method stub
			return 1==1;
		}
	}));
```

**Example - Set**
```
    	// Create ArrayList
    	TDoubleSet x = new TDoubleHashSet();
    	
    	// Add values
    	x.addAll(new double[]{11.5,2.3,14,7.1,22,2.3});
    	System.out.println(x);
    	
    	// Remove element with value 2
    	x.remove(2.3);
    	System.out.println(x);
    	
    	// Create iterator
    	TDoubleIterator iterator = x.iterator();
    	
    	// Show elements
    	while (iterator.hasNext()) System.out.println(iterator.next()); 
```

**Example - Map**
```
    	// Create Map
    	TIntIntMap x = new TIntIntHashMap();
    	
    	// Add values
    	x.put(1, 12);
    	x.put(11, 12);
    	x.put(2, 2);
    	x.put(5, 10);
    	x.put(12, 20);
    	System.out.println(x);
    	
    	// Remove element with value 2
    	x.remove(5);
    	System.out.println(x);
    	
    	// Create iterator
    	TIntIntIterator iterator = x.iterator();

    	// Show elements
    	while (iterator.hasNext()) {    		
        	// Advance() method has to show keys and values of Map
    		iterator.advance();
    		System.out.println("Key: " + iterator.key() + ", value: " + iterator.value());  	
    	}
```

### <a href="#goldmanSachsCollections" name="goldmanSachsCollections"><i class="fa fa-link anchor" aria-hidden="true"></i></a> Goldman Sachs Collections (Eclipse Collections)

Just like Trove, *Goldman Sachs Collections* is optimized for performance and memory usage. It allows storing primitive data types in Collections. Its focus is on the iterative improvement. Moreover, it has the possibility of creating Immutable Collections, Bags, Multimaps, BiMaps, and Intervals. Alike Guava, writing the code is much simpler and smoother with *Goldman Sachs Collections*. This library provides sort(), min(), max(), select(), collect() methods for all kinds of Collections.

**How to use a library:**
To use this library, all you need to do is to insert Maven's *dependency* code into your project.
```
<!-- https://mvnrepository.com/artifact/com.goldmansachs/gs-collections-forkjoin -->
<dependency>
    <groupId>com.goldmansachs</groupId>
    <artifactId>gs-collections-forkjoin</artifactId>
    <version>7.0.1</version>
</dependency>
```

More information about Maven, and how to use it, you can find in this <a href="https://ivanursul.com/articles/java/maven">article</a>.

According to the <a href="https://www.goldmansachs.com">official website</a>, the most practiced iteration patterns in *Goldman Sachs Collections* are:
* Filtering patterns:
	* Select
	* Reject
	* Partition
* Transforming patterns:
	* Collect
	* Flatten
	* GroupBy
* "Short-circuit" patterns:
	* Detect
	* AnySatisfy
	* AllSatisfy
* Generic action patterns:
	* ForEach
	* InjectInto

More about patterns you can find on official links: <a href="https://www.goldmansachs.com/gs-collections/presentations/BOJUG_April_26_2014_GSCollections.pdf">link1</a>, <a href="https://www.goldmansachs.com/gs-collections/documents/GS%20Collections%20Training%20Session%20and%20Kata%205.0.0.pdf">link2</a>, and <a href="https://www.goldmansachs.com/gs-collections/documents/GS%20Collections%20Reference%20Guide%201.2.0.pdf">link3</a>.

Below, you can find some Interfaces supported by *Goldman Sachs Collections*. For further information feel free to check the <a href="https://www.goldmansachs.com/gs-collections/javadoc/5.0.0/overview-summary.html">official website</a>:
<table>
  <tr>
    <th>Interfaces</th>
    <th>Description</th> 
  </tr>
  <tr>
    <td>Bag<&#xfeff;T></td>
    <td>A Bag whose elements are unordered and may contain duplicate entries</td>
  </tr>
  <tr>
    <td>ImmutableSortedBag<&#xfeff;T></td>
    <td>A sorted Bag that is immutable</td>
  </tr>
  <tr>
    <td>BiMap<&#xfeff;K, V></td>
    <td>A Map that allows bidirectional lookup between key and values</td> 
  </tr>
  <tr>
    <td>MapIterable<&#xfeff;K, V></td>
    <td>A Read-only Map</td>
  </tr>  
  <tr>
    <td>Multimap<&#xfeff;K, V></td>
    <td>A Map that can associate multiple values for keys</td>
  </tr>
  <tr>
    <td>ImmutableSortedSet<&#xfeff;T></td>
    <td>A non-modifiable sorted Set</td>
  </tr>
</table>

Below, you can find some Classes supported by *Goldman Sachs Collections*. For further information feel free to check the <a href="https://www.goldmansachs.com/gs-collections/javadoc/5.0.0/overview-summary.html">official website</a>:
<table>
  <tr>
    <th>Classes</th>
    <th>Description</th> 
  </tr>
  <tr>
    <td>SynchronizedBag<&#xfeff;T></td>
    <td>A synchronized view of a MutableBag</td>
  </tr>
    <td>ImmutableArrayBag<&#xfeff;T></td>
    <td>A non-modifiable Array Bag</td>
  </tr>
  <tr>
    <td>DropIterator<&#xfeff;T></td>
    <td>Iterates over the elements of the iterator skipping the first count elements or the full iterator if the count is non-positive</td>
  </tr> 
</table>

**Example - Bag**
```
    	// Create immutable bag and add values - all in one line of code
    	Bag<String> bag = Bags.immutable.of("Banana", "Avocado", "Apple", "Orange", "Avocado", "Avocado");
    	
    	System.out.println(bag);    	
    	System.out.println("First element is: " + bag.getFirst() + ", and last element is: " + bag.getLast());
    	System.out.println("Number of different elements in bag: " + bag.sizeDistinct());
    	System.out.println("Number of all elements in bag: " + bag.size());
    	
    	// Transform bag to a list
    	List<String> list = bag.toList();
    	
    	System.out.println("Elements in list: " + list);
    	
    	// List is mutable, in opposite of created immutable bag, so we can add values
    	list.add("Kiwi");
    	
    	// Create comparator so we can sort the list
    	Comparator<? super String> comparator = Comparators.reverseNaturalOrder();
    	list.sort(comparator);
    	System.out.println("Elements in list after change: " + list);
```

**Example - BiMap**
```
    	// Create BiMap and add elements
    	BiMap<Integer, String> map = BiMaps.mutable.of(1,"Banana",22,"Avocado",5,"Kiwi",7,"Orange");
    	((MutableBiMap<Integer, String>) map).put(3,"Apple");
    	
    	System.out.println("Keys in map: " + map.keysView() + ", values in map: " + map.valuesView());
    	
    	// Transform map to mutable list
    	MutableList<String> mutableList = map.toSortedList();
    	mutableList.add("Orange");
    	System.out.println(mutableList);
    	
    	// Transform mutable to immutable list
    	ImmutableList<String> immutableList = mutableList.toImmutable();   
```

**Example - List**
```
    	// Create IntList and add values
    	IntList list = IntLists.mutable.of(1,4,5,22,13);  
    	((MutableIntCollection) list).add(11);
    
    	System.out.println("The average value of elements in list is: " + list.average());
    	
    	// Create MutableList and add values
    	MutableList<String> fruits = FastList.newListWith("Banana","Orange","Apple","Kiwi","Avocado");
    	System.out.println(fruits);
    	
	// Create MutableListMultimap and add values from fruits with keys expressed in the number of letters each word contains
	MutableListMultimap<Integer, String> multimap = fruits.groupBy(StringFunctions.length());
    	System.out.println(multimap);
	
    	// Create Map
    	Map<Integer, String> map = new HashMap();
    		
    	// Add keys from list and values from fruits to a Map
    	for(int i = 0; i < list.size() - 1; i++) 
    		map.put(list.get(i), fruits.get(i));
    	
    	System.out.println(map);  
```

**Example - Set**
```
    	// Create ImmutableDoubleSet and add values
    	ImmutableDoubleSet set = DoubleSets.immutable.of(4.2,3.3,15.5,8.4);
    	
    	// Show elements stored in Set
    	set.forEach((DoubleProcedure) System.out::println);
    	System.out.println("Max value is: " + set.max());
    	System.out.println("Min value is: " + set.min());
    	System.out.println("Average value is: " + set.average());
    	
    	// Method freeze() returns a copy similar to immutable
    	ImmutableDoubleSet set2 = (ImmutableDoubleSet) set.freeze();
    	
    	// Transform Set to sorted List
    	DoubleList list = set2.toSortedList();
    	
    	// Elements are sorted by value
    	list.forEach((DoubleProcedure) System.out::println);
```

If you like this article, you may be interested in <a href="https://ivanursul.com/articles/java/lists">Lists</a>, <a href="https://ivanursul.com/articles/java/sets">Sets</a>, <a href="https://ivanursul.com/articles/java/maps">Maps</a>, <a href="https://ivanursul.com/articles/java/queues">Queues</a>, and <a href="https://ivanursul.com/articles/java/deques">Deques</a>. Feel free to browse!
