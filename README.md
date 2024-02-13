# JavaSE-Maps

See the Udemy course: https://www.udemy.com/course/curso-certificacion-profesional-desarrollador-java-se-11

## In summary

Use **HashMap** if you need fast access to elements and order doesn't matter.

Use **TreeMap** if you need elements sorted in a natural order.

Use **LinkedHashMap** if you need to maintain the order of insertion.


In Java, the term "Map" refers to a data structure that stores key-value pairs. 

Each key is associated with exactly one value, and you can use the key to retrieve the corresponding value. 

Java provides several implementations of the Map interface, but the most commonly used ones are: HashMap, TreeMap, and LinkedHashMap.


## 1. HashMap

Use **HashMap** if you need fast access to elements and order doesn't matter.

```java
import java.util.HashMap;
import java.util.Map;

public class HashMapExample {
    public static void main(String[] args) {
        // Creating a HashMap
        Map<String, Integer> ageMap = new HashMap<>();

        // Adding key-value pairs
        ageMap.put("Alice", 25);
        ageMap.put("Bob", 30);
        ageMap.put("Charlie", 22);

        // Accessing values using keys
        System.out.println("Alice's age: " + ageMap.get("Alice"));

        // Iterating through the map
        for (Map.Entry<String, Integer> entry : ageMap.entrySet()) {
            System.out.println(entry.getKey() + ": " + entry.getValue());
        }
    }
}
```

## 2. TreeMap

Use **TreeMap** if you need elements sorted in a natural order.

```java
import java.util.Map;
import java.util.TreeMap;

public class TreeMapExample {
    public static void main(String[] args) {
        // Creating a TreeMap
        Map<String, Integer> ageMap = new TreeMap<>();

        // Adding key-value pairs
        ageMap.put("Alice", 25);
        ageMap.put("Bob", 30);
        ageMap.put("Charlie", 22);

        // Accessing values using keys
        System.out.println("Alice's age: " + ageMap.get("Alice"));

        // Iterating through the map (Note: TreeMap is ordered)
        for (Map.Entry<String, Integer> entry : ageMap.entrySet()) {
            System.out.println(entry.getKey() + ": " + entry.getValue());
        }
    }
}
```

## 3. LinkedHashMap

Use **LinkedHashMap** if you need to maintain the order of insertion.

```java
import java.util.LinkedHashMap;
import java.util.Map;

public class LinkedHashMapExample {
    public static void main(String[] args) {
        // Creating a LinkedHashMap
        Map<String, Integer> ageMap = new LinkedHashMap<>();

        // Adding key-value pairs
        ageMap.put("Alice", 25);
        ageMap.put("Bob", 30);
        ageMap.put("Charlie", 22);

        // Accessing values using keys
        System.out.println("Alice's age: " + ageMap.get("Alice"));

        // Iterating through the map (Note: LinkedHashMap maintains insertion order)
        for (Map.Entry<String, Integer> entry : ageMap.entrySet()) {
            System.out.println(entry.getKey() + ": " + entry.getValue());
        }
    }
}
```

In these examples, you can see how to create a map, add key-value pairs, and retrieve values based on keys.

The choice of which map implementation to use depends on your specific requirements regarding ordering and performance.

## 4. HashTable

The HashTable class in Java is another implementation of the Map interface that is similar to HashMap. 

However, there are some key differences, and HashTable has some characteristics that make it less commonly used in modern Java development. Here's an example:

```java
import java.util.Hashtable;
import java.util.Map;

public class HashTableExample {
    public static void main(String[] args) {
        // Creating a HashTable
        Map<String, Integer> ageTable = new Hashtable<>();

        // Adding key-value pairs
        ageTable.put("Alice", 25);
        ageTable.put("Bob", 30);
        ageTable.put("Charlie", 22);

        // Accessing values using keys
        System.out.println("Alice's age: " + ageTable.get("Alice"));

        // Iterating through the table (Note: HashTable is synchronized)
        for (Map.Entry<String, Integer> entry : ageTable.entrySet()) {
            System.out.println(entry.getKey() + ": " + entry.getValue());
        }
    }
}
```

## Important Points about HashTable

**Synchronization**: One of the main differences between HashMap and HashTable is that HashTable is synchronized. 

This means that all operations on the table are thread-safe. However, this comes at the cost of reduced performance.

**Nulls**: Neither keys nor values can be null in a HashTable. If you attempt to insert a null key or value, a NullPointerException will be thrown.

**Performance**: Due to synchronization, HashTable can be slower than HashMap in a single-threaded environment. If you don't need thread safety, it's often recommended to use HashMap or other non-synchronized maps for better performance.

**Legacy**: While HashTable is part of the Java Collections Framework, it's considered somewhat legacy, and newer implementations like HashMap are generally preferred for most use cases.

In modern Java development, HashMap is often preferred over HashTable due to better performance and the ability to handle null values. 

However, if you specifically need thread safety, and can handle the performance trade-off, ConcurrentHashMap might be a more contemporary choice.

In Java, HashMap, TreeMap, and LinkedHashMap are all implementations of the Map interface, but they have different characteristics in terms of ordering and performance.

## HashMap

Use **HashMap** if you need fast access to elements and order doesn't matter.

Does not guarantee any specific order of elements.

Offers constant-time performance for basic operations (add, remove, and get), assuming the hash function distributes the elements properly.

It is the most efficient for frequent insertions and lookups.

```java
Map<String, Integer> hashMap = new HashMap<>();
hashMap.put("Alice", 25);
hashMap.put("Bob", 30);
hashMap.put("Charlie", 22);

System.out.println(hashMap); // Output order may vary
```

## TreeMap

Use **TreeMap** if you need elements sorted in a natural order.

Maintains elements in natural order (ascending order for numeric types, lexicographic order for strings).

Slower insertion and removal compared to HashMap, but the elements are ordered.

```java
Map<String, Integer> treeMap = new TreeMap<>();
treeMap.put("Alice", 25);
treeMap.put("Bob", 30);
treeMap.put("Charlie", 22);

System.out.println(treeMap); // Output in ascending order
```

## LinkedHashMap

Use **LinkedHashMap** if you need to maintain the order of insertion.

Maintains the order of elements based on the order they were inserted.

Slightly slower than HashMap for basic operations but provides predictable iteration order.

```java
Map<String, Integer> linkedHashMap = new LinkedHashMap<>();
linkedHashMap.put("Alice", 25);
linkedHashMap.put("Bob", 30);
linkedHashMap.put("Charlie", 22);

System.out.println(linkedHashMap); // Output in insertion order
```
