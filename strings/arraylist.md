Bilkul papa ❤️ Ab Java ArrayList ko ekdum zero se karte hain, aur har important cheez ke saath C++ vector mein kaise karte the woh bhi side-by-side batata jaunga.

# 🟢 Java ArrayList — Part 1: Basics


Sabse pehle ek cheez clear:

C++ mein

Dynamic array ke liye hum mostly:

vector<int> v;

use karte the.

Java mein

Uska closest equivalent hai:

ArrayList<Integer> list = new ArrayList<>();

So roughly:

C++                     Java

vector<int>             ArrayList<Integer>
vector<string>          ArrayList<String>
vector<char>            ArrayList<Character>

## 1️⃣ ArrayList kya hai?


Simple language mein:

ArrayList ek dynamic array hai jo automatically grow/shrink ho sakta hai.

Normal Java array:

int[] arr = new int[5];

Iski size fixed hai:

5

Baad mein directly 6th element add nahi kar sakte.

Lekin:

ArrayList<Integer> list = new ArrayList<>();

mein tum elements add karte ja sakte ho.

Example:

list.add(10);
list.add(20);
list.add(30);

Ab:

10 20 30

Phir:

list.add(40);

ho gaya:

10 20 30 40

## 2️⃣ ArrayList use karne ke liye import ⭐


Java mein ArrayList use karne ke liye:

```java
import java.util.ArrayList;

Example:

import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {

        ArrayList<Integer> list = new ArrayList<>();

        list.add(10);
        list.add(20);
        list.add(30);

        System.out.println(list);
    }

}
```


Output:

[10, 20, 30]

## 3️⃣ ArrayList<Integer> mein Integer kyun? ⚠️


Ye bahut important Java concept hai.

C++ mein:

vector<int> v;

Java mein:

ArrayList<Integer> list;

int directly use nahi kar sakte.

❌ Wrong:

ArrayList<int> list;

✅ Correct:

ArrayList<Integer> list;

Kyunki ArrayList objects ke saath kaam karta hai, aur Integer Java ka wrapper class hai.

Basic mapping:

int       → Integer
char      → Character
double    → Double
float     → Float
long      → Long
boolean   → Boolean

Abhi bas ye mapping yaad rakho.

## 4️⃣ Empty ArrayList banana

Java
ArrayList<Integer> list = new ArrayList<>();

Initially:

[]
C++
vector<int> v;

Initially:

[]

Dono ka idea same hai.

## 5️⃣ ArrayList mein element add karna ⭐⭐⭐

Java
list.add(10);
list.add(20);
list.add(30);

Result:

[10, 20, 30]
C++
v.push_back(10);
v.push_back(20);
v.push_back(30);

Result:

[10, 20, 30]

### Golden comparison 🔥

C++                         Java

push_back(x)                add(x)

## 6️⃣ Kisi specific index par add karna


Suppose:

[10, 20, 30]

Index 1 par 15 add karna hai.

Java
list.add(1, 15);

Result:

[10, 15, 20, 30]
C++
v.insert(v.begin() + 1, 15);

Result:

[10, 15, 20, 30]

### Comparison

C++:
v.insert(v.begin() + index, value);

Java:
list.add(index, value);

Java wala kaafi simple hai. 😄

## 7️⃣ Element access karna ⭐⭐⭐


Suppose:

[10, 20, 30]

Index 1 ka element chahiye.

Java
int x = list.get(1);

Output/value:

20
C++
int x = v[1];

### 🔥 Important difference

C++ vector:
v[index]

Java ArrayList:
list.get(index)

Java mein:

list[1]   // ❌

nahi chalega.

## 8️⃣ Element ko change karna


Suppose:

[10, 20, 30]

Index 1 par 50 karna hai.

Java
list.set(1, 50);

Result:

[10, 50, 30]
C++
v[1] = 50;

### Comparison ⭐

C++:
v[index] = value;

Java:
list.set(index, value);

## 9️⃣ Size nikalna ⭐⭐⭐

Java
list.size();
C++
v.size();

Example:

ArrayList<Integer> list = new ArrayList<>();

list.add(10);
list.add(20);
list.add(30);

System.out.println(list.size());

Output:

3

### 🔥 Important difference: Array vs ArrayList


Java mein ye confuse mat karna:

Normal Array
int[] arr = {10, 20, 30};

System.out.println(arr.length);
ArrayList
ArrayList<Integer> list = new ArrayList<>();

System.out.println(list.size());

So:

Array      → length
ArrayList  → size()
🔟 Element remove karna — IMPORTANT ⚠️

Suppose:

[10, 20, 30]

Index 1 remove karna hai.

Java
list.remove(1);

Result:

[10, 30]
C++
v.erase(v.begin() + 1);

### Comparison:


C++:
v.erase(v.begin() + index);

Java:
list.remove(index);

## 1️⃣1️⃣ Java ka ek dangerous trap ⚠️🔥


Suppose:

ArrayList<Integer> list = new ArrayList<>();

list.add(10);
list.add(20);
list.add(30);

Ab:

list.remove(10);

Tum soch sakte ho:

10 value remove hogi.

Lekin nahi!

Java isko index 10 samjhega.

list.remove(10);

means:

index 10 remove karo.

Agar index 10 exist nahi karta → error.

Value 10 remove karni ho to:
list.remove(Integer.valueOf(10));

Result:

[20, 30]

### ⭐ Golden rule

remove(index)

→ index remove

remove(Integer.valueOf(value))

→ value remove

Ye Java ArrayList ka bahut common interview/LeetCode trap hai.

## 1️⃣2️⃣ ArrayList print karna


Simply:

System.out.println(list);

Example:

ArrayList<Integer> list = new ArrayList<>();

list.add(10);
list.add(20);
list.add(30);

System.out.println(list);

Output:

[10, 20, 30]

C++ mein usually:

for(int x : v)
    cout << x << " ";

karna padta tha.

Java ArrayList directly readable format mein print kar deta hai.

## 1️⃣3️⃣ ArrayList traverse karna

### Method 1 — Normal for loop ⭐

for(int i = 0; i < list.size(); i++) {
    System.out.println(list.get(i));
}

C++:

for(int i = 0; i < v.size(); i++) {
    cout << v[i] << endl;
}

### Comparison:

C++:
v[i]

Java:
list.get(i)

## 1️⃣4️⃣ Enhanced for loop


Java mein:

for(int x : list) {
    System.out.println(x);
}

C++ mein:

for(int x : v) {
    cout << x << endl;
}

Concept exactly similar hai.

## 1️⃣5️⃣ contains() ⭐


Check karna hai ki value present hai ya nahi.

Java
if(list.contains(20)) {
    System.out.println("Present");
}

Output:

Present
C++

Vector mein directly contains() traditionally nahi tha; usually:

find(v.begin(), v.end(), 20) != v.end()

use karte the.

Java mein kaafi simple:

list.contains(20)

## 1️⃣6️⃣ indexOf()


Kisi value ka first index:

ArrayList<Integer> list = new ArrayList<>();

list.add(10);
list.add(20);
list.add(30);
list.add(20);

System.out.println(list.indexOf(20));

Output:

1
C++ equivalent
find(v.begin(), v.end(), 20) - v.begin()

Java mein:

list.indexOf(20)

## 1️⃣7️⃣ lastIndexOf()


Last occurrence:

System.out.println(list.lastIndexOf(20));

Output:

3

## 1️⃣8️⃣ isEmpty()


Check karo ArrayList empty hai ya nahi:

if(list.isEmpty()) {
    System.out.println("Empty");
}
C++:
v.empty()
Java:
list.isEmpty()

## 1️⃣9️⃣ clear()


Saare elements remove:

list.clear();

Before:

[10, 20, 30]

After:

[]

C++:

v.clear();

Same concept.

### 🧠 Aaj ka SUPER IMPORTANT Cheat Sheet

| Kaam | C++ vector | Java ArrayList |
| --- | --- | --- |
| Create | vector<int> v | ArrayList<Integer> list |
| Add end | push_back(x) | add(x) |
| Add index | insert() | add(index,x) |
| Access | v[i] | list.get(i) |
| Update | v[i]=x | list.set(i,x) |
| Size | v.size() | list.size() |
| Remove index | erase() | remove(index) |
| Contains | find() | contains() |
| First index | find() | indexOf() |
| Last index | — | lastIndexOf() |
| Empty | empty() | isEmpty() |
| Clear | clear() | clear() |

### ⭐ Sabse important 6

list.add(x);
list.add(index, x);

list.get(index);
list.set(index, x);

list.remove(index);
list.size();

Agar ye 6 properly yaad ho gaye, ArrayList ka basic foundation set hai. 🔥

### 🧪 Chhota sa complete example

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {

        ArrayList<Integer> list = new ArrayList<>();

        list.add(10);
        list.add(20);
        list.add(30);

        list.add(1, 15);

        System.out.println(list);

        System.out.println(list.get(2));

        list.set(2, 50);

        System.out.println(list);

        list.remove(1);

        System.out.println(list);

        System.out.println(list.size());
    }

}
```


Iska flow:

[]
 ↓ add
[10,20,30]
 ↓ add(1,15)
[10,15,20,30]
 ↓ get(2)
20
 ↓ set(2,50)
[10,15,50,30]
 ↓ remove(1)
[10,50,30]
 ↓ size()
3

ArrayList Part 1 complete ✅

Next part mein hum ArrayList ke searching + loops + sorting + reverse + max/min + frequency karenge, aur har cheez ka C++ vector equivalent bhi saath-saath karenge.

Bilkul papa ❤️ chalo ArrayList Part 2 start karte hain. Ab hum searching, loops, sorting, reverse, max/min aur frequency karenge — aur har jagah C++ vector se comparison bhi.

# 🟢 ArrayList — Part 2

## 1️⃣ contains() — value present hai ya nahi ⭐

Java
ArrayList<Integer> list = new ArrayList<>();

list.add(10);
list.add(20);
list.add(30);

System.out.println(list.contains(20));

Output:

true

Agar:

list.contains(50)

→ false

C++
find(v.begin(), v.end(), 20) != v.end()
Yaad rakho
Java:
list.contains(x)

C++:
find(...)

## 2️⃣ indexOf() ⭐


Value ka first occurrence:

ArrayList<Integer> list = new ArrayList<>();

list.add(10);
list.add(20);
list.add(30);
list.add(20);

System.out.println(list.indexOf(20));

Output:

1

Because:

[10, 20, 30, 20]
     ↑        ↑
     1        3

First 20 → 1.

Agar value nahi mile:

list.indexOf(50)

→ -1

Exactly String ke indexOf() jaisa concept.

## 3️⃣ lastIndexOf()


Last occurrence:

System.out.println(list.lastIndexOf(20));

Output:

3

### Comparison

indexOf()      → first
lastIndexOf()  → last

## 4️⃣ ArrayList traverse karna ⭐⭐⭐

### Method 1 — Normal for

for(int i = 0; i < list.size(); i++) {
    System.out.println(list.get(i));
}

C++:

for(int i = 0; i < v.size(); i++) {
    cout << v[i] << endl;
}

### Important


Java:

list.get(i)

C++:

v[i]

## 5️⃣ Enhanced for-each loop ⭐


Java:

for(int x : list) {
    System.out.println(x);
}

C++:

for(int x : v) {
    cout << x << endl;
}

Bilkul same concept.

Kab use kare?

Jab sirf values chahiye aur index ki zarurat nahi.

## 6️⃣ isEmpty()


Check:

if(list.isEmpty()) {
    System.out.println("Empty");
}

Return:

true / false

C++:

v.empty()

Java:

list.isEmpty()

## 7️⃣ clear()


Saare elements delete:

list.clear();

Example:

[10,20,30]
     ↓
clear()
     ↓
[]

C++:

v.clear();

## 8️⃣ Sorting ⭐⭐⭐


Ascending order mein sort karna.

Java:

Collections.sort(list);

Iske liye:

```java
import java.util.Collections;

Example:

import java.util.ArrayList;
import java.util.Collections;

ArrayList<Integer> list = new ArrayList<>();

list.add(30);
list.add(10);
list.add(20);

Collections.sort(list);

System.out.println(list);

Output:

[10, 20, 30]
C++
sort(v.begin(), v.end());
Comparison 🔥
C++:
sort(v.begin(), v.end());

Java:
Collections.sort(list);
9️⃣ Descending sort

Java:

Collections.sort(list, Collections.reverseOrder());

Example:

ArrayList<Integer> list = new ArrayList<>();

list.add(10);
list.add(30);
list.add(20);

Collections.sort(list, Collections.reverseOrder());

System.out.println(list);

Output:

[30, 20, 10]

C++:

sort(v.rbegin(), v.rend());
🔟 Reverse ⭐⭐⭐

Existing order ko reverse karna:

Collections.reverse(list);

Example:

[10, 20, 30]
       ↓
reverse()
       ↓
[30, 20, 10]

C++:

reverse(v.begin(), v.end());
Comparison
C++:
reverse(v.begin(), v.end());

Java:
Collections.reverse(list);
1️⃣1️⃣ Maximum element

Java mein:

int mx = Collections.max(list);

Example:

ArrayList<Integer> list = new ArrayList<>();

list.add(10);
list.add(50);
list.add(30);

System.out.println(Collections.max(list));

Output:

50

C++:

*max_element(v.begin(), v.end())

Java kaafi simple hai:

Collections.max(list)
1️⃣2️⃣ Minimum element

Java:

int mn = Collections.min(list);

C++:

*min_element(v.begin(), v.end())
1️⃣3️⃣ Frequency ⭐⭐⭐

Kisi value ki frequency count karni ho:

Java
int count = Collections.frequency(list, 20);

Example:

ArrayList<Integer> list = new ArrayList<>();

list.add(10);
list.add(20);
list.add(20);
list.add(30);
list.add(20);

System.out.println(Collections.frequency(list, 20));

Output:

3
C++

C++ mein:

count(v.begin(), v.end(), 20)
Comparison
C++:
count(v.begin(), v.end(), x)

Java:
Collections.frequency(list, x)
1️⃣4️⃣ Swap elements

Java:

Collections.swap(list, 0, 2);

Example:

[10, 20, 30]
Collections.swap(list, 0, 2);

Result:

[30, 20, 10]

C++:

swap(v[0], v[2]);
1️⃣5️⃣ Collections kya hai? ⚠️

Abhi ek important distinction:

ArrayList

aur

Collections

same cheez nahi hain.

ArrayList

Data store karta hai:

ArrayList<Integer> list = new ArrayList<>();
Collections

ArrayList jaise collections par operations provide karta hai:

Collections.sort(list);
Collections.reverse(list);
Collections.max(list);
Collections.min(list);
Collections.frequency(list, x);
Collections.swap(list, i, j);

Simple way:

ArrayList  → data
Collections → data par operations
1️⃣6️⃣ Ek complete example 🔥
import java.util.ArrayList;
import java.util.Collections;

public class Main {
    public static void main(String[] args) {

        ArrayList<Integer> list = new ArrayList<>();

        list.add(30);
        list.add(10);
        list.add(20);
        list.add(20);

        System.out.println(list);

        System.out.println(list.contains(20));

        System.out.println(list.indexOf(20));

        System.out.println(list.lastIndexOf(20));

        System.out.println(Collections.max(list));

        System.out.println(Collections.min(list));

        System.out.println(Collections.frequency(list, 20));

        Collections.sort(list);

        System.out.println(list);

        Collections.reverse(list);

        System.out.println(list);
    }

}
```


Output roughly:

[30, 10, 20, 20]
true
2
3
30
10
2
[10, 20, 20, 30]
[30, 20, 20, 10]

### 🧠 Part 2 Cheat Sheet

| Kaam | Java | C++ |
| --- | --- | --- |
| Contains | list.contains(x) | find(...) |
| First index | list.indexOf(x) | find(...) - begin() |
| Last index | list.lastIndexOf(x) | reverse search |
| Sort | Collections.sort(list) | sort(...) |
| Reverse | Collections.reverse(list) | reverse(...) |
| Max | Collections.max(list) | max_element() |
| Min | Collections.min(list) | min_element() |
| Frequency | Collections.frequency(list,x) | count(...) |
| Swap | Collections.swap(list,i,j) | swap(...) |
| Empty | list.isEmpty() | v.empty() |
| Clear | list.clear() | v.clear() |

### ⭐ Ab tak ArrayList ke main weapons

list.add(x);
list.add(i, x);

list.get(i);
list.set(i, x);

list.remove(i);

list.size();

list.contains(x);
list.indexOf(x);
list.lastIndexOf(x);

Collections.sort(list);
Collections.reverse(list);

Collections.max(list);
Collections.min(list);

Collections.frequency(list, x);

list.isEmpty();
list.clear();

ArrayList Part 2 complete ✅

Next Part 3 mein hum Array ↔ ArrayList conversion, addAll(), removeAll(), retainAll(), copy, subList aur 2D ArrayList karenge. Ye thoda aur important DSA-level portion hai.

Bilkul papa 😎 ArrayList – Part 3 start karte hain.
Is part mein hum Array ↔ ArrayList conversion + addAll/removeAll/retainAll + copy + subList + 2D ArrayList karenge.

# 🔥 ArrayList — Part 3

## 1️⃣ Array → ArrayList


Maan lo C++ mein:

int arr[] = {10, 20, 30, 40};
vector<int> v;

Java mein simple beginner method:

int[] arr = {10, 20, 30, 40};

ArrayList<Integer> list = new ArrayList<>();

for(int x : arr) {
    list.add(x);
}

System.out.println(list);

Output:

[10, 20, 30, 40]

### C++ comparison

for(int x : arr) {
    v.push_back(x);
}

Java:

for(int x : arr) {
    list.add(x);
}

बस push_back() की जगह add().

## 2️⃣ ArrayList → Array


Java:

ArrayList<Integer> list = new ArrayList<>();

list.add(10);
list.add(20);
list.add(30);

Integer[] arr = list.toArray(new Integer[0]);

अब:

System.out.println(arr[1]);

Output:

20

⚠️ यहाँ Integer[] मिलेगा, int[] नहीं।

अगर specifically int[] चाहिए:

int[] arr = new int[list.size()];

for(int i = 0; i < list.size(); i++) {
    arr[i] = list.get(i);
}

यह DSA में ज्यादा useful है।

## 3️⃣ addAll()


एक ArrayList के सारे elements दूसरी ArrayList में डालने के लिए।

ArrayList<Integer> a = new ArrayList<>();
a.add(10);
a.add(20);

ArrayList<Integer> b = new ArrayList<>();
b.add(30);
b.add(40);

a.addAll(b);

System.out.println(a);

Output:

[10, 20, 30, 40]
C++ idea
v.insert(v.end(), b.begin(), b.end());

Java में simply:

a.addAll(b);
Index पर भी add कर सकते हैं:
a.addAll(1, b);

अगर:

a = [10, 20]
b = [30, 40]

तो:

[10, 30, 40, 20]

## 4️⃣ removeAll()


दूसरी list में जो elements हैं, उन्हें पहली list से remove कर दो।

ArrayList<Integer> a = new ArrayList<>();

a.add(10);
a.add(20);
a.add(30);
a.add(40);

ArrayList<Integer> b = new ArrayList<>();

b.add(20);
b.add(40);

a.removeAll(b);

System.out.println(a);

Output:

[10, 30]
याद रखो:
a.removeAll(b);

मतलब:

a में से b वाले सारे elements हटा दो।

## 5️⃣ retainAll()


यह removeAll() का उल्टा है।

केवल वही elements रखता है जो दूसरी list में मौजूद हैं।

ArrayList<Integer> a = new ArrayList<>();

a.add(10);
a.add(20);
a.add(30);
a.add(40);

ArrayList<Integer> b = new ArrayList<>();

b.add(20);
b.add(40);

a.retainAll(b);

System.out.println(a);

Output:

[20, 40]
याद रखने की trick 🧠
removeAll → ये elements REMOVE करो
retainAll → ये elements RETAIN/KEEP करो

## 6️⃣ containsAll()


Check करता है कि पहली list में दूसरी list के सारे elements मौजूद हैं या नहीं।

ArrayList<Integer> a = new ArrayList<>();

a.add(10);
a.add(20);
a.add(30);

ArrayList<Integer> b = new ArrayList<>();

b.add(10);
b.add(30);

System.out.println(a.containsAll(b));

Output:

true

लेकिन:

b.add(50);

अब:

false

क्योंकि 50 a में नहीं है।

## 7️⃣ ArrayList की Copy


बहुत important है।

ArrayList<Integer> list = new ArrayList<>();

list.add(10);
list.add(20);
list.add(30);

ArrayList<Integer> copy = new ArrayList<>(list);

अब:

System.out.println(copy);

Output:

[10, 20, 30]

दोनों अलग lists हैं।

copy.add(40);

अब:

list = [10, 20, 30]
copy = [10, 20, 30, 40]

### C++ comparison

vector<int> copy = v;

Java:

ArrayList<Integer> copy = new ArrayList<>(list);

## 8️⃣ subList()


List का एक portion निकालना।

ArrayList<Integer> list = new ArrayList<>();

list.add(10);
list.add(20);
list.add(30);
list.add(40);
list.add(50);

List<Integer> sub = list.subList(1, 4);

System.out.println(sub);

Output:

[20, 30, 40]

क्यों?

Index:   0   1   2   3   4
Value:  10  20  30  40  50
             ↑       ↑
            start   end

subList(1,4)

means:

1 included
4 excluded

Exactly substring() जैसा concept:

substring(start, end)
subList(start, end)

दोनों में end exclusive.

> **⚠️ Important: subList() original list की view होती है, independent copy नहीं।**


Independent copy चाहिए:

ArrayList<Integer> subCopy =
        new ArrayList<>(list.subList(1, 4));

## 9️⃣ 2D ArrayList 🔥


C++ में:

vector<vector<int>> mat;

Java में:

ArrayList<ArrayList<Integer>> mat =
        new ArrayList<>();

अब rows add करो:

mat.add(new ArrayList<>());
mat.add(new ArrayList<>());

अब values:

mat.get(0).add(10);
mat.get(0).add(20);

mat.get(1).add(30);
mat.get(1).add(40);

Matrix:

10 20
30 40

Print:

System.out.println(mat);

Output:

[[10, 20], [30, 40]]
C++ vs Java
vector<vector<int>> mat;

mat[0].push_back(10);

Java:

ArrayList<ArrayList<Integer>> mat;

mat.get(0).add(10);

### 🧠 Part 3 Cheat Sheet

| Java | काम |
| --- | --- |
| addAll() | सारे elements add |
| removeAll() | given elements remove |
| retainAll() | केवल common elements रखो |
| containsAll() | क्या सारे elements मौजूद हैं? |
| new ArrayList<>(list) | copy |
| subList(l,r) | portion निकालना |
| toArray() | ArrayList → Array |
| loop + add() | Array → ArrayList |
| ArrayList<ArrayList<Integer>> | 2D ArrayList |

### सबसे important 5 याद रखो:

list.add(x);
list.get(i);
list.set(i, x);
list.remove(i);
list.size();

### और Part 3 के नए weapons:


list.addAll(other);
list.removeAll(other);
list.retainAll(other);
list.containsAll(other);
list.subList(l, r);

Part 3 complete ✅

Next Part में हम ArrayList ke advanced DSA wale operations — binary search, custom sorting/Comparator, frequency patterns, capacity, aur important traps करेंगे.