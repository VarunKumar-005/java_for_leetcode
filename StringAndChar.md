# 📚 String and Array Functions

## Basic Concepts

---

## 1️⃣ Initializing

### Character

```java
char ch = 'A';
```

### String

```java
String str = "Hello";
```

### Character Array

```java
char[] arr = {'H', 'e', 'l', 'l', 'o'};
```

### String Array

```java
String[] words = {"Java", "Python", "C++"};
```

---

## 2️⃣ Accessing Elements

### Character

```java
char ch = 'A';

System.out.println(ch);
```

### Output

```text
A
```

---

### Entire String

```java
String str = "Hello";

System.out.println(str);
```

### Output

```text
Hello
```

---

### Access a Character from a String

```java
String str = "Hello";

char ch = str.charAt(0);

System.out.println(ch);
```

### Output

```text
H
```

---

### Access Character Array Elements

```java
char[] arr = {'H', 'e', 'l', 'l', 'o'};

System.out.println(arr[0]);
System.out.println(arr[1]);
```

### Output

```text
H
e
```

---

### Access String Array Elements

```java
String[] words = {"Java", "Python", "C++"};

System.out.println(words[0]);
System.out.println(words[1]);
```

### Output

```text
Java
Python
```

---

## 3️⃣ Length

### String Length

```java
String str = "Hello";

System.out.println(str.length());
```

### Output

```text
5
```

---

### Character Array Length

```java
char[] arr = {'H', 'e', 'l', 'l', 'o'};

System.out.println(arr.length);
```

### Output

```text
5
```

---

### String Array Length

```java
String[] words = {"Java", "Python", "C++"};

System.out.println(words.length);
```

### Output

```text
3
```

---

## 4️⃣ Convert String to Character Array

```java
String str = "Hello";

char[] arr = str.toCharArray();
```

### Traversing

```java
for(char ch : arr)
{
    System.out.print(ch + " ");
}
```

### Output

```text
H e l l o
```

---

## 5️⃣ Convert Character Array to String

```java
char[] arr = {'H', 'e', 'l', 'l', 'o'};

String str = new String(arr);
```

### Output

```text
Hello
```

---

# 🚀 Special String Functions

---

## 1. charAt()

Returns the character at a given index.

```java
String s = "Hello";

System.out.println(s.charAt(1));
```

### Output

```text
e
```

---

## 2. substring()

Extracts part of a string.

```java
String s = "Hello";

System.out.println(s.substring(1, 4));
```

### Output

```text
ell
```

### Index Visualization

```text
H e l l o
0 1 2 3 4
```

---

## 3. toCharArray()

Converts String → Character Array.

```java
String s = "Hello";

char[] arr = s.toCharArray();
```

---

## 4. equals()

Compares string contents.

```java
String s1 = "Java";
String s2 = "Java";

System.out.println(s1.equals(s2));
```

### Output

```text
true
```

---

### Never Use

```java
s1 == s2
```

for content comparison.

Use:

```java
s1.equals(s2)
```

---

## 5. contains()

Checks whether a substring exists.

```java
String s = "Hello World";

System.out.println(s.contains("World"));
```

### Output

```text
true
```

---

## 6. replace()

Replaces characters or strings.

```java
String s = "Hello";

System.out.println(s.replace('l', 'x'));
```

### Output

```text
Hexxo
```

---

### Replace Word

```java
String s = "I love Java";

System.out.println(s.replace("Java", "Python"));
```

### Output

```text
I love Python
```

---

## 7. split()

Splits a string into an array.

```java
String s = "Java,Python,C++";

String[] arr = s.split(",");
```

### Traversal

```java
for(String word : arr)
{
    System.out.println(word);
}
```

### Output

```text
Java
Python
C++
```

---

## 8. trim()

Removes spaces from the beginning and end.

```java
String s = "   Hello World   ";

System.out.println(s.trim());
```

### Output

```text
Hello World
```

---

### Useful Interview Pattern

```java
String s = "      ";

System.out.println(s.trim().isEmpty());
```

### Output

```text
true
```

---

# 🎯 Common DSA Patterns

## Traverse a String

```java
String s = "Hello";

for(int i = 0; i < s.length(); i++)
{
    System.out.println(s.charAt(i));
}
```

---

## Reverse a String

```java
String s = "Hello";

for(int i = s.length() - 1; i >= 0; i--)
{
    System.out.print(s.charAt(i));
}
```

### Output

```text
olleH
```

---

## Count Character Frequency

```java
String s = "banana";

int[] freq = new int[26];

for(char ch : s.toCharArray())
{
    freq[ch - 'a']++;
}
```

### Example

```java
System.out.println(freq['a' - 'a']);
```

### Output

```text
3
```

---

## Compare Two Strings

```java
String s1 = "Java";
String s2 = "Java";

if(s1.equals(s2))
{
    System.out.println("Equal");
}
```

### Output

```text
Equal
```

---

# ⚡ DSA Cheat Sheet

## Most Used String Functions

```java
s.length()
s.charAt(i)
s.substring(a,b)
s.toCharArray()
s.equals(str)
s.contains(str)
s.replace(a,b)
s.split(regex)
s.trim()
```

## Most Used Array Operations

```java
arr.length
arr[i]
for(char ch : arr)
for(String word : arr)
```

## String ↔ Array Conversion

```java
char[] arr = s.toCharArray();

String s = new String(arr);
```

---

# 🏆 Interview Rule

Master these methods:

```java
charAt()
length()
substring()
toCharArray()
equals()
split()
trim()
replace()
contains()
```

These alone are enough to solve a huge percentage of beginner and intermediate String problems on LeetCode and coding interviews.