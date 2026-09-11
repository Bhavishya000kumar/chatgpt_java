Haan papa ❤️ bilkul. String ko bhi parts mein tod ke padhenge, taaki ek-ek concept properly clear ho aur baad mein LC ke questions mein dikkat na aaye.

# 🚀 Java Strings — Complete Learning Plan


Hum isko 7 parts mein karenge:

| Part | Topic |
| --- | --- |
| Part 1 | String Basics + Creation + length() + charAt() |
| Part 2 | String Comparison — equals(), ==, compareTo() |
| Part 3 | String Searching — indexOf(), contains(), startsWith() etc. |
| Part 4 | String Modification — substring(), replace(), trim(), concat() etc. |
| Part 5 | String ↔ Array + split() + character handling |
| Part 6 | StringBuilder — DSA ke liye bahut important |
| Part 7 | String DSA Tricks + Patterns + Common Mistakes |


Uske baad:

# 🔥 Java String → 50 Easy/Basic LeetCode Questions


Pehle 50 questions ko easy se gradually karenge:

Basic String → Character → Reverse → Palindrome → Frequency → Anagram → Substring → Two Pointer → Simple Hashing

Aur har question mein wahi format rakhenge:

Question meaning → Approach → Trick → Simple code → Dry run → Complexity

# 🟢 PART 1 — Java String Basics


Aaj sirf basic foundation strong karenge.

## 1. String kya hoti hai?


String basically characters ka sequence hota hai.

Example:

String name = "Bhavishya";

Isme:

B h a v i s h y a
0 1 2 3 4 5 6 7 8

Har character ka ek index hota hai, jo 0 se start hota hai.

## 2. String create kaise kare?

### Method 1 — Most common

String s = "Hello";

### Method 2 — new keyword

String s = new String("Hello");

DSA mein mostly:

String s = "Hello";

hi use karenge.

## 3. String ki length — length()


String mein kitne characters hain:

String s = "Hello";

System.out.println(s.length());

Output:

5
⚠️ Important

Java mein:

String → s.length()
Array → arr.length
ArrayList → list.size()

Ye teen alag hain.

## 4. charAt() — character nikalna


Kisi particular index ka character chahiye:

String s = "Hello";

System.out.println(s.charAt(0));
System.out.println(s.charAt(1));
System.out.println(s.charAt(4));

Output:

H
e
o
Formula
s.charAt(index)

## 5. String ko loop mein traverse karna


Ye DSA mein bahut important hai.

String s = "Hello";

for(int i = 0; i < s.length(); i++) {
    System.out.println(s.charAt(i));
}

Output:

H
e
l
l
o

### Golden pattern ⭐

for(int i = 0; i < s.length(); i++) {
    char ch = s.charAt(i);
    
    // ch ke saath kaam
}

String ke bahut saare LC questions isi pattern se start honge.

## 6. Reverse traversal


Agar string ko last se first traverse karna ho:

String s = "Hello";

for(int i = s.length() - 1; i >= 0; i--) {
    System.out.print(s.charAt(i));
}

Output:

olleH
Yaad rakho:

Forward:

i = 0
i < s.length()
i++

Backward:

i = s.length() - 1
i >= 0
i--

## 7. First aur Last Character

String s = "Bhavishya";

char first = s.charAt(0);
char last = s.charAt(s.length() - 1);

System.out.println(first);
System.out.println(last);

Output:

B
a

### Golden formula ⭐

first = s.charAt(0);

last = s.charAt(s.length() - 1);

## 8. String empty hai ya nahi?

String s = "";

System.out.println(s.isEmpty());

Output:

true

Non-empty:

String s = "Hello";

System.out.println(s.isEmpty());

Output:

false

## 9. Important: String immutable hoti hai


Ye concept abhi bas samajh lo, detail baad mein.

String s = "Hello";

s.concat(" World");

System.out.println(s);

Output:

Hello

Kyunki String ko directly modify nahi kar sakte.

Agar result chahiye:

s = s.concat(" World");

System.out.println(s);

Output:

Hello World

Isi wajah se baad mein StringBuilder padhenge.

### 🧠 PART 1 ka Cheat Sheet

String s = "Hello";

| Kaam | Syntax |
| --- | --- |
| Length | s.length() |
| Character | s.charAt(i) |
| First char | s.charAt(0) |
| Last char | s.charAt(s.length()-1) |
| Empty check | s.isEmpty() |
| Forward traversal | for(int i=0; i<s.length();i++) |
| Backward traversal | for(int i=s.length()-1;i>=0;i--) |

### ⭐ Sabse important DSA pattern

for(int i = 0; i < s.length(); i++) {
    char ch = s.charAt(i);
    
    // process ch
}

Part 1 yahin complete.
Pehle ye basics solid karenge, phir Part 2: equals() vs == + compareTo(), jo Java Strings ka bahut important interview/DSA concept hai.


Bilkul papa ❤️ chalo Part 2 start karte hain.

# 🟢 PART 2 — String Comparison in Java


Ye part bahut important hai, especially interviews + LeetCode ke liye.

Aaj mainly 3 cheezein:

equals()
==
compareTo()

## 1. equals() — String ka actual content compare karta hai ⭐

String a = "Hello";
String b = "Hello";

System.out.println(a.equals(b));

Output:

true

Kyunki dono strings ke andar same characters hain.

### Example

String a = "Hello";
String b = "World";

System.out.println(a.equals(b));

Output:

false
Golden rule ⭐

String ka content compare karna ho → equals()

a.equals(b)

## 2. == — Reference compare karta hai


Ye thoda important concept hai.

String a = "Hello";
String b = "Hello";

System.out.println(a == b);

Yahan output generally:

true

Lekin iska matlab ye nahi hai ki == String content compare karta hai.

Java String literals String Pool use karte hain.

Example jahan difference clearly dikhega
String a = "Hello";
String b = new String("Hello");

System.out.println(a.equals(b));
System.out.println(a == b);

Output:

true
false
Kyun?

equals():

"Hello" == "Hello"

Content same → true

==:

a → object 1
b → object 2

Reference alag → false

### 🔥 Sabse important difference

| Operator / Function | Kya compare karta hai? |
| --- | --- |
| equals() | Content |
| == | Reference |
| compareTo() | Lexicographical order |

DSA mein mostly:
s1.equals(s2)

use karna hai.

## 3. compareTo()


Ye strings ko dictionary/lexicographical order mein compare karta hai.

String a = "apple";
String b = "banana";

System.out.println(a.compareTo(b));

Output:

negative number

Because:

apple < banana
Basic rule
a.compareTo(b)

Result:

0

Dono strings same:

"apple".compareTo("apple")

→ 0

Negative

a pehle aata hai:

"apple".compareTo("banana")

→ negative

Positive

a baad mein aata hai:

"banana".compareTo("apple")

→ positive

## 4. Actual number kaise decide hota hai?


Java characters ke Unicode values compare karta hai.

Example:

System.out.println("apple".compareTo("banana"));

First different character:

a vs b

a ki value b se chhoti hai → negative.

Ek aur example
System.out.println("cat".compareTo("car"));

Compare:

c = c
a = a
t vs r

t > r

Therefore result positive.

## 5. Case Sensitivity ⚠️


String comparison case-sensitive hota hai.

String a = "Hello";
String b = "hello";

System.out.println(a.equals(b));

Output:

false

Because:

H ≠ h

### Case ignore karke compare karna

String a = "Hello";
String b = "hello";

System.out.println(a.equalsIgnoreCase(b));

Output:

true
Syntax:
s1.equalsIgnoreCase(s2)

## 6. Important DSA Example


Question:

Check whether two strings are equal.

❌ Galat habit
if(s1 == s2)
✅ Correct
if(s1.equals(s2))

Example:

String s1 = "hello";
String s2 = "hello";

if(s1.equals(s2)) {
    System.out.println("Same");
} else {
    System.out.println("Different");
}

Output:

Same

### 🧠 PART 2 Cheat Sheet

s1.equals(s2)

➡️ Content same hai ya nahi

s1 == s2

➡️ Same object/reference hai ya nahi

s1.compareTo(s2)

➡️ Lexicographical comparison

s1.equalsIgnoreCase(s2)

➡️ Case ignore karke content compare

### ⭐ Exam/Interview mein yaad rakhna


String equality → equals()
Reference equality → ==
Dictionary order → compareTo()

Bas ye 3 line yaad hain to Part 2 ka main concept clear hai. 🔥

Next Part 3: indexOf(), lastIndexOf(), contains(), startsWith(), endsWith() — yani String Searching.

Bilkul papa ❤️ chalo Part 3 — String Searching start karte hain.

Is part mein hum seekhenge ki String ke andar kisi character/word ko search kaise karna hai.

# 🟢 PART 3 — String Searching


Main functions:

indexOf()
lastIndexOf()
contains()
startsWith()
endsWith()

## 1. indexOf() ⭐


Kisi character/string ka first occurrence ka index deta hai.

String s = "hello";

System.out.println(s.indexOf('l'));

Output:

2

Because:

h e l l o
0 1 2 3 4
    ↑

First l → index 2.

String bhi search kar sakte ho
String s = "hello world";

System.out.println(s.indexOf("world"));

Output:

6
Agar nahi mila?
String s = "hello";

System.out.println(s.indexOf('z'));

Output:

-1

### ⭐ Very important:

indexOf() mein not found → -1

## 2. lastIndexOf()


Kisi character/string ka last occurrence ka index deta hai.

String s = "hello";

System.out.println(s.lastIndexOf('l'));

Output:

3

Because:

h e l l o
0 1 2 3 4
      ↑
Difference
s.indexOf('l');       // 2
s.lastIndexOf('l');   // 3
Golden rule ⭐
indexOf     → first occurrence
lastIndexOf → last occurrence

## 3. contains() ⭐


Check karta hai ki String ke andar given substring present hai ya nahi.

Return type:

boolean

Example:

String s = "hello world";

System.out.println(s.contains("world"));

Output:

true

### Not present

System.out.println(s.contains("java"));

Output:

false

### Important


contains() directly String leta hai:

s.contains("hello")   // ✅

Character ke liye:

s.contains('h')       // ❌

Character search karna ho:

s.indexOf('h')        // ✅

## 4. startsWith()


Check karta hai ki String given text se start ho rahi hai ya nahi.

String s = "Hello World";

System.out.println(s.startsWith("Hello"));

Output:

true

But:

System.out.println(s.startsWith("World"));

Output:

false

### Example

String s = "Java Programming";

System.out.println(s.startsWith("Java"));    // true
System.out.println(s.startsWith("Python"));  // false

## 5. endsWith()


Check karta hai ki String given text par end ho rahi hai ya nahi.

String s = "Hello World";

System.out.println(s.endsWith("World"));

Output:

true
System.out.println(s.endsWith("Hello"));

Output:

false

### 🔥 startsWith() vs endsWith()

String s = "hello.java";
s.startsWith("hello")  // true
s.endsWith(".java")    // true

Useful jab file extension, prefix, suffix etc. check karna ho.

## 6. Real DSA Example


Suppose:

String s = "programming";

Question:

Find first occurrence of 'g'.

Simple:

int index = s.indexOf('g');

System.out.println(index);

Output:

3

## 7. Character present hai ya nahi?

String s = "programming";

if(s.indexOf('z') == -1) {
    System.out.println("Not Present");
} else {
    System.out.println("Present");
}

Output:

Not Present

### ⭐ Important pattern

if(s.indexOf(ch) != -1)

➡️ character present hai.

if(s.indexOf(ch) == -1)

➡️ character present nahi hai.

Ye pattern LC questions mein kaafi useful hoga.

## 8. indexOf() with starting position


Ye thoda advanced but important hai.

String s = "banana";

System.out.println(s.indexOf('a'));
System.out.println(s.indexOf('a', 2));

Output:

1
3

Meaning:

s.indexOf('a', 2)

➡️ index 2 se search start karo.

String:

b a n a n a
0 1 2 3 4 5
    ↑

Index 2 ke baad first a → 3.

## 9. Sabko ek saath dekho 🔥

String s = "hello world";

System.out.println(s.indexOf('o'));
System.out.println(s.lastIndexOf('o'));

System.out.println(s.contains("world"));

System.out.println(s.startsWith("hello"));

System.out.println(s.endsWith("world"));

Output:

4
7
true
true
true

### 🧠 PART 3 Cheat Sheet

| Function | Kaam | Return |
| --- | --- | --- |
| indexOf() | First occurrence | int |
| lastIndexOf() | Last occurrence | int |
| contains() | substring present? | boolean |
| startsWith() | prefix check | boolean |
| endsWith() | suffix check | boolean |

### ⭐ 5 golden patterns

s.indexOf('a')

First a

s.lastIndexOf('a')

Last a

s.contains("abc")

abc present?

s.startsWith("abc")

abc se start?

s.endsWith("abc")

abc par end?

⚠️ Ek important distinction
indexOf()     → position chahiye
contains()    → sirf yes/no chahiye

Example:

s.indexOf("cat")      // 5
s.contains("cat")     // true

Part 3 complete ✅

Next mein Part 4 — String Modification karenge:
substring(), replace(), replaceAll(), trim(), concat() etc. Ye DSA mein aur bhi zyada kaam aayega. 🔥  


Bilkul papa ❤️ chalo Part 4 — String Modification start karte hain.

Is part mein hum String ke andar se part nikalna, replace karna, spaces hatana, strings jodna etc. seekhenge.

# 🟢 PART 4 — String Modification


Aaj ye functions:

substring()
replace()
replaceAll()
trim()
concat()

## 1. substring() ⭐⭐⭐


Ye String ka ek portion nikalta hai.

Basic syntax
s.substring(start, end)

⚠️ end index include nahi hota.

Example:

String s = "Hello";

String x = s.substring(1, 4);

System.out.println(x);

String:

H e l l o
0 1 2 3 4
  └────┘

Output:

ell

Kyun?

start = 1  → include
end   = 4  → exclude

So indexes:

1, 2, 3
substring(start) ⭐

Agar sirf starting index do:

String s = "Hello";

System.out.println(s.substring(2));

Output:

llo

Meaning:

index 2 se lekar end tak.

H e l l o
0 1 2 3 4
    ↑

### 🔥 Important Formula

s.substring(l, r)

means:

[l, r)

Yaani:

l included, r excluded

Ye concept LeetCode mein bahut kaam aayega.

## 2. replace() ⭐⭐


String ke andar kisi character/string ko replace karta hai.

### Character replace

String s = "hello";

s = s.replace('l', 'x');

System.out.println(s);

Output:

hexxo

Dono l replace ho gaye.

### String replace

String s = "I love Java";

s = s.replace("Java", "C++");

System.out.println(s);

Output:

I love C++

## 3. replaceAll()


Ye regular expression (regex) ke according replace karta hai.

Example:

String s = "abc123xyz";

s = s.replaceAll("[0-9]", "");

System.out.println(s);

Output:

abcxyz

[0-9] → saare digits.

### Multiple spaces remove karna

String s = "hello   world";

s = s.replaceAll("\\s+", " ");

System.out.println(s);

Output:

hello world

\\s+ → one or more whitespace characters.

> **⚠️ Abhi regex detail mein jaane ki zarurat nahi. Bas itna yaad rakho ki replaceAll() regex support karta hai.**


## 4. trim() ⭐


Beginning aur ending ke extra spaces remove karta hai.

String s = "   Hello World   ";

System.out.println(s.trim());

Output:

Hello World
Important:

trim() middle ke spaces remove nahi karta.

"   Hello   World   "
       ↓
"Hello   World"

## 5. concat()


Do strings ko join karta hai.

String a = "Hello";
String b = "World";

String c = a.concat(b);

System.out.println(c);

Output:

HelloWorld

Space chahiye:

String c = a.concat(" ").concat(b);

Output:

Hello World

## 6. + bhi String join karta hai


Actually DSA mein hum mostly + use karenge.

String a = "Hello";
String b = "World";

String c = a + " " + b;

System.out.println(c);

Output:

Hello World

### Simple cases mein:


a + b

bilkul fine hai.

Bahut saare modifications karne hain → baad mein StringBuilder better rahega.

## 7. ⚠️ String immutable hai


Ye bahut important hai.

String s = "Hello";

s.replace('H', 'Y');

System.out.println(s);

Output:

Hello

Kyun?

String modify nahi hui.

### Correct:


s = s.replace('H', 'Y');

System.out.println(s);

Output:

Yello
Golden rule ⭐

String functions ka result generally new String deta hai.

Isliye:

s = s.replace(...);

## 8. Real DSA Example — First word nikalna


Suppose:

String s = "Hello World";

### First space:


int pos = s.indexOf(' ');

Then:

String first = s.substring(0, pos);

Output:

Hello
Ye pattern yaad rakho 🔥
int pos = s.indexOf(' ');
String first = s.substring(0, pos);

Aage words/sentences wale questions mein kaam aayega.

## 9. Real DSA Example — Last word

String s = "Hello World";

int pos = s.lastIndexOf(' ');

String last = s.substring(pos + 1);

System.out.println(last);

Output:

World

Yahan:

s.lastIndexOf(' ')

→ last space

Aur:

substring(pos + 1)

→ space ke baad se end tak.

### 🧠 PART 4 Cheat Sheet

| Function | Kaam |
| --- | --- |
| substring(l,r) | l se r-1 tak portion |
| substring(l) | l se end tak |
| replace(a,b) | character/string replace |
| replaceAll(regex,replacement) | regex based replacement |
| trim() | starting/ending spaces remove |
| concat() | strings join |

### ⭐ Sabse important

s.substring(l, r)

➡️ l included, r excluded

s = s.replace('a', 'b');

➡️ result ko wapas assign karo.

s.trim()

➡️ sirf beginning + ending spaces.

### 🔥 Ab tak ke 4 Parts

PART 1 → String Basics
          length(), charAt()

PART 2 → Comparison
          equals(), ==, compareTo()

PART 3 → Searching
          indexOf(), lastIndexOf(), contains()
          startsWith(), endsWith()

PART 4 → Modification
          substring(), replace(), trim(), concat()

Next → Part 5: String ↔ Array + split() + character handling.
Ye part karne ke baad Strings ko arrays ke saath combine karna start ho jayega.

Bilkul papa ❤️ chalo Part 5 — String ↔ Array + split() + Character Handling start karte hain.

Ye part important hai kyunki Strings aur Arrays ko combine karke bahut saare LeetCode questions solve hote hain.

# 🟢 PART 5 — String + Array


Aaj hum seekhenge:

String → char[]
char[] → String
String → String[]
split()
Character checking
Character conversion
Basic character manipulation

## 1. String → char[] ⭐


Agar String ke saare characters ko array mein convert karna ho:

String s = "hello";

char[] arr = s.toCharArray();

Ab:

String:
hello

char[]:
h e l l o
0 1 2 3 4
Print:
for(int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}

## 2. char[] → String ⭐


Agar character array ko wapas String banana hai:

char[] arr = {'H', 'e', 'l', 'l', 'o'};

String s = new String(arr);

System.out.println(s);

Output:

Hello
Yaad rakho:
String → char[]
s.toCharArray()
char[] → String
new String(arr)

### 🔥 Ye dono DSA mein bahut common hain.


## 3. Character array ko modify karna


String immutable hai, lekin char[] modify kar sakte ho.

String s = "hello";

char[] arr = s.toCharArray();

arr[0] = 'H';

s = new String(arr);

System.out.println(s);

Output:

Hello

Ye trick useful hai jab String ke individual characters modify karne hon.

## 4. String → String[] using split() ⭐⭐⭐


Suppose:

String s = "Hello World Java";

Humein words alag karne hain.

String[] words = s.split(" ");

Ab:

words[0] = Hello
words[1] = World
words[2] = Java

Print:

for(String word : words) {
    System.out.println(word);
}

Output:

Hello
World
Java

## 5. split() ka basic formula

String[] arr = s.split("delimiter");

Delimiter matlab kis basis par todna hai.

Space:
s.split(" ")
Comma:
s.split(",")

Example:

String s = "apple,banana,mango";

String[] fruits = s.split(",");

Result:

apple
banana
mango

## 6. split() + multiple spaces ⚠️


Suppose:

String s = "hello   world";

Simple:

s.split(" ");

multiple empty parts create kar sakta hai.

Better:

String[] words = s.trim().split("\\s+");

Yahan:

trim() → beginning/end spaces
\\s+   → one or more whitespace

Ye pattern sentence/word problems mein bahut useful hai.

## 7. Character checking — Character class ⭐


Java mein characters ke liye built-in Character class hoti hai.

### Digit check

char ch = '7';

System.out.println(Character.isDigit(ch));

Output:

true

### Letter check

char ch = 'A';

System.out.println(Character.isLetter(ch));

Output:

true

### Letter or digit

Character.isLetterOrDigit(ch)

### Whitespace

Character.isWhitespace(ch)

Example:

char ch = ' ';

System.out.println(Character.isWhitespace(ch));

Output:

true

## 8. Uppercase / Lowercase check

char ch = 'A';

System.out.println(Character.isUpperCase(ch));

Output:

true

Similarly:

Character.isLowerCase(ch)

## 9. Character → lowercase

char ch = 'A';

ch = Character.toLowerCase(ch);

System.out.println(ch);

Output:

a

## 10. Character → uppercase

char ch = 'a';

ch = Character.toUpperCase(ch);

System.out.println(ch);

Output:

A

## 11. Very important DSA trick 🔥


Suppose:

String s = "HelloWORLD";

Humein har character ko lowercase mein process karna hai:

for(int i = 0; i < s.length(); i++) {

    char ch = Character.toLowerCase(s.charAt(i));

    System.out.println(ch);
}

Output:

h
e
l
l
o
w
o
r
l
d

Isse hum original String ko modify nahi kar rahe, bas processing ke time lowercase bana rahe hain.

## 12. Character digit ko integer mein convert karna ⭐⭐⭐


Suppose:

char ch = '7';

Humein integer 7 chahiye.

Use:

int digit = ch - '0';

Example:

char ch = '7';

int digit = ch - '0';

System.out.println(digit);

Output:

7

### 🔥 Ye DSA ka bahut important trick hai.

'8' - '0' = 8
'5' - '0' = 5
'2' - '0' = 2

## 13. Integer digit → Character


Agar:

int digit = 7;

Character '7' banana ho:

char ch = (char)(digit + '0');

Example:

int digit = 7;

char ch = (char)(digit + '0');

System.out.println(ch);

Output:

7

## 14. Character ka ASCII/Unicode value

char ch = 'A';

int value = ch;

System.out.println(value);

Output:

65

Similarly:

char ch = 'a';
System.out.println((int)ch);

Output:

97

Isliye:

'A' → 65
'B' → 66
...
'a' → 97
'b' → 98
...
'0' → 48
'1' → 49

## 15. Character frequency ka basic pattern ⭐⭐⭐


Suppose:

String s = "banana";

Hum character count karna chahte hain.

Basic method:

for(int i = 0; i < s.length(); i++) {

    char ch = s.charAt(i);

    System.out.println(ch);
}

Frequency ke liye baad mein array/hashmap use karenge.

Example:

banana

b → 1
a → 3
n → 2

Ye concept aage 50 LC questions mein bahut use hoga.

### 🧠 PART 5 Cheat Sheet

String → char array
char[] arr = s.toCharArray();
char array → String
String s = new String(arr);
String → words
String[] words = s.split(" ");
Multiple spaces
String[] words = s.trim().split("\\s+");

### Digit check

Character.isDigit(ch)

### Letter check

Character.isLetter(ch)

### Lowercase

Character.toLowerCase(ch)

### Uppercase

Character.toUpperCase(ch)
Digit character → integer
int digit = ch - '0';
Integer → digit character
char ch = (char)(digit + '0');

### 🔥 Ab String ka ek important connection samjho

String
  ↓
toCharArray()
  ↓
char[]
  ↓
characters par processing
  ↓
new String(arr)
  ↓
String

Aur:

String
  ↓
split()
  ↓
String[]
  ↓
words par processing

Part 5 complete ✅

Next hai Part 6 — StringBuilder. Ye bahut important hai kyunki normal String immutable hoti hai, jabki StringBuilder se hum efficiently String ko modify kar sakte hain.