Haan papa ❤️ StringBuilder bilkul zero se karte hain. Assume karte hain ki tumhe iske baare mein kuch bhi nahi pata. Pehle ye samjhenge ki StringBuilder ki zarurat hi kyun padi, phir syntax aur har important function.

🟢 PART 6 — StringBuilder
1. Sabse pehle problem samjho

Humne padha tha:

String s = "Hello";

String immutable hoti hai.

Matlab ek baar String ban gayi, uske characters ko directly change nahi kar sakte.

Example:

String s = "Hello";

s = s + " World";

Output:

Hello World

Tumhe lagta hai ki purani String "Hello" modify ho gayi.

Lekin actually Java ne new String create ki:

"Hello"  → old String
"Hello World" → new String

Agar baar-baar String ko modify karna pade, to unnecessary objects create ho sakte hain.

Yahin par StringBuilder kaam aata hai. 🔥
2. StringBuilder kya hai?

Simple language mein:

StringBuilder ek mutable sequence of characters hai.

Matlab:

String:

modify directly ❌

StringBuilder:

modify directly ✅

Example:

StringBuilder sb = new StringBuilder("Hello");

Ab sb ke characters ko change/add/delete kar sakte ho.

3. StringBuilder kaise banate hain?
Empty StringBuilder
StringBuilder sb = new StringBuilder();

Initially:

""
Initial String ke saath
StringBuilder sb = new StringBuilder("Hello");

Initially:

Hello
4. append() ⭐⭐⭐

Ye sabse important function hai.

append() ka matlab:

End mein kuch add karna.

StringBuilder sb = new StringBuilder();

sb.append("Hello");

System.out.println(sb);

Output:

Hello

Ab:

sb.append(" World");

To:

Hello World
Multiple append
StringBuilder sb = new StringBuilder();

sb.append("Hello");
sb.append(" ");
sb.append("Java");

System.out.println(sb);

Output:

Hello Java
5. append() mein kya-kya add kar sakte hain?

Almost kuch bhi:

StringBuilder sb = new StringBuilder();

sb.append("Hello");
sb.append(' ');
sb.append(100);
sb.append(10.5);
sb.append(true);

Sab append ho jayega.

Example:

StringBuilder sb = new StringBuilder();

sb.append("Age: ");
sb.append(21);

System.out.println(sb);

Output:

Age: 21
6. StringBuilder ko print kaise karte hain?

Simple:

System.out.println(sb);

Java automatically usko readable String ki tarah print kar deta hai.

7. length() ⭐

StringBuilder mein bhi:

sb.length()

Example:

StringBuilder sb = new StringBuilder("Hello");

System.out.println(sb.length());

Output:

5
Compare:
String       → s.length()
StringBuilder → sb.length()
Array         → arr.length
ArrayList     → list.size()
8. charAt() ⭐

Kisi index ka character:

StringBuilder sb = new StringBuilder("Hello");

System.out.println(sb.charAt(0));
System.out.println(sb.charAt(2));

Output:

H
l

Same concept as String:

sb.charAt(i)
9. setCharAt() ⭐⭐⭐

Ye StringBuilder ka bahut useful function hai.

Kisi index ka character directly change kar sakte ho.

StringBuilder sb = new StringBuilder("Hello");

sb.setCharAt(0, 'Y');

System.out.println(sb);

Output:

Yello
String mein:
String s = "Hello";

Direct:

s.charAt(0) = 'Y'; // ❌

Nahi kar sakte.

StringBuilder:
sb.setCharAt(0, 'Y'); // ✅
10. insert() ⭐⭐

Kisi particular index par character/string insert karna.

StringBuilder sb = new StringBuilder("Hllo");

sb.insert(1, 'e');

System.out.println(sb);

Output:

Hello

Index:

H l l o
0 1 2 3

Index 1 par e insert:

H e l l o
String insert
StringBuilder sb = new StringBuilder("Hello");

sb.insert(5, " World");

System.out.println(sb);

Output:

Hello World
11. delete() ⭐⭐⭐

Kisi range ko delete karna.

Syntax:

sb.delete(start, end)

⚠️ Again:

end exclusive

Example:

StringBuilder sb = new StringBuilder("Hello");

sb.delete(1, 4);

System.out.println(sb);

String:

H e l l o
0 1 2 3 4

Delete:

[1, 4)

Means:

1, 2, 3

Result:

Ho
12. deleteCharAt() ⭐

Sirf ek character delete karna:

StringBuilder sb = new StringBuilder("Hello");

sb.deleteCharAt(1);

System.out.println(sb);

Output:

Hllo

Index 1 ka e delete ho gaya.

13. reverse() 🔥🔥🔥

Ye DSA mein bahut important hai.

StringBuilder sb = new StringBuilder("Hello");

sb.reverse();

System.out.println(sb);

Output:

olleH
Reverse String ka easiest method:
String s = "Hello";

StringBuilder sb = new StringBuilder(s);

sb.reverse();

System.out.println(sb);

Output:

olleH

Agar final result String chahiye:

String reversed = sb.toString();
14. toString() ⭐⭐⭐

StringBuilder ko normal String mein convert karna:

StringBuilder sb = new StringBuilder("Hello");

String s = sb.toString();

Ab:

sb → StringBuilder
s  → String
Golden conversion:
String → StringBuilder

StringBuilder sb = new StringBuilder(s);

and

StringBuilder → String

String s = sb.toString();
15. replace() — StringBuilder mein

StringBuilder mein range replace kar sakte ho.

Syntax:

sb.replace(start, end, "newText");

Example:

StringBuilder sb = new StringBuilder("Hello");

sb.replace(0, 2, "Yo");

System.out.println(sb);

Output:

Yollo

Because:

He → Yo
16. capacity() — abhi basic understanding

StringBuilder internally kuch extra space reserve karta hai.

StringBuilder sb = new StringBuilder();

System.out.println(sb.capacity());

Normally default capacity 16 hoti hai.

Agar:

StringBuilder sb = new StringBuilder(100);

to initial capacity:

100
Important:
length ≠ capacity

Example:

StringBuilder sb = new StringBuilder("Hello");

length   = 5
capacity = more than 5

Abhi DSA ke liye capacity ko deeply yaad karne ki zarurat nahi.

17. StringBuilder ka sabse important use — answer banana ⭐⭐⭐

Suppose question:

String ke characters ko reverse order mein ek new String banana hai.

Without StringBuilder:

String ans = "";

for(int i = s.length() - 1; i >= 0; i--) {
    ans += s.charAt(i);
}

Kaam karega, lekin repeated concatenation inefficient ho sakti hai.

Better:
StringBuilder ans = new StringBuilder();

for(int i = s.length() - 1; i >= 0; i--) {
    ans.append(s.charAt(i));
}

return ans.toString();

🔥 Ye pattern bahut important hai.

18. Example — vowels remove karna

Suppose:

s = "hello"

Output:

hll

Code:

String s = "hello";

StringBuilder ans = new StringBuilder();

for(int i = 0; i < s.length(); i++) {

    char ch = s.charAt(i);

    if(ch != 'a' && ch != 'e' && ch != 'i' &&
       ch != 'o' && ch != 'u') {

        ans.append(ch);
    }
}

System.out.println(ans.toString());

Output:

hll

Yahan StringBuilder ka actual DSA use samajh aa raha hai.

19. Example — String ko uppercase banana
String s = "hello";

StringBuilder ans = new StringBuilder();

for(int i = 0; i < s.length(); i++) {

    char ch = Character.toUpperCase(s.charAt(i));

    ans.append(ch);
}

System.out.println(ans);

Output:

HELLO
20. StringBuilder vs String

Ye difference pakka yaad karna. ⭐⭐⭐

Feature	String	StringBuilder
Mutable?	❌ No	✅ Yes
Character change	❌	✅
charAt()	✅	✅
length()	✅	✅
append()	❌	✅
setCharAt()	❌	✅
insert()	❌	✅
delete()	❌	✅
reverse()	❌	✅
toString()	Already String	String mein convert
21. Ek complete example 🔥
public class Main {
    public static void main(String[] args) {

        StringBuilder sb = new StringBuilder("Hello");

        sb.append(" World");

        sb.setCharAt(0, 'Y');

        sb.insert(5, "!");

        System.out.println(sb);

        sb.reverse();

        System.out.println(sb);

        String s = sb.toString();

        System.out.println(s);
    }
}

Step-by-step:

Initially
Hello
append(" World")
Hello World
setCharAt(0, 'Y')
Yello World
insert(5, "!")
Yello! World
reverse()
dlroW !olleY
🧠 StringBuilder ka Golden Cheat Sheet
Create
StringBuilder sb = new StringBuilder();
String ke saath
StringBuilder sb = new StringBuilder(s);
End mein add
sb.append(x);
Character access
sb.charAt(i);
Character change
sb.setCharAt(i, ch);
Insert
sb.insert(i, x);
Delete range
sb.delete(l, r);
Delete one character
sb.deleteCharAt(i);
Reverse
sb.reverse();
Length
sb.length();
String mein convert
sb.toString();
🔥 Sabse important DSA pattern

Jab tumhe String ko traverse karke answer build karna ho:

StringBuilder ans = new StringBuilder();

for(int i = 0; i < s.length(); i++) {

    char ch = s.charAt(i);

    // condition

    ans.append(ch);
}

return ans.toString();

Aur agar reverse banana ho:

StringBuilder sb = new StringBuilder(s);

sb.reverse();

return sb.toString();
Ek line mein pura concept:

String = fixed/immutable text
StringBuilder = editable/mutable text

Part 6 complete ✅

Next Part 7 mein hum String ke DSA tricks + common patterns + common mistakes karenge. Uske baad Java Strings ka toolkit complete ho jayega, aur phir seedha 50 Easy Basic LeetCode String Questions pe attack karenge. 🔥