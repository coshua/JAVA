# Sets
Set does not contain duplicate elements. It could be one of three concrete classes: HashSet, LinkedHashSet, or TreeSet. 
The AbstractSet class extends AbstractCollection and partially implements Set.

### HashSet
It has capacity and load factor which is a value between 0.0 and 1.0 (default is 0.75). The load factor measures how full the set is allowed to be before its capacity is increased.
When the number of elements exceeds the product of the capacity and the load factor, the capacity is doubled. A higher load factor decreses the space costs but increases the search time.

Objects added to HashSet need to implement the hashCode method in a manner that property disperses the hash code. The hashCode method is defined in the Object class, and returns the same value if the two objects are equal.
It could happen that two unequal objects have the same hash code.

The elements are not stored in the order in which they are inserted into the set. You can impose the order with LinkedHashSet.

### LinkedHashSet
LinkedHashSet extends HashSet with a linked-list implementation. It maintains the order in which the element is inserted. To impose a different order, you can use the TreeSet class.

### TreeSet
SortedSet is a subinterface of Set, which guarantees that the elements in the set are sorted. In addition, it provides the methods first() and last() for returning specific value.
headSet(toElement) and tailSet(fromElement) return a portion of the set whose elements are less than toElement and greater than or equal to fromElement, respectively.

NavigableSet extends SortedSet to provide navigation methods lower(e), floor(e), ceiling(e), and higher(e) that return elements, respectively,
less than, less than or equal, greater than or equal, and greater than a given element and return null if no element matches the condition. They return one element.
The pollFirst() and pollLast() methods remove and return the first and last element. 

**TreeSet** implements the SortedSet interface. You can add objects into a tree set as long as they can be compared with each other(remember Comparable and Comparator).
If you create a TreeSet using a no-arg constructor, the compareTo method is used to compare the elements, assuming the class of the elements implements the Comparable inferface.
To use a Comparator, you have to use the consructor TreeSet(Comparator c) to create a sorted set that uses the **compare** method to order the elements in the set.
TreeSet test if two elements are equal using e1.compare(e2) to see the return 0. Other than comparator, all sets test if e1.equal(e2) is true and their hashCode() are the same.


# Maps
A map in Java is a container object that stores a collection of key-value pairs. It enables fast retrieval, deletion, and updating of the pair through key.
In List, the indexes are integers. In Map, the keys can be any objects. A map cannot contain duplicate keys. Each key maps to one value. There are three types of maps: HashMap, LinkedHashMap, and TreeMap (notice it is the same with Sets. Their relationship with Map interface is also exactly the same. ex) 
TreeMap implements NavigableMap which implements SortedMap which implements Map.)

The Map interface provides the methods for querying, updating, and obtaining a collection of values and a set of keys.

The update methods include *clear(), put(K, V), putAll(Map m), and remove(Object Key)*. If you add a key already exist, the old value is replaced y the new value. 

The query methods include *containsKey(Object key), containsValue(Object value), isEmpty(), and size()*. All except size() returns boolean.

You can object a set of keys in the map using the *keySet()*, and a collection of values using *values()*. The *entrySet()* returns a set of entries.
The entries are instances of Map.Entry(K, V) interface, where Entry is an inner interface for the Map interface. Each entry in the set is a key/value pair in the underlying map. It also has a default forEach method.

The AbstractMap class implements all the methods in Map except entrySet().

The entries in a LinkedHashMap can be retrieved either in the order in which they were inserted into the map (insertion order) or in the order in which they were last accessed, from least to most recently accessed (access order). It uses insertion order if not specified in its third argument as true in its constructor. It is important to know that TreeMap uses key as it's sorting order.
