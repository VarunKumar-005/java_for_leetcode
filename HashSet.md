# HashSet

## HashSet vs HashMap

Many beginners get confused between `HashSet` and `HashMap`.

Think of them like this:

### HashSet

Stores only values.

```java
HashSet<Integer> set = new HashSet<>();

set.add(10);
set.add(20);
set.add(30);
```

Visualization:

```text
10
20
30
```

Use HashSet when you only care about whether an element exists.

Examples:

* Check duplicates
* Distinct elements
* Fast lookup
* Unique values

---

Use HashMap when you need extra information associated with a key.

Examples:

* Frequency counting
* Storing indices
* Lookup tables
* Mapping relationships

---

### Quick Rule

```text
Need only existence?
→ HashSet

Need key + information?
→ HashMap
```

Example:

Finding duplicates:

```java
[1,2,3,2,5]
```

Use HashSet:

```java
if(set.contains(2))
```

Need frequency?

```java
1 -> 1
2 -> 2
3 -> 1
5 -> 1
```

Use HashMap:

```java
map.put(num,
        map.getOrDefault(num,0)+1);
```

---

# Definition

`HashSet` is a collection that stores only unique elements.

```java
HashSet<Integer> set = new HashSet<>();
```

Duplicate values are automatically ignored.

Example:

```java
set.add(10);
set.add(10);
set.add(10);
```

Result:

```text
[10]
```

Only one copy is stored.

---

# Features

* Stores unique elements
* No duplicate values
* Fast insertion
* Fast deletion
* Fast searching

Average Complexity:

```text
Add      O(1)
Remove   O(1)
Search   O(1)
```

---

# Internal Working

HashSet internally uses a HashMap.

```text
Element
   ↓
Hash Function
   ↓
Bucket
   ↓
Stored
```

Internally Java stores:

```text
10 → PRESENT
20 → PRESENT
30 → PRESENT
```

using a hidden HashMap.

---

# HashSet Functions

## 1. add()

Insert an element.

```java
HashSet<Integer> set = new HashSet<>();

set.add(10);
set.add(20);
set.add(30);
```

Result:

```text
[10,20,30]
```

### Common Uses

* Unique elements
* Distinct values
* Visited nodes

---

## 2. contains()

Check whether an element exists.

```java
set.contains(20);
```

Result:

```text
true
```

### Common Uses

* Duplicate detection
* Fast lookup
* Graph traversal

---

## 3. remove()

Delete an element.

```java
set.remove(20);
```

Result:

```text
[10,30]
```

### Common Uses

* Sliding Window
* Dynamic sets

---

## 4. size()

Returns total elements.

```java
set.size();
```

Result:

```text
2
```

### Common Uses

* Count distinct elements

---

## 5. isEmpty()

Checks whether set is empty.

```java
set.isEmpty();
```

Result:

```text
true / false
```

---

## 6. clear()

Removes all elements.

```java
set.clear();
```

Result:

```text
[]
```

---

## 7. iterator()

Returns an iterator.

```java
Iterator<Integer> it = set.iterator();

while(it.hasNext())
{
    System.out.println(it.next());
}
```

### Common Uses

Rare in DSA.

Mostly Java Collection usage.

---

# Traversing a HashSet

## Enhanced For Loop

```java
for(int num : set)
{
    System.out.println(num);
}
```

Output:

```text
10
20
30
```

Most common traversal method.

---

# Common DSA Patterns

## Duplicate Detection

```java
HashSet<Integer> set = new HashSet<>();

for(int num : arr)
{
    if(set.contains(num))
    {
        System.out.println("Duplicate Found");
    }

    set.add(num);
}
```

### Uses

* Contains Duplicate
* Repeated Elements

---

## Count Distinct Elements

```java
HashSet<Integer> set = new HashSet<>();

for(int num : arr)
{
    set.add(num);
}

System.out.println(set.size());
```

### Uses

* Distinct count
* Unique elements

---

## Longest Consecutive Sequence

LeetCode Classic.

```java
HashSet<Integer> set = new HashSet<>();

for(int num : nums)
{
    set.add(num);
}

for(int num : set)
{
    if(!set.contains(num - 1))
    {
        int current = num;
        int length = 1;

        while(set.contains(current + 1))
        {
            current++;
            length++;
        }
    }
}
```

### Uses

* Longest Consecutive Sequence
* Number lookup problems

---

## Visited Array Alternative

```java
HashSet<Integer> visited =
        new HashSet<>();

visited.add(node);

if(visited.contains(node))
{
    continue;
}
```

### Uses

* DFS
* BFS
* Graph problems

---

## Remove Duplicates

```java
HashSet<Integer> set =
        new HashSet<>();

for(int num : arr)
{
    set.add(num);
}
```

Input:

```text
1 1 1 2 2 3 4
```

Output:

```text
1 2 3 4
```

### Uses

* Remove duplicates
* Unique collections

---

# DSA Cheat Sheet

## Must Know Methods

```java
add()
contains()
remove()
size()
clear()
isEmpty()
```

---

## Good To Know

```java
iterator()
```

---

# Interview Rule

Use HashSet when:

```text
Need uniqueness
Need duplicate detection
Need fast lookup
Need visited tracking
Need distinct elements
```

Use HashMap when:

```text
Need frequencies
Need indices
Need key-value mapping
Need extra information per key
```

---

# Most Common HashSet Problems

```text
Contains Duplicate
Longest Consecutive Sequence
Happy Number
Intersection of Arrays
Remove Duplicates
Graph Traversal
Cycle Detection
Visited Nodes
```

---

# One-Line Memory Trick

```text
HashSet = "Have I seen this before?"

HashMap = "Tell me everything about this."
```
