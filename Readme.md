# **Methods of Collection**
The Collection interface includes various methods that can be used to perform different operations on objects. These methods are available in all its subinterfaces.
```java
add() - inserts the specified element to the collection
size() - returns the size of the collection
remove() - removes the specified element from the collection
iterator() - returns an iterator to access elements of the collection
addAll() - adds all the elements of a specified collection to the collection
removeAll() - removes all the elements of the specified collection from the collection
clear() - removes all the elements of the collection
```

# **set methods**
```java
add() - adds the specified element to the set
addAll() - adds all the elements of the specified collection to the set
iterator() - returns an iterator that can be used to access elements of the set sequentially
remove() - removes the specified element from the set
removeAll() - removes all the elements from the set that is present in another specified set
retainAll() - retains all the elements in the set that are also present in another specified set
clear() - removes all the elements from the set
size() - returns the length (number of elements) of the set
toArray() - returns an array containing all the elements of the set
contains() - returns true if the set contains the specified element
containsAll() - returns true if the set contains all the elements of the specified collection
hashCode() - returns a hash code value (address of the element in the set)
```

# **Set Method**

```java
import java.util.*;


class SetPrograms {

    public static void main(String[] args) {
     Set<Integer> set1=new HashSet<>();
     
     //adding the elements
     set1.add(10);
     set1.add(20);
     set1.add(30);
     set1.add(10);
     System.out.println("After add(): " + set1);
      Set<Integer> anotherSet = new HashSet<>();
        anotherSet.add(40);
        anotherSet.add(50);
        set1.addAll(anotherSet);
         System.out.println("After addAll(): " + set1);

// iterator() - Access elements using an iterator
        Iterator<Integer> iterator=set1.iterator();
         System.out.print("Using iterator(): ");
        while (iterator.hasNext()) {
            System.out.print(iterator.next() + " ");
        }
        System.out.println();
     // remove() - Remove a specific element
        set1.remove(20);
        System.out.println("After remove(): " + set1);

        // removeAll() - Remove elements present in another set
        set1.removeAll(anotherSet);
        System.out.println("After removeAll(): " + set1);

        // retainAll() - Retain only elements also present in another set
        set1.add(60);
        set1.add(70);
        anotherSet.add(30); // Adding common element for testing retainAll
        set1.retainAll(anotherSet);
        System.out.println("After retainAll(): " + set1);

        // clear() - Remove all elements
        set1.clear();
        System.out.println("After clear(): " + set1);

         // size() - Get the number of elements in the set
        set1.add(10);
        set1.add(20);
        System.out.println("Size of set: " + set1.size());

        // toArray() - Convert set to an array
        Object[] array = set1.toArray();
        System.out.print("Array from set: ");
        for (Object obj : array) {
            System.out.print(obj + " ");
        }
        System.out.println();

        // contains() - Check if set contains an element
        System.out.println("Contains 10: " + set1.contains(10));

        // containsAll() - Check if set contains all elements of another set
        anotherSet.clear();
        anotherSet.add(10);
        anotherSet.add(20);
        System.out.println("Contains all elements of anotherSet: " + set1.containsAll(anotherSet));

        // hashCode() - Get hash code of the set
        System.out.println("Hash code of set: " + set1.hashCode());
    }
}
```
