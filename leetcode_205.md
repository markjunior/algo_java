**205**. Isomorphic Strings
Given two strings s and t, determine if they are isomorphic.
Two strings are isomorphic if the characters in s can be replaced to get t.
All occurrences of a character must be replaced with another character while preserving the order of characters. No two characters may map to the same character but a character may map to itself.

For example,
Given "egg", "add", return true.
Given "foo", "bar", return false.
Given "paper", "title", return true.



```
public class Solution {
    public boolean isIsomorphic(String s, String t) {
        char[] a=s.toCharArray();
        char[] b=t.toCharArray();
        HashMap<Character, Character> test= new HashMap<Character, Character>();
        int iter=0;
        for(char i : a){
            if(test.containsKey(i)){
                if(test.get(i)!=b[iter]){
                    return false;
                }
            }else{
                if(test.containsValue(b[iter])){
                    return false;
                }else{
                    test.put(i,b[iter]);
                }
            }

            iter++;
        }
        return true;
    }
}
```
