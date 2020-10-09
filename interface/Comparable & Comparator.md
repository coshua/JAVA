
### Common Concept
Java use two interfaces to compare objects. However, the basic principles exist.

If a comparing method returns a positive integer, it means the current object or the object passed into the first argument to the method is greater (what greater means differ by class) than the other.

### Comparable
It is an interface containing the compareTo method. If a class has natural order and implements comparable, the objects of the class can be compared without overriding any method.
It is in the java.lang package.

```java
public class A implements Comparable<A> {
  public int compareTo(A other) {
    return an integer;
  }
}
```

### Comparator
It is an interface containing the compare and equals method. It is used to specify the order to match user needs.
It is in the java.util package.

```java
public class B implements Comparator<B1> {
  public int compare(B1 o1, B1 o2) {
    return an integer;
  }
}
```

Comparator is often implemented by lambda expression or Comparator.comparing method like followings.

`java.util.Arrays.sort(cityList, (city1, city2) -> city1.length() - city2.length());` //call a static sort method from Array class with a custumized Comparator in a second argument

`java.util.Arrays.sort(cityList, Comparator.comparing(String::length));`

`cityList.sort((city1, city2) -> city1.compareToIgnoreCase(city2));`

`cityList.sort(String::compareToIgnoreCase);`

