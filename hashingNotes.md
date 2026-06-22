# HashMap

## Definition

`HashMap` is a data structure in Java that stores data as **key-value pairs**.

```java
HashMap<KeyType, ValueType> map = new HashMap<>();
```

Example:

```java
HashMap<String, Integer> map = new HashMap<>();

map.put("apple", 5);
map.put("banana", 3);
```

### Visualization

```text
Key      Value
----     -----
apple →   5
banana →  3
```

---

## Features

* Stores data in key-value pairs
* Keys must be unique
* Values can be duplicated
* Average Time Complexity:

  * Insert → O(1)
  * Search → O(1)
  * Delete → O(1)

---

## Internal Working

```text
Key
 ↓
Hash Function
 ↓
Hash Code
 ↓
Bucket Index
 ↓
Store Value
```

Java uses hashing to quickly locate keys.

---

# HashMap Functions

## 1. `put()`

Insert or update a key-value pair.

```java
HashMap<String,Integer> map = new HashMap<>();

map.put("apple", 5);
map.put("banana", 10);
```

### Result

```text
apple → 5
banana → 10
```

### Common Uses

* Frequency counting
* Storing indices
* Lookup tables

---

## 2. `get()`

Retrieve a value using its key.

```java
int value = map.get("apple");
```

### Result

```text
5
```

### Common Uses

* Retrieve frequency
* Get stored index
* Lookup operations

---

## 3. `getOrDefault()`

Returns the value if key exists, otherwise returns a default value.

```java
map.getOrDefault("apple", 0);
```

### Result

```text
5
```

If key doesn't exist:

```java
map.getOrDefault("orange", 0);
```

### Result

```text
0
```

### Common Uses

* Frequency counting
* Character counting
* Word counting

```java
map.put(ch, map.getOrDefault(ch, 0) + 1);
```

---

## 4. `containsKey()`

Checks whether a key exists.

```java
map.containsKey("apple");
```

### Result

```text
true
```

### Common Uses

* Duplicate detection
* Two Sum
* Frequency maps

---

## 5. `containsValue()`

Checks whether a value exists.

```java
map.containsValue(10);
```

### Result

```text
true
```

### Common Uses

Rarely used in DSA.

---

## 6. `remove()`

Removes a key-value pair.

```java
map.remove("apple");
```

### Common Uses

* Sliding Window
* Cache problems
* Dynamic updates

---

## 7. `size()`

Returns number of entries.

```java
map.size();
```

### Result

```text
2
```

### Common Uses

* Count distinct elements
* Window size calculations

---

## 8. `isEmpty()`

Checks whether map is empty.

```java
map.isEmpty();
```

### Result

```text
true / false
```

---

## 9. `clear()`

Removes all entries.

```java
map.clear();
```

### Result

```text
{}
```

---

## 10. `keySet()`

Returns all keys.

```java
for(String key : map.keySet()) {
    System.out.println(key);
}
```

### Common Uses

* Traverse keys
* Distinct element problems

---

## 11. `values()`

Returns all values.

```java
for(int value : map.values()) {
    System.out.println(value);
}
```

### Common Uses

* Find maximum frequency
* Aggregate values

---

## 12. `entrySet()`

Returns key-value pairs.

```java
for(Map.Entry<String,Integer> entry : map.entrySet()) {
    System.out.println(
        entry.getKey() + " " +
        entry.getValue()
    );
}
```

### Result

```text
apple 5
banana 10
```

### Common Uses

* Frequency map traversal
* Most frequent element
* Printing maps

---

## 13. `putIfAbsent()`

Insert only if key doesn't exist.

```java
map.putIfAbsent("apple", 20);
```

### Common Uses

* Memoization
* Initialization

---

## 14. `replace()`

Replace an existing value.

```java
map.replace("apple", 50);
```

### Result

```text
apple → 50
```

### Common Uses

* Updating frequencies
* Dynamic modifications

---

# Common DSA Patterns

## Frequency Count

```java
HashMap<Character,Integer> freq = new HashMap<>();

for(char ch : s.toCharArray()) {
    freq.put(ch,
             freq.getOrDefault(ch,0)+1);
}
```

### Uses

* Character Frequency
* Word Frequency
* Majority Element

---

## Duplicate Detection

```java
HashMap<Integer,Integer> map = new HashMap<>();

for(int num : arr) {

    if(map.containsKey(num)) {
        System.out.println("Duplicate Found");
    }

    map.put(num,1);
}
```

### Uses

* Contains Duplicate
* Repeated Elements

---

## Two Sum

```java
HashMap<Integer,Integer> map = new HashMap<>();

for(int i=0;i<arr.length;i++) {

    int target = k - arr[i];

    if(map.containsKey(target)) {
        return new int[]{
            map.get(target),
            i
        };
    }

    map.put(arr[i], i);
}
```

### Uses

* Two Sum
* Pair Finding

---

## First Non-Repeating Character

```java
HashMap<Character,Integer> map = new HashMap<>();

for(char ch : s.toCharArray()) {
    map.put(ch,
            map.getOrDefault(ch,0)+1);
}

for(char ch : s.toCharArray()) {
    if(map.get(ch)==1) {
        return ch;
    }
}
```

### Uses

* String Problems
* Frequency Based Questions

---

# DSA Cheat Sheet

## Must Know

```java
put()
get()
getOrDefault()
containsKey()
remove()
size()
keySet()
values()
entrySet()
```

## Good To Know

```java
putIfAbsent()
replace()
containsValue()
clear()
isEmpty()
```

---

# Interview Rule

Master these patterns:

```text
Frequency Count
Two Sum
Duplicate Detection
First Non-Repeating Character
```

and you'll be able to solve most HashMap questions asked in coding interviews.
