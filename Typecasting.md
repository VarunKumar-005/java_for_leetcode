# TYPE-CASTING
## Ranking the DataTypes based on size
```java
bit (1 unit) -> byte (8 bits) -> char(1 byte) -> int (2 bytes) -> long (4 bytes) -> double (8 bytes) -> long .........
```
---
## Types
There are two types of casting they are **Explicit** & **Implicit** typecasting
### Implicit Type Casting
Type casting is automatic we need not to mannually cast anything this happens only if 
the DataType(DT) is increasing 
#### Note but the char gives ASCII to the int to get the int do  
```java
char c = '5'
int a = c - '0' // to get exact number not in ASCII format
```
---
### Explicit Type Casting
From larger size DT to smaller DT
```java
int i = 65;

// int → byte (possible overflow)
byte b = (byte) i;   // 65 → 65, but 130 → -126

// int → char
char c = (char) i;   // 65 → 'A'

// int → long
long l = (long) i;   // widening, but explicit cast allowed

// int → float/double
float f = (float) i; // 65.0
double d = (double) i; // 65.0

// double → int (truncation)
double pi = 3.14159;
int truncated = (int) pi; // 3

// boolean → (no numeric cast allowed!)
boolean flag = true;
// int x = (int) flag; // ❌ compile error

```
