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

# **Methods of Map**
```java
The Map interface includes the following methods:

put(K, V) - Inserts the association of a key K and a value V into the map. If the key is already present, the new value replaces the old value.
putAll() - Inserts all the entries from the specified map to this map.
putIfAbsent(K, V) - Inserts the association if the key K is not already associated with the value V.
get(K) - Returns the value associated with the specified key K. If the key is not found, it returns null.
getOrDefault(K, defaultValue) - Returns the value associated with the specified key K. If the key is not found, it returns the defaultValue.
containsKey(K) - Checks if the specified key K is present in the map or not.
containsValue(V) - Checks if the specified value V is present in the map or not.
replace(K, V) - Replace the value of the key K with the new specified value V.
replace(K, oldValue, newValue) - Replaces the value of the key K with the new value newValue only if the key K is associated with the value oldValue.
remove(K) - Removes the entry from the map represented by the key K.
remove(K, V) - Removes the entry from the map that has key K associated with value V.
keySet() - Returns a set of all the keys present in a map.
values() - Returns a set of all the values present in a map.
entrySet() - Returns a set of all the key/value mapping present in a map.
```

```java
import java.util.*;


class MapExample {

    public static void main(String[] args) {
     Map<String,Integer> playerScores=new HashMap<>();
     // put(K, V) - Add player scores
        playerScores.put("Virat Kohli", 85);
        playerScores.put("MS Dhoni", 72);
        playerScores.put("Rohit Sharma", 120);
        System.out.println("After put(): " + playerScores);

        // putAll() - Add scores from another map
        Map<String, Integer> additionalScores = new HashMap<>();
        additionalScores.put("KL Rahul", 91);
        additionalScores.put("Jasprit Bumrah", 15);
        playerScores.putAll(additionalScores);
        System.out.println("After putAll(): " + playerScores);

        // putIfAbsent(K, V) - Add player only if not already present
        playerScores.putIfAbsent("MS Dhoni", 50); // Key already exists
        playerScores.putIfAbsent("Hardik Pandya", 45); // New key
        System.out.println("After putIfAbsent(): " + playerScores);

        // get(K) - Get score for a specific player
        System.out.println("Score of Virat Kohli: " + playerScores.get("Virat Kohli"));
        System.out.println("Score of unknown player: " + playerScores.get("Suresh Raina"));

        // getOrDefault(K, defaultValue) - Get score or default value
        System.out.println("Score of unknown player or default: " + playerScores.getOrDefault("Suresh Raina", 0));

        // containsKey(K) - Check if a player exists in the map
        System.out.println("Does MS Dhoni exist? " + playerScores.containsKey("MS Dhoni"));
        System.out.println("Does Yuvraj Singh exist? " + playerScores.containsKey("Yuvraj Singh"));

        // containsValue(V) - Check if a score exists in the map
        System.out.println("Does score 120 exist? " + playerScores.containsValue(120));
        System.out.println("Does score 200 exist? " + playerScores.containsValue(200));

        // replace(K, V) - Update score for a player
        playerScores.replace("Rohit Sharma", 140);
        System.out.println("After replace(key, value): " + playerScores);

     // replace(K, oldValue, newValue) - Update score only if old value matches
        boolean replaced = playerScores.replace("KL Rahul", 91, 100);
        System.out.println("After replace(key, oldValue, newValue): " + playerScores);
        System.out.println("Was replace successful? " + replaced);

         // remove(K) - Remove a player by name
        playerScores.remove("Jasprit Bumrah");
        System.out.println("After remove(key): " + playerScores);

         // remove(K, V) - Remove a player by name and score
        boolean removed = playerScores.remove("Hardik Pandya", 45);
        System.out.println("After remove(key, value): " + playerScores);
        System.out.println("Was remove successful? " + removed);

         // keySet() - Get a set of all player names
        Set<String> players = playerScores.keySet();
        System.out.println("Players: " + players);

        // values() - Get a collection of all scores
        Collection<Integer> scores = playerScores.values();
        System.out.println("Scores: " + scores);

        // entrySet() - Get a set of all player-score pairs
        Set<Map.Entry<String, Integer>> entries = playerScores.entrySet();
        System.out.println("Player-Score Entries: ");
        for (Map.Entry<String, Integer> entry : entries) {
            System.out.println(entry.getKey() + " = " + entry.getValue());
        }

    }
}
```
