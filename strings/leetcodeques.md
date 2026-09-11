Ab sirf STRINGS ke questions honge. No Arrays-only, no Stack, no random topics.

# 🟢 Level 1 — Super Easy / Ekdum Basic


20 Questions

709. To Lower Case
344. Reverse String
125. Valid Palindrome
771. Jewels and Stones
1108. Defanging an IP Address
58. Length of Last Word
1678. Goal Parser Interpretation
1528. Shuffle String
1768. Merge Strings Alternately
1816. Truncate Sentence
1859. Sorting the Sentence
2129. Capitalize the Title
1662. Check If Two String Arrays are Equivalent
28. Find the Index of the First Occurrence in a String
14. Longest Common Prefix
557. Reverse Words in a String III
541. Reverse String II
1021. Remove Outermost Parentheses
1614. Maximum Nesting Depth of the Parentheses
1704. Determine if String Halves Are Alike

# 🟡 Level 2 — Easy


15 Questions

242. Valid Anagram
387. First Unique Character in a String
383. Ransom Note
205. Isomorphic Strings
290. Word Pattern
520. Detect Capital
657. Robot Return to Origin
804. Unique Morse Code Words
929. Unique Email Addresses
1071. Greatest Common Divisor of Strings
459. Repeated Substring Pattern
392. Is Subsequence
1512. Number of Good Pairs
1663. Smallest String With A Given Numeric Value
1945. Sum of Digits of String After Convert

# 🔴 Level 3 — Medium


20 Questions — Kal karenge

3. Longest Substring Without Repeating Characters
49. Group Anagrams
438. Find All Anagrams in a String
567. Permutation in String
424. Longest Repeating Character Replacement
151. Reverse Words in a String
5. Longest Palindromic Substring
647. Palindromic Substrings
22. Generate Parentheses
394. Decode String
443. String Compression
791. Custom Sort String
12. Integer to Roman
13. Roman to Integer
43. Multiply Strings
71. Simplify Path
165. Compare Version Numbers
678. Valid Parenthesis String
763. Partition Labels
424. Longest Repeating Character Replacement ❌ duplicate

55 ko duplicate nahi rakhenge — practice mein iski jagah ek naya Medium String question lenge.

## 🎯 Abhi ka target


1–20 → ekdum basic Strings
21–35 → Easy Strings
36–55 → Medium Strings (kal)

Aur ab hum Question 1 se start karenge, ek-ek karke. Tum next bologe tabhi next question. ❤️

## 709. To Lower Case

Solved
Easy
Topics
premium lock icon
Companies
Hint
Given a string s, return the string after replacing every uppercase letter with the same lowercase letter.

 

**Example 1:**


Input: s = "Hello"
Output: "hello"

**Example 2:**


Input: s = "here"
Output: "here"

**Example 3:**


Input: s = "LOVELY"
Output: "lovely"

```java
class Solution {
    public String toLowerCase(String s) {

        StringBuilder ans = new StringBuilder();

        for(int i = 0; i < s.length(); i++) {

            char ch = s.charAt(i);

            ans.append(Character.toLowerCase(ch));
        }

        return ans.toString();
    }
}

344. Reverse String
Solved
Easy
Topics
premium lock icon
Companies
Hint
Write a function that reverses a string. The input string is given as an array of characters s.

You must do this by modifying the input array in-place with O(1) extra memory.

 

Example 1:

Input: s = ["h","e","l","l","o"]
Output: ["o","l","l","e","h"]
Example 2:

Input: s = ["H","a","n","n","a","h"]
Output: ["h","a","n","n","a","H"]
 
 class Solution {
    public void reverseString(char[] s) {

        int left = 0;
        int right = s.length - 1;

        while(left < right) {

            char temp = s[left];
            s[left] = s[right];
            s[right] = temp;

            left++;
            right--;
        }
    }
}

125. Valid Palindrome
Solved
Easy
Topics
premium lock icon
Companies
A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string s, return true if it is a palindrome, or false otherwise.

 

Example 1:

Input: s = "A man, a plan, a canal: Panama"
Output: true
Explanation: "amanaplanacanalpanama" is a palindrome.
Example 2:

Input: s = "race a car"
Output: false
Explanation: "raceacar" is not a palindrome.
Example 3:

Input: s = " "
Output: true
Explanation: s is an empty string "" after removing non-alphanumeric characters.
Since an empty string reads the same forward and backward, it is a palindrome.

class Solution {
    public boolean isPalindrome(String s) {

        int left = 0;
        int right = s.length() - 1;

        while(left < right) {

            while(left < right && !Character.isLetterOrDigit(s.charAt(left))) {
                left++;
            }

            while(left < right && !Character.isLetterOrDigit(s.charAt(right))) {
                right--;
            }

            char l = Character.toLowerCase(s.charAt(left));
            char r = Character.toLowerCase(s.charAt(right));

            if(l != r) {
                return false;
            }

            left++;
            right--;
        }

        return true;
    }
}

771. Jewels and Stones
Solved
Easy
Topics
premium lock icon
Companies
Hint
You're given strings jewels representing the types of stones that are jewels, and stones representing the stones you have. Each character in stones is a type of stone you have. You want to know how many of the stones you have are also jewels.

Letters are case sensitive, so "a" is considered a different type of stone from "A".

 

Example 1:

Input: jewels = "aA", stones = "aAAbbbb"
Output: 3
Example 2:

Input: jewels = "z", stones = "ZZ"
Output: 0

class Solution {
    public int numJewelsInStones(String jewels, String stones) {

        int count = 0;

        for(int i = 0; i < stones.length(); i++) {

            char ch = stones.charAt(i);

            if(jewels.indexOf(ch) != -1) {
                count++;
            }
        }

        return count;
    }
}

1108. Defanging an IP Address
Solved
Easy
Topics
premium lock icon
Companies
Given a valid (IPv4) IP address, return a defanged version of that IP address.

A defanged IP address replaces every period "." with "[.]".

 

Example 1:

Input: address = "1.1.1.1"
Output: "1[.]1[.]1[.]1"
Example 2:

Input: address = "255.100.50.0"
Output: "255[.]100[.]50[.]0"

class Solution {
    public String defangIPaddr(String address) {
        return address.replace(".", "[.]");
    }
}

StringBuilder se bhi kar sakte hain

Abhi humne StringBuilder padha hai, to manually bhi:

class Solution {
    public String defangIPaddr(String address) {

        StringBuilder ans = new StringBuilder();

        for(int i = 0; i < address.length(); i++) {

            char ch = address.charAt(i);

            if(ch == '.') {
                ans.append("[.]");
            } else {
                ans.append(ch);
            }
        }

        return ans.toString();
    }
}

58. Length of Last Word
Solved
Easy
Topics
premium lock icon
Companies
Given a string s consisting of words and spaces, return the length of the last word in the string.

A word is a maximal substring consisting of non-space characters only.

 

Example 1:

Input: s = "Hello World"
Output: 5
Explanation: The last word is "World" with length 5.
Example 2:

Input: s = "   fly me   to   the moon  "
Output: 4
Explanation: The last word is "moon" with length 4.
Example 3:

Input: s = "luffy is still joyboy"
Output: 6
Explanation: The last word is "joyboy" with length 6.

class Solution {
    public int lengthOfLastWord(String s) {

        int i = s.length() - 1;

        // Ending spaces skip karo
        while(i >= 0 && s.charAt(i) == ' ') {
            i--;
        }

        int count = 0;

        // Last word count karo
        while(i >= 0 && s.charAt(i) != ' ') {
            count++;
            i--;
        }

        return count;
    }
}

trim() se bhi kar sakte hain

Ek aur simple approach:

class Solution {
    public int lengthOfLastWord(String s) {

        s = s.trim();

        int i = s.length() - 1;
        int count = 0;

        while(i >= 0 && s.charAt(i) != ' ') {
            count++;
            i--;
        }

        return count;
    }
}

Ye bhi correct hai.

Lekin pehla solution extra String banane se bachata hai, isliye DSA perspective se better hai.

1678. Goal Parser Interpretation
Solved
Easy
Topics
premium lock icon
Companies
Hint
You own a Goal Parser that can interpret a string command. The command consists of an alphabet of "G", "()" and/or "(al)" in some order. The Goal Parser will interpret "G" as the string "G", "()" as the string "o", and "(al)" as the string "al". The interpreted strings are then concatenated in the original order.

Given the string command, return the Goal Parser's interpretation of command.

 

Example 1:

Input: command = "G()(al)"
Output: "Goal"
Explanation: The Goal Parser interprets the command as follows:
G -> G
() -> o
(al) -> al
The final concatenated result is "Goal".
Example 2:

Input: command = "G()()()()(al)"
Output: "Gooooal"
Example 3:

Input: command = "(al)G(al)()()G"
Output: "alGalooG"

class Solution {
    public String interpret(String command) {

        StringBuilder ans = new StringBuilder();

        int i = 0;

        while(i < command.length()) {

            if(command.charAt(i) == 'G') {
                ans.append('G');
                i++;
            }
            else if(command.startsWith("()", i)) {
                ans.append('o');
                i += 2;
            }
            else if(command.startsWith("(al)", i)) {
                ans.append("al");
                i += 4;
            }
        }

        return ans.toString();
    }
}
```

### Ek alternative — replace()


Is question ko aur bhi short kar sakte hain:

```java
class Solution {
    public String interpret(String command) {

        return command
                .replace("()", "o")
                .replace("(al)", "al");
    }
}

1528. Shuffle String
Solved
Easy
Topics
premium lock icon
Companies
Hint
You are given a string s and an integer array indices of the same length. The string s will be shuffled such that the character at the ith position moves to indices[i] in the shuffled string.

Return the shuffled string.

 

Example 1:


Input: s = "codeleet", indices = [4,5,6,7,0,2,1,3]
Output: "leetcode"
Explanation: As shown, "codeleet" becomes "leetcode" after shuffling.
Example 2:

Input: s = "abc", indices = [0,1,2]
Output: "abc"
Explanation: After shuffling, each character remains in its position.

class Solution {
    public String restoreString(String s, int[] indices) {

        char[] ans = new char[s.length()];

        for(int i = 0; i < s.length(); i++) {
            ans[indices[i]] = s.charAt(i);
        }

        return new String(ans);
    }
}
```
