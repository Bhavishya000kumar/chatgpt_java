Bilkul papa ❤️ HashMap ko proper zero se karenge, aur is baar jaldi-jaldi functions ki list nahi maarunga. Har cheez:

Meaning → syntax → example → output → C++ comparison → DSA use

Aur end mein ek full revision cheat sheet bhi bana denge jisme dekhte hi yaad aa jaye ki kis function ka kya kaam hai. 🔥

# 🚀 Java HashMap — Part 1: Basic Understanding

## 1️⃣ HashMap hota kya hai?


Sabse pehle basic idea.

C++ mein tumne map / unordered_map dekha hai:

map<int, string> mp;
mp[101] = "Rahul";

Yahan:

101  →  Rahul

Matlab key → value.

Java mein isi type ka structure:

HashMap<Integer, String> map = new HashMap<>();

Aur:

map.put(101, "Rahul");

Ab:

Key     Value
101  →  Rahul

### 🧠 Simple definition


HashMap data ko key-value pair mein store karta hai.

Example:

Roll No → Student Name
101     → Rahul
102     → Aman
103     → Priya

## 2️⃣ HashMap banane ka syntax


Sabse pehle import:

```java
import java.util.HashMap;

Phir:

HashMap<Integer, String> map = new HashMap<>();

Iska matlab:

Integer → Key ka type
String  → Value ka type

So:

HashMap<Integer, String>

means:

Integer key aur String value.

3️⃣ Different types bhi ho sakte hain
Integer → Integer
HashMap<Integer, Integer> map = new HashMap<>();

Example:

1 → 100
2 → 200
3 → 300
Character → Integer

Frequency counting mein bahut important:

HashMap<Character, Integer> freq = new HashMap<>();

Example:

'a' → 3
'b' → 2
'c' → 1
String → Integer
HashMap<String, Integer> map = new HashMap<>();

Example:

"apple"  → 5
"banana" → 3
"mango"  → 7
4️⃣ put() — Data Add Karna 🔥

Sabse important function.

map.put(key, value);

Example:

HashMap<Integer, String> map = new HashMap<>();

map.put(101, "Rahul");
map.put(102, "Aman");
map.put(103, "Priya");

Map:

101 → Rahul
102 → Aman
103 → Priya
C++ comparison

C++:

mp[101] = "Rahul";

Java:

map.put(101, "Rahul");

🧠 put() = key-value pair daalo

5️⃣ get() — Value Nikalna

Agar key pata hai aur uski value chahiye:

map.get(key);

Example:

HashMap<Integer, String> map = new HashMap<>();

map.put(101, "Rahul");
map.put(102, "Aman");

System.out.println(map.get(101));

Output:

Rahul

Because:

101 → Rahul
C++
mp[101]

Java:

map.get(101)
6️⃣ Agar key exist nahi karti?
System.out.println(map.get(999));

Agar 999 map mein nahi hai:

null

⚠️ null ka matlab:

Is key ki value currently nahi mili.

7️⃣ containsKey() 🔥

Check karna hai ki key present hai ya nahi.

map.containsKey(key);

Ye true / false return karta hai.

Example:

HashMap<Integer, String> map = new HashMap<>();

map.put(101, "Rahul");
map.put(102, "Aman");

System.out.println(map.containsKey(101));
System.out.println(map.containsKey(500));

Output:

true
false
Real DSA use
if(map.containsKey(x)) {
    // x already present
}
```


## 8️⃣ containsValue()


Same concept, but value search karega.

map.containsValue(value);

Example:

System.out.println(map.containsValue("Rahul"));

Output:

true

Lekin DSA mein generally containsKey() zyada important hota hai.

## 9️⃣ remove() — Key Remove Karna

map.remove(key);

Example:

HashMap<Integer, String> map = new HashMap<>();

map.put(101, "Rahul");
map.put(102, "Aman");
map.put(103, "Priya");

map.remove(102);

Ab:

101 → Rahul
103 → Priya

### 🧠 Yaad rakho

map.remove(key);

Key ko remove karta hai aur uska associated value bhi chali jaati hai.

🔟 size()

Map mein kitne key-value pairs hain:

map.size();

Example:

map.put(101, "Rahul");
map.put(102, "Aman");
map.put(103, "Priya");

System.out.println(map.size());

Output:

3

## 1️⃣1️⃣ isEmpty()


Check karta hai map empty hai ya nahi.

map.isEmpty();

Example:

HashMap<Integer, String> map = new HashMap<>();

System.out.println(map.isEmpty());

Output:

true

Data add karne ke baad:

map.put(1, "A");

ab:

false

## 1️⃣2️⃣ clear()


Poora HashMap empty karna:

map.clear();

Example:

map.put(1, "A");
map.put(2, "B");

map.clear();

System.out.println(map.size());

Output:

0

## 1️⃣3️⃣ Existing Key par put() karoge toh? ⚠️


Ye bahut important hai.

HashMap<Integer, String> map = new HashMap<>();

map.put(101, "Rahul");
map.put(101, "Aman");

Ab kya hoga?

❌ Do entries nahi banengi.

Instead:

101 → Aman

Purani value "Rahul" replace/update ho jayegi.

### 🧠 Rule

map.put(key, newValue);

Agar key:

nahi hai → new pair add
already hai → old value update

## 1️⃣4️⃣ Duplicate Keys allowed nahi ❌

map.put(1, "A");
map.put(1, "B");
map.put(1, "C");

Final:

1 → C

Ek key ke saath ek hi current value hoti hai.

Lekin values duplicate ho sakti hain:

map.put(1, "A");
map.put(2, "A");
map.put(3, "A");

Allowed:

1 → A
2 → A
3 → A
🧠
Duplicate KEY     ❌
Duplicate VALUE   ✅

## 1️⃣5️⃣ HashMap mein null


Java HashMap null key aur null values ko allow karta hai.

Example:

HashMap<Integer, String> map = new HashMap<>();

map.put(null, "Unknown");
map.put(1, null);

Valid hai.

Beginner DSA mein iska use kam milega, bas concept yaad rakho.

### 🔥 Part 1 ka Real Example


Student marks store karte hain:

```java
import java.util.HashMap;

class Main {
    public static void main(String[] args) {

        HashMap<String, Integer> marks = new HashMap<>();

        marks.put("Rahul", 85);
        marks.put("Aman", 92);
        marks.put("Priya", 88);

        System.out.println(marks.get("Aman"));

        System.out.println(marks.containsKey("Rahul"));

        marks.put("Rahul", 95);

        System.out.println(marks.get("Rahul"));

        marks.remove("Priya");

        System.out.println(marks.size());
    }

}
```


Output:

92
true
95
2

Yahan dekho:

put()           → data add/update
get()            → value nikalo
containsKey()    → key hai?
remove()         → key hatao
size()           → total pairs

### 🧠 PART 1 REVISION CHEAT SHEET

HashMap<K,V>
     ↓
Key → Value
Create
HashMap<Integer, String> map = new HashMap<>();
Add / Update
map.put(key, value);
Value get
map.get(key);
Key exists?
map.containsKey(key);
Value exists?
map.containsValue(value);
Remove
map.remove(key);
Number of pairs
map.size();
Empty check
map.isEmpty();
Everything delete
map.clear();
Important rules
Key → unique
Value → duplicate allowed

put(existingKey, newValue)
→ old value replace

get(nonExistingKey)
→ null

### 🆚 C++ Quick Comparison

| C++ | Java |
| --- | --- |
| map<int,string> mp | HashMap<Integer,String> map |
| mp[key] = value | map.put(key,value) |
| mp[key] | map.get(key) |
| mp.find(key) | map.containsKey(key) |
| mp.erase(key) | map.remove(key) |
| mp.size() | map.size() |
| mp.empty() | map.isEmpty() |
| mp.clear() | map.clear() |


Ye HashMap ka Part 1 hai. ❤️
Part 2 mein hum HashMap ko traverse kaise karte hain — keySet(), values(), entrySet(), Map.Entry, for-each aur phir actual frequency counting start karenge.

Haan papa ❤️ chalo HashMap Part 2 start karte hain. Is part mein sabse important cheez hai HashMap ko traverse karna, kyunki DSA questions mein baar-baar yehi use hoga.

# 🔥 Java HashMap — Part 2

## 1️⃣ keySet() — saari Keys


Agar HashMap hai:

HashMap<Integer, String> map = new HashMap<>();

map.put(101, "Rahul");
map.put(102, "Aman");
map.put(103, "Priya");

Saari keys chahiye:

map.keySet();

Example:

for(int key : map.keySet()) {
    System.out.println(key);
}

Output order guaranteed nahi hai:

101
102
103

### 🧠 Meaning

map.keySet()

→ sirf keys ka collection

## 2️⃣ values() — saari Values

for(String value : map.values()) {
    System.out.println(value);
}

Output:

Rahul
Aman
Priya

### 🧠 Meaning

map.values()

→ sirf values

## 3️⃣ Key + Value dono chahiye → entrySet() 🔥


Ye bahut important hai.

for(Map.Entry<Integer, String> entry : map.entrySet()) {

    System.out.println(entry.getKey());
    System.out.println(entry.getValue());
}

Output conceptually:

101
Rahul

102
Aman

103
Priya

Yahan:

entry.getKey()

→ key

entry.getValue()

→ value

## 4️⃣ Map.Entry kya hai?


Isko simple language mein samjho.

Ek complete pair:

101 → Rahul

ek entry hai.

So:

Map.Entry<Integer, String>

means:

ek key-value pair.

Isliye:

for(Map.Entry<Integer, String> entry : map.entrySet())

means:

HashMap ki har key-value pair ko ek-ek karke entry mein lao.

## 5️⃣ Most Important Traversal Pattern 🧠


Ye pattern ratta nahi, samajh ke yaad karna:

for(Map.Entry<Integer, String> entry : map.entrySet()) {

    int key = entry.getKey();
    String value = entry.getValue();

    System.out.println(key + " -> " + value);
}

Output:

101 -> Rahul
102 -> Aman
103 -> Priya

DSA mein ye bahut kaam aayega.

## 6️⃣ C++ Comparison


C++ mein:

for(auto it : mp) {
    cout << it.first << " " << it.second;
}

Java:

for(Map.Entry<Integer, String> entry : map.entrySet()) {

    System.out.println(
        entry.getKey() + " " + entry.getValue()
    );
}

### Comparison:


C++                    Java
--------------------------------
it.first             → getKey()
it.second            → getValue()

## 7️⃣ keySet() se value kaise nikalenge?


Agar keys ke through traverse karna ho:

for(int key : map.keySet()) {

    System.out.println(
        key + " -> " + map.get(key)
    );
}

Example:

HashMap<Integer, String> map = new HashMap<>();

map.put(101, "Rahul");
map.put(102, "Aman");
map.put(103, "Priya");

for(int key : map.keySet()) {
    System.out.println(key + " -> " + map.get(key));
}

Output conceptually:

101 -> Rahul
102 -> Aman
103 -> Priya
Lekin recommended?

Agar key + value dono directly chahiye, toh:

entrySet()

better hai.

## 8️⃣ getOrDefault() 🔥🔥


Ab aata hai DSA ka sabse useful HashMap function.

Syntax:

map.getOrDefault(key, defaultValue);

Meaning:

Agar key present hai → uski value do.
Agar key present nahi hai → default value do.

Example:

HashMap<String, Integer> map = new HashMap<>();

map.put("apple", 5);

System.out.println(map.getOrDefault("apple", 0));
System.out.println(map.getOrDefault("banana", 0));

Output:

5
0

Because:

apple  → present → 5
banana → absent  → 0

## 9️⃣ Frequency Counting — getOrDefault() ka real use 🔥


Maan lo:

"banana"

Hume characters ki frequency nikalni hai.

Expected:

b → 1
a → 3
n → 2

Code:

HashMap<Character, Integer> freq = new HashMap<>();

String s = "banana";

for(char ch : s.toCharArray()) {

    freq.put(
        ch,
        freq.getOrDefault(ch, 0) + 1
    );
}

Ab map:

b → 1
a → 3
n → 2
Is line ko tod ke samjho:
freq.getOrDefault(ch, 0)

Pehli baar 'b':

b present nahi
→ 0

Then:

0 + 1 = 1

So:

freq.put('b', 1);

Next 'a':

a nahi hai
→ 0 + 1
→ 1

Next 'n':

n nahi hai
→ 0 + 1
→ 1

Next 'a':

a already 1
→ 1 + 1
→ 2

Next 'n':

n already 1
→ 1 + 1
→ 2

Next 'a':

a already 2
→ 2 + 1
→ 3

Final:

b → 1
a → 3
n → 2

### 🔥 Ye pattern bahut important hai.


🔟 putIfAbsent()

Meaning:

Agar key already present nahi hai tabhi value add karo.

map.putIfAbsent(101, "Rahul");

Example:

HashMap<Integer, String> map = new HashMap<>();

map.put(101, "Rahul");

map.putIfAbsent(101, "Aman");

System.out.println(map.get(101));

Output:

Rahul

Because 101 already present tha, "Aman" add nahi hua.

But:

map.putIfAbsent(102, "Aman");

Then:

102 → Aman
Difference 🧠
map.put(key, value);

→ existing value replace kar sakta hai.

map.putIfAbsent(key, value);

→ existing value replace nahi karega.

## 1️⃣1️⃣ replace()


Existing key ki value change karni ho:

map.replace(key, newValue);

Example:

HashMap<Integer, String> map = new HashMap<>();

map.put(101, "Rahul");

map.replace(101, "Aman");

System.out.println(map.get(101));

Output:

Aman

## 1️⃣2️⃣ replace() vs put()

map.put(101, "Aman");

Agar 101 nahi hai:

→ add karega.

Agar hai:

→ update karega.

map.replace(101, "Aman");

Agar 101 hai:

→ update karega.

Agar 101 nahi hai:

→ kuch add nahi karega.

🧠
put()     → Add OR Update
replace() → Only Update

### 🔥 Part 2 Final Revision

Keys:
map.keySet()

→ all keys

Values:
map.values()

→ all values

Key + Value:
map.entrySet()

→ all key-value pairs

Entry se:
entry.getKey()
entry.getValue()
Default value:
map.getOrDefault(key, 0)
Frequency:
freq.put(ch, freq.getOrDefault(ch, 0) + 1);
Only if absent:
map.putIfAbsent(key, value);
Update existing:
map.replace(key, value);

### 🧠 HashMap Traversal Cheat Sheet

keySet()     → keys
values()     → values
entrySet()   → key + value

getKey()     → key
getValue()   → value

getOrDefault() → value OR default
putIfAbsent()  → add only if key absent
replace()      → update existing key

### ⭐ DSA ke liye abhi sabse important pattern:

HashMap<Character, Integer> freq = new HashMap<>();

for(char ch : s.toCharArray()) {
    freq.put(ch, freq.getOrDefault(ch, 0) + 1);
}

HashMap Part 2 complete ✅
Next Part 3 mein hum frequency counting ko numbers + strings + characters par properly practice karenge, HashMap ke common DSA patterns, aur HashMap vs HashSet ka difference karen

Haan papa ❤️ chalo Java HashMap — Part 3 start karte hain.
Ab actual DSA mein HashMap ka use samjhenge. Ye part important hai, kyunki yahin se HashMap ka asli fayda samajh aayega. 🔥

# 🚀 HashMap — Part 3: Frequency & DSA Patterns

## 1️⃣ Number Frequency


Maan lo:

[10, 20, 10, 30, 20, 10]

Hume frequency chahiye:

10 → 3
20 → 2
30 → 1
Code

```java
import java.util.HashMap;

class Main {
    public static void main(String[] args) {

        int[] arr = {10, 20, 10, 30, 20, 10};

        HashMap<Integer, Integer> freq = new HashMap<>();

        for(int x : arr) {
            freq.put(x, freq.getOrDefault(x, 0) + 1);
        }


        System.out.println(freq);
    }
}
```


Conceptually output:

10=3, 20=2, 30=1

### 🧠 Main formula

freq.put(x, freq.getOrDefault(x, 0) + 1);

Isko frequency pattern samajh ke rakho.

## 2️⃣ Character Frequency


String:

"hello"

Frequency:

h → 1
e → 1
l → 2
o → 1

Code:

String s = "hello";

HashMap<Character, Integer> freq = new HashMap<>();

for(char ch : s.toCharArray()) {
    freq.put(ch, freq.getOrDefault(ch, 0) + 1);
}

## 3️⃣ Frequency ko Print Karna


Map ban gaya. Ab har key-value pair:

for(Map.Entry<Character, Integer> entry : freq.entrySet()) {

    System.out.println(
        entry.getKey() + " -> " + entry.getValue()
    );
}

Output:

h -> 1
e -> 1
l -> 2
o -> 1

> **⚠️ HashMap order guaranteed nahi hota, isliye output ka order different aa sakta hai.**


## 4️⃣ Kisi Element ki Frequency Directly Find Karna


Maan lo:

arr = [1, 2, 2, 3, 2, 4]

Frequency of 2:

HashMap<Integer, Integer> freq = new HashMap<>();

for(int x : arr) {
    freq.put(x, freq.getOrDefault(x, 0) + 1);
}

System.out.println(freq.get(2));

Output:

3

## 5️⃣ Duplicate Find Karna 🔥


Maan lo:

[1, 2, 3, 2, 4, 1]

Hume duplicate elements chahiye.

Simple HashMap approach:

int[] arr = {1, 2, 3, 2, 4, 1};

HashMap<Integer, Integer> freq = new HashMap<>();

for(int x : arr) {
    freq.put(x, freq.getOrDefault(x, 0) + 1);
}

for(Map.Entry<Integer, Integer> entry : freq.entrySet()) {

    if(entry.getValue() > 1) {
        System.out.println(entry.getKey());
    }
}

Output conceptually:

1
2

### Logic:

frequency > 1
       ↓
    duplicate

## 6️⃣ First Unique Element


Maan lo:

[4, 2, 4, 3, 2, 5]

Frequency:

4 → 2
2 → 2
3 → 1
5 → 1

First unique = 3.

Important: agar original array ka order preserve karke first unique nikalna hai, pehle frequency map banao, phir array ko dobara traverse karo:

int[] arr = {4, 2, 4, 3, 2, 5};

HashMap<Integer, Integer> freq = new HashMap<>();

for(int x : arr) {
    freq.put(x, freq.getOrDefault(x, 0) + 1);
}

for(int x : arr) {

    if(freq.get(x) == 1) {
        System.out.println(x);
        break;
    }
}

Output:

3

### 🔥 Pattern

Pass 1 → frequency count
Pass 2 → original order check

Ye pattern bahut questions mein aata hai.

## 7️⃣ Check Duplicate Exists or Not


Agar bas ye check karna hai:

Kya array mein koi duplicate hai?

Frequency map:

int[] arr = {1, 2, 3, 4, 2};

HashMap<Integer, Integer> freq = new HashMap<>();

for(int x : arr) {

    if(freq.containsKey(x)) {
        System.out.println("Duplicate exists");
        break;
    }

    freq.put(x, 1);
}
Yahan frequency ki zarurat bhi nahi hai.

Hum sirf check kar rahe:

freq.containsKey(x)

Agar already present:

duplicate

Otherwise:

freq.put(x, 1);

## 8️⃣ getOrDefault() vs containsKey()


Dono ka use samjho.

Frequency ke liye:
freq.put(x, freq.getOrDefault(x, 0) + 1);
Sirf existence check:
if(freq.containsKey(x))

### 🧠 Rule

Count chahiye      → getOrDefault()
Present hai?       → containsKey()

## 9️⃣ Count Characters of a String


Example:

"programming"

Code:

String s = "programming";

HashMap<Character, Integer> freq = new HashMap<>();

for(char ch : s.toCharArray()) {
    freq.put(ch, freq.getOrDefault(ch, 0) + 1);
}

Agar hume 'g' ki frequency chahiye:

System.out.println(freq.get('g'));
🔟 Most Frequent Element

Maan lo:

[1, 3, 2, 3, 4, 3, 2]

Frequency:

1 → 1
2 → 2
3 → 3
4 → 1

Hume 3 chahiye.

HashMap<Integer, Integer> freq = new HashMap<>();

for(int x : arr) {
    freq.put(x, freq.getOrDefault(x, 0) + 1);
}

int maxFreq = 0;
int answer = 0;

for(Map.Entry<Integer, Integer> entry : freq.entrySet()) {

    if(entry.getValue() > maxFreq) {
        maxFreq = entry.getValue();
        answer = entry.getKey();
    }
}

System.out.println(answer);

### Logic:


frequency compare karo
        ↓
maximum frequency wala element

> **⚠️ Agar tie ho, answer kis element ko choose karega ye question ki exact condition par depend karega.**


## 1️⃣1️⃣ Two Sum Pattern 🔥🔥


Ye HashMap ka sabse famous DSA pattern hai.

Array:

[2, 7, 11, 15]

Target:

9

Hume do numbers chahiye:

2 + 7 = 9
HashMap idea

Har number ke liye:

needed = target - current

Agar needed pehle map mein mil gaya → pair mil gaya.

int[] arr = {2, 7, 11, 15};
int target = 9;

HashMap<Integer, Integer> map = new HashMap<>();

for(int i = 0; i < arr.length; i++) {

    int needed = target - arr[i];

    if(map.containsKey(needed)) {
        System.out.println(
            map.get(needed) + " " + i
        );
        break;
    }

    map.put(arr[i], i);
}

### Dry run:


i=0
x=2
needed=7
7 nahi mila
map: 2 → 0

i=1
x=7
needed=2
2 mil gaya!

So indices:

0, 1

### 🧠 Two Sum formula

int needed = target - arr[i];

Then:

if(map.containsKey(needed))

> **🔥 Ye pattern future LeetCode questions mein bahut kaam aayega.**


## 1️⃣2️⃣ HashMap ka Main DSA Pattern


Ab tak ke patterns ko ek jagah dekho:

Pattern 1 — Frequency
map.put(x, map.getOrDefault(x, 0) + 1);
Pattern 2 — Existence
map.containsKey(x)
Pattern 3 — Get stored information
map.get(x)
Pattern 4 — Store information
map.put(x, value);
Pattern 5 — Complement / Two Sum
int needed = target - x;

if(map.containsKey(needed)) {
    // answer
}

### 🆚 HashMap vs ArrayList

| Kaam | ArrayList | HashMap |
| --- | --- | --- |
| Ordered elements | ✅ | ❌ guaranteed order |
| Index se access | ✅ | ❌ |
| Key-value | ❌ | ✅ |
| get(index) | O(1) | — |
| Search | O(n) | Average O(1) by key |
| Frequency | possible but inefficient | ⭐ Excellent |
| Duplicate allowed | ✅ | Keys ❌, values ✅ |

### 🔥 Important: HashMap vs C++ map


Java:

HashMap<Integer, Integer> map;

C++ ka closest conceptual equivalent:

unordered_map<int, int> mp;

Because both are hash-based.

C++:

map<int,int>

ordered tree-based map hai, jabki:

unordered_map<int,int>

hash-based hai.

Rough comparison
C++ map          → Tree based, O(log n)
C++ unordered_map → Hash based, average O(1)

Java HashMap     → Hash based, average O(1)

Java mein baad mein TreeMap bhi padhenge jo ordered-map concept ke closer hai.

### 🧠 PART 3 — REVISION CHEAT SHEET

Frequency
map.put(x, map.getOrDefault(x, 0) + 1);
Check existence
map.containsKey(x);
Get value
map.get(x);
First unique

## 1. frequency map banao

## 2. original data dobara traverse karo

## 3. frequency == 1 → answer

Duplicate
frequency > 1

or simply:

if(map.containsKey(x))
Two Sum
int needed = target - x;

if(map.containsKey(needed)) {
    // pair found
}
Traverse keys
for(int key : map.keySet())
Traverse values
for(int value : map.values())
Traverse key + value
for(Map.Entry<Integer, Integer> entry : map.entrySet()) {
    entry.getKey();
    entry.getValue();
}

### ⭐ Ab tak HashMap ke 3 parts ka complete toolkit

put()
get()
containsKey()
containsValue()
remove()
size()
isEmpty()
clear()

keySet()
values()
entrySet()
getKey()
getValue()

getOrDefault()
putIfAbsent()
replace()

frequency pattern
duplicate pattern
first unique pattern
most frequent pattern
Two Sum / complement pattern

HashMap Part 3 complete ✅

Next logical step hoga HashMap Part 4: advanced patterns + HashSet, jisme dekhenge ki kab HashMap use karna hai aur kab HashSet.

Haan papa ❤️ HashMap ka ye last learning part rakhte hain. Iske baad direct practice questions karenge. Aaj Part 4 mein remaining important concepts + HashSet complete kar dete hain.

# 🔥 Java HashMap — Part 4 FINAL

## 1️⃣ HashMap mein condition ke saath value update


Maan lo:

HashMap<String, Integer> marks = new HashMap<>();

marks.put("Aman", 80);
marks.put("Rahul", 90);

Aman ke marks 10 badhane hain:

marks.put("Aman", marks.get("Aman") + 10);

Now:

Aman → 90
Rahul → 90
Agar key exist hi nahi karti?

Safe way:

marks.put("Priya", marks.getOrDefault("Priya", 0) + 10);

Result:

Priya → 10

### 🔥 Isliye getOrDefault() DSA mein itna useful hai.


## 2️⃣ putIfAbsent() ka practical use


Maan lo hume kisi number ka first occurrence index store karna hai.

int[] arr = {10, 20, 10, 30, 20};

HashMap<Integer, Integer> map = new HashMap<>();

for(int i = 0; i < arr.length; i++) {
    map.putIfAbsent(arr[i], i);
}

Final:

10 → 0
20 → 1
30 → 3

Notice:

10 second time index 2 par aaya

Lekin putIfAbsent() ne old index 0 ko replace nahi kiya.

### 🧠 Pattern

First occurrence store karni ho
        ↓
putIfAbsent()

## 3️⃣ HashMap mein keys unique hoti hain


Example:

map.put(10, "A");
map.put(10, "B");

Final:

10 → B

Agar hume ek key ke saath multiple values rakhni ho, toh value khud ArrayList ho sakti hai:

HashMap<Integer, ArrayList<Integer>> map = new HashMap<>();

Ye advanced DSA mein kaafi useful hai.

Example:

Student ID → marks list
1 → [80, 90, 85]
2 → [70, 75]

Is concept ko Map of Lists bol sakte ho.

## 4️⃣ HashMap + ArrayList 🔥


Example:

HashMap<Integer, ArrayList<Integer>> map = new HashMap<>();

map.put(1, new ArrayList<>());

map.get(1).add(10);
map.get(1).add(20);
map.get(1).add(30);

System.out.println(map);

Output:

{1=[10, 20, 30]}

Agar key pehle se present nahi hai toh:

map.putIfAbsent(1, new ArrayList<>());
map.get(1).add(10);

Ye pattern later grouping problems mein kaam aayega.

## 5️⃣ Ab HashSet 🔥


HashMap ke baad HashSet samajhna bahut easy hai.

HashSet kya hai?

HashSet unique elements store karta hai.

C++ mein closest concept:

unordered_set<int> st;

Java:

HashSet<Integer> set = new HashSet<>();

Import:

```java
import java.util.HashSet;
6️⃣ HashSet mein add()
HashSet<Integer> set = new HashSet<>();

set.add(10);
set.add(20);
set.add(30);

Set:

10
20
30
7️⃣ Duplicate add karoge toh?
set.add(10);
set.add(10);
set.add(10);

Sirf:

10

rahega.

🧠 Rule
HashSet → duplicate elements ❌
8️⃣ contains()

Check karna hai element present hai ya nahi:

set.contains(20);

Returns:

true
set.contains(50);

Returns:

false
9️⃣ remove()
set.remove(20);

20 delete ho jayega.

🔟 size()
set.size();

Unique elements ki count dega.

Example:

HashSet<Integer> set = new HashSet<>();

set.add(10);
set.add(20);
set.add(10);

System.out.println(set.size());

Output:

2
1️⃣1️⃣ isEmpty() & clear()

Empty check:

set.isEmpty();

Sab delete:

set.clear();
1️⃣2️⃣ HashSet Traversal
for(int x : set) {
    System.out.println(x);
}
```



⚠️ HashSet ka order guaranteed nahi hai.

## 1️⃣3️⃣ HashMap vs HashSet 🔥🔥


Ye bahut important difference hai.

| HashMap | HashSet |
| --- | --- |
| Key → Value | Only elements |
| Duplicate keys ❌ | Duplicate elements ❌ |
| Values duplicate ho sakti hain | Duplicate nahi |
| put() | add() |
| get() | ❌ |
| containsKey() | contains() |
| remove(key) | remove(value) |

Example:

HashMap:

HashMap<Integer, String> map = new HashMap<>();

map.put(101, "Rahul");
101 → Rahul

HashSet:

HashSet<Integer> set = new HashSet<>();

set.add(101);
101

## 1️⃣4️⃣ Kab HashMap aur kab HashSet?

Sirf check karna hai:

Ye element pehle aa chuka hai?

Use:

HashSet<Integer> set

Example:

for(int x : arr) {

    if(set.contains(x)) {
        System.out.println("Duplicate");
        break;
    }

    set.add(x);
}
Frequency bhi chahiye:

Ye element kitni baar aaya?

Use:

HashMap<Integer, Integer> freq

Example:

freq.put(x, freq.getOrDefault(x, 0) + 1);

### 🧠 Golden Rule

Sirf presence → HashSet
Presence + information/count → HashMap

## 1️⃣5️⃣ Duplicate Check — HashSet


Array:

[1, 2, 3, 4, 2]

Code:

HashSet<Integer> set = new HashSet<>();

for(int x : arr) {

    if(set.contains(x)) {
        System.out.println("Duplicate: " + x);
        break;
    }

    set.add(x);
}

Output:

Duplicate: 2

Ye HashMap se bhi simpler hai.

## 1️⃣6️⃣ Unique Elements


Maan lo:

[10, 20, 10, 30, 20]

HashSet:

HashSet<Integer> set = new HashSet<>();

for(int x : arr) {
    set.add(x);
}

System.out.println(set);

Conceptually:

[10, 20, 30]

### Order guaranteed nahi hai.


## 1️⃣7️⃣ HashSet + String


Unique characters find karne ke liye:

String s = "banana";

HashSet<Character> set = new HashSet<>();

for(char ch : s.toCharArray()) {
    set.add(ch);
}

System.out.println(set);

Unique characters:

b
a
n

## 1️⃣8️⃣ HashMap ki Time Complexity


Average case:

| Operation | Time |
| --- | --- |
| put() | O(1) |
| get() | O(1) |
| containsKey() | O(1) |
| remove() | O(1) |
| size() | O(1) |


HashSet:

| Operation | Time |
| --- | --- |
| add() | O(1) average |
| contains() | O(1) average |
| remove() | O(1) average |


⚠️ Ye average-case complexity hai.

### 🧠 FINAL HASHING REVISION 🔥

HashMap
HashMap<Integer, String> map = new HashMap<>();
Add / Update
map.put(key, value);
Get
map.get(key);
Check key
map.containsKey(key);
Check value
map.containsValue(value);
Remove
map.remove(key);
Size
map.size();
Empty
map.isEmpty();
Clear
map.clear();
Traversal
Keys
for(int key : map.keySet())
Values
for(String value : map.values())
Both
for(Map.Entry<Integer, String> entry : map.entrySet()) {
    entry.getKey();
    entry.getValue();
}
Important DSA Functions
Default value
map.getOrDefault(key, 0);
Only if absent
map.putIfAbsent(key, value);
Update existing
map.replace(key, value);

### ⭐ Most Important HashMap Patterns

Frequency
HashMap<Integer, Integer> freq = new HashMap<>();

for(int x : arr) {
    freq.put(x, freq.getOrDefault(x, 0) + 1);
}
Character Frequency
HashMap<Character, Integer> freq = new HashMap<>();

for(char ch : s.toCharArray()) {
    freq.put(ch, freq.getOrDefault(ch, 0) + 1);
}

### First occurrence

map.putIfAbsent(x, i);
Two Sum
int needed = target - x;

if(map.containsKey(needed)) {
    // found
}

map.put(x, i);

### ⭐ HashSet Toolkit

HashSet<Integer> set = new HashSet<>();
Add
set.add(x);
Check
set.contains(x);
Remove
set.remove(x);
Size
set.size();
Empty
set.isEmpty();
Clear
set.clear();

### 🆚 Final C++ → Java Mapping

C++                         Java
------------------------------------------------
unordered_map<K,V>      →   HashMap<K,V>
unordered_set<T>        →   HashSet<T>

mp[key] = value         →   map.put(key,value)
mp[key]                 →   map.get(key)
mp.find(key)            →   map.containsKey(key)
mp.erase(key)           →   map.remove(key)

st.insert(x)            →   set.add(x)
st.find(x)              →   set.contains(x)
st.erase(x)             →   set.remove(x)
🎯 Golden Rule — Bas Ye Yaad Rakhna
                    HASHING
                       │
             ┌─────────┴─────────┐
             ↓                   ↓
         HashMap              HashSet
       key → value          unique values
             │                   │
      information chahiye?    sirf presence?
             │                   │
        YES → HashMap        YES → HashSet
Example:

"10 kitni baar aaya?"

→ HashMap

"10 present hai?"

→ HashSet

"10 ke saath index/value bhi store karni hai?"

→ HashMap

✅ HASHMAP + HASHSET COMPLETE

Ab hum ArrayList ke questions directly start nahi karenge. Pehle HashMap + HashSet ke super-basic questions karenge, taaki jo toolkit padha hai woh pakka ho jaye.

Phir gradually:

Hashing → ArrayList + Hashing → Strings + Hashing → Two Pointer/Sliding Window → LC questions 🔥