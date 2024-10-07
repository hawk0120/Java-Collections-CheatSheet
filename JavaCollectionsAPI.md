# Java Collections Cheatsheet

## Core Collections

### 1. Array
- **Definition**: Fixed-size sequential collection of elements of the same type.
- **Syntax**:
  ```java
  int[] arr = new int[10];
  int[] arr = {1, 2, 3, 4, 5};
  ```
- **Access**: `arr[index]`
- **Length**: `arr.length`

### 2. ArrayList
- **Definition**: Resizable array implementation of the List interface.
- **Import**: `import java.util.ArrayList;`
- **Syntax**:
  ```java
  ArrayList<Integer> list = new ArrayList<>();
  list.add(1);
  list.get(0); // Access element at index 0
  ```
- **Methods**: `add()`, `get()`, `remove()`, `size()`

### 3. LinkedList
- **Definition**: Doubly-linked list implementation of the List and Deque interfaces.
- **Import**: `import java.util.LinkedList;`
- **Syntax**:
  ```java
  LinkedList<Integer> list = new LinkedList<>();
  list.add(1);
  list.get(0); // Access element at index 0
  ```
- **Methods**: `add()`, `get()`, `remove()`, `size()`

### 4. HashSet
- **Definition**: Implementation of the Set interface that uses a hash table.
- **Import**: `import java.util.HashSet;`
- **Syntax**:
  ```java
  HashSet<Integer> set = new HashSet<>();
  set.add(1);
  set.contains(1); // Check if set contains element
  ```
- **Methods**: `add()`, `contains()`, `remove()`, `size()`

### 5. TreeSet
- **Definition**: A NavigableSet implementation that uses a TreeMap.
- **Import**: `import java.util.TreeSet;`
- **Syntax**:
  ```java
  TreeSet<Integer> set = new TreeSet<>();
  set.add(1);
  set.contains(1); // Check if set contains element
  ```
- **Methods**: `add()`, `contains()`, `remove()`, `size()`, `first()`, `last()`

### 6. HashMap
- **Definition**: Hash table based implementation of the Map interface.
- **Import**: `import java.util.HashMap;`
- **Syntax**:
  ```java
  HashMap<Integer, String> map = new HashMap<>();
  map.put(1, "One");
  map.get(1); // Get value for key 1
  ```
- **Methods**: `put()`, `get()`, `remove()`, `size()`, `containsKey()`

### 7. TreeMap
- **Definition**: Red-Black tree based implementation of the NavigableMap interface.
- **Import**: `import java.util.TreeMap;`
- **Syntax**:
  ```java
  TreeMap<Integer, String> map = new TreeMap<>();
  map.put(1, "One");
  map.get(1); // Get value for key 1
  ```
- **Methods**: `put()`, `get()`, `remove()`, `size()`, `firstKey()`, `lastKey()`

## Utility Classes

### 8. String
- **Definition**: Immutable sequence of characters.
- **Syntax**:
  ```java
  String str = "Hello";
  ```
- **Methods**: `length()`, `charAt()`, `substring()`, `indexOf()`, `toUpperCase()`, `toLowerCase()`

### 9. StringBuilder
- **Definition**: Mutable sequence of characters.
- **Import**: `import java.lang.StringBuilder;`
- **Syntax**:
  ```java
  StringBuilder sb = new StringBuilder("Hello");
  sb.append(" World");
  ```
- **Methods**: `append()`, `insert()`, `delete()`, `reverse()`, `toString()`

### 10. Stack
- **Definition**: Last-in-first-out (LIFO) stack of objects.
- **Import**: `import java.util.Stack;`
- **Syntax**:
  ```java
  Stack<Integer> stack = new Stack<>();
  stack.push(1);
  stack.pop(); // Remove and return the top element
  ```
- **Methods**: `push()`, `pop()`, `peek()`, `isEmpty()`, `size()`

### 11. Queue
- **Definition**: First-in-first-out (FIFO) queue of objects.
- **Import**: `import java.util.Queue;`
- **Common Implementations**: `LinkedList`, `PriorityQueue`
- **Syntax**:
  ```java
  Queue<Integer> queue = new LinkedList<>();
  queue.add(1);
  queue.poll(); // Remove and return the head element
  ```
- **Methods**: `add()`, `poll()`, `peek()`, `isEmpty()`, `size()`

### 12. Deque
- **Definition**: Double-ended queue, can be used as both stack and queue.
- **Import**: `import java.util.Deque;`
- **Common Implementations**: `LinkedList`, `ArrayDeque`
- **Syntax**:
  ```java
  Deque<Integer> deque = new LinkedList<>();
  deque.addFirst(1);
  deque.addLast(2);
  deque.pollFirst(); // Remove and return the first element
  ```
- **Methods**: `addFirst()`, `addLast()`, `pollFirst()`, `pollLast()`, `peekFirst()`, `peekLast()`

### 13. Pair (JavaFX)
- **Definition**: Simple container to store a pair of objects.
- **Import**: `import javafx.util.Pair;`
- **Syntax**:
  ```java
  Pair<Integer, String> pair = new Pair<>(1, "One");
  pair.getKey(); // Get the first element
  pair.getValue(); // Get the second element
  ```
- **Methods**: `getKey()`, `getValue()`

### 14. Optional
- **Definition**: Container object which may or may not contain a non-null value.
- **Import**: `import java.util.Optional;`
- **Syntax**:
  ```java
  Optional<String> optional = Optional.of("Hello");
  optional.isPresent(); // Check if a value is present
  optional.get(); // Get the value
  ```
- **Methods**: `of()`, `empty()`, `isPresent()`, `get()`, `ifPresent()`, `orElse()`

## Sorting Collections

### Collections.sort()
- **Definition**: Sorts the specified list into ascending order.
- **Import**: `import java.util.Collections;`
- **Syntax**:
  ```java
  List<Integer> list = new ArrayList<>();
  Collections.sort(list);
  ```
- **Custom Comparator**:
  ```java
  Collections.sort(list, new Comparator<Integer>() {
      public int compare(Integer o1, Integer o2) {
          return o1.compareTo(o2);
      }
  });
  ```

### Arrays.sort()
- **Definition**: Sorts the specified array into ascending order.
- **Syntax**:
  ```java
  int[] arr = {5, 3, 4, 1, 2};
  Arrays.sort(arr);
  ```

## Streams

### Stream API
- **Definition**: Introduced in Java 8, provides a functional approach to processing collections of objects.
- **Import**: `import java.util.stream.*;`
- **Syntax**:
  ```java
  List<Integer> list = Arrays.asList(1, 2, 3, 4, 5);
  list.stream().filter(n -> n % 2 == 0).forEach(System.out::println);
  ```
- **Common Methods**:
  - **filter()**: Filters elements based on a condition.
    ```java
    list.stream().filter(n -> n > 2);
    ```
  - **map()**: Transforms elements.
    ```java
    list.stream().map(n -> n * 2);
    ```
  - **collect()**: Collects elements into a new collection.
    ```java
    List<Integer> evenNumbers = list.stream().filter(n -> n % 2 == 0).collect(Collectors.toList());
    ```
  - **forEach()**: Performs an action for each element.
    ```java
    list.stream().forEach(System.out::println);
    ```
  - **reduce()**: Combines elements into a single result.
    ```java
    int sum = list.stream().reduce(0, Integer::sum);
    ```

