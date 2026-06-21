# StringBuilder

## Definition

`StringBuilder` is a class in Java used to create and modify character sequences efficiently.

```java
StringBuilder sb = new StringBuilder("Hello");
```

Unlike `String`, its contents can be changed without creating a new object.

---

## Inheritance Hierarchy

```text
AbstractStringBuilder
           ↑
 ┌---------┴---------┐
 ↓                   ↓
StringBuilder    StringBuffer
```

> **Note:** `StringBuffer` is thread-safe because its methods are synchronized. However, it is slower than `StringBuilder`. Both share most of their implementation through `AbstractStringBuilder`.

---

# StringBuilder Functions

## 1. `append()`

Used to build strings efficiently.

```java
StringBuilder sb = new StringBuilder();

sb.append("Hello");
sb.append(" ");
sb.append("World");
```

### Result

```text
Hello World
```

### Common Uses

- Build output strings
- DFS/BFS path creation
- Generate answers
- String compression

---

## 2. `charAt()`

Access a character at a given index.

```java
StringBuilder sb = new StringBuilder("hello");

char ch = sb.charAt(1);
```

### Result

```text
e
```

### Common Uses

- Palindrome checking
- Two pointers
- Character comparison

---

## 3. `setCharAt()`

Modify a character at a specific index.

```java
StringBuilder sb = new StringBuilder("hello");

sb.setCharAt(0, 'H');
```

### Result

```text
Hello
```

### Common Uses

- In-place modifications
- Backtracking
- Character replacement

---

## 4. `length()`

Returns the current length.

```java
sb.length();
```

### Common Uses

Used almost everywhere.

```java
for(int i = 0; i < sb.length(); i++) {
    // logic
}
```

---

## 5. `delete()`

Removes a range of characters.

```java
StringBuilder sb = new StringBuilder("abcdef");

sb.delete(2, 4);
```

### Result

```text
abef
```

> Removes characters at indices `2` and `3`.

### Common Uses

- Backtracking
- Remove invalid characters
- String manipulation

---

## 6. `deleteCharAt()`

Removes a single character.

```java
sb.deleteCharAt(3);
```

### Common Uses

- Parentheses problems
- Backtracking

---

## 7. `insert()`

Inserts characters at a given position.

```java
StringBuilder sb = new StringBuilder("abcd");

sb.insert(2, "XYZ");
```

### Result

```text
abXYZcd
```

### Common Uses

- Formatting strings
- Constructing answers

---

## 8. `reverse()`

Reverses the sequence.

```java
StringBuilder sb = new StringBuilder("hello");

sb.reverse();
```

### Result

```text
olleh
```

### Common Uses

- Palindrome problems
- Reverse string
- Reverse words

---

## 9. `toString()`

Converts a `StringBuilder` back to a `String`.

```java
String result = sb.toString();
```

### Common Uses

Almost every `StringBuilder` problem ends with:

```java
return sb.toString();
```

---

# Bonus Methods

## `substring()`

Extracts a portion of the string.

```java
StringBuilder sb = new StringBuilder("abcdef");

String s = sb.substring(2, 5);
```

### Result

```text
cde
```

---

## `indexOf()`

Returns the first occurrence of a substring.

```java
sb.indexOf("abc");
```

### Common Uses

- Pattern searching
- String matching

---

## `lastIndexOf()`

Returns the last occurrence of a substring.

```java
sb.lastIndexOf("abc");
```

### Common Uses

- Reverse searching
- Finding repeated patterns

---

# DSA Cheat Sheet

## Must-Know Methods

```java
append()
charAt()
setCharAt()
length()
delete()
deleteCharAt()
insert()
reverse()
toString()
```

## Good to Know

```java
substring()
indexOf()
lastIndexOf()
```

### Interview Rule

If you're solving LeetCode, coding rounds, or DSA problems, mastering these **9 core methods** is enough to handle the vast majority of StringBuilder-based questions.