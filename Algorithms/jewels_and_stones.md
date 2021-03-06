Problem:

You're given strings J representing the types of stones that are jewels, and S representing the stones you have.  Each character in S is a type of stone you have.  You want to know how many of the stones you have are also jewels.

The letters in J are guaranteed distinct, and all characters in J and S are letters. Letters are case sensitive, so "a" is considered a different type of stone from "A".

Example 1:
```
Input: J = "aA", S = "aAAbbbb"
Output: 3
```

Example 2:
```
Input: J = "z", S = "ZZ"
Output: 0
```
Note:

S and J will consist of letters and have length at most 50.
The characters in J are distinct.

Solution:

Java:
```
import java.util.HashSet;
import java.util.Set;

class Solution {
    public int numJewelsInStones(String J, String S) {
        if ( J == null || J.length() == 0 )
            return 0;
        if ( S == null || S.length() == 0 )
            return 0;
        

        char[] jArray = J.toCharArray();
        Set jSet = new HashSet();
        for (char j : jArray) {
            jSet.add(j);
        }

        char[] sArray = S.toCharArray();
        int count = 0;
        for (char s : sArray) {
            if (jSet.contains(s))
                count++;
        }

        return count;
    }
}
```

Python:

```
class Solution:
    def numJewelsInStones(self, J, S):
        """
        :type J: str
        :type S: str
        :rtype: int
        """
        info = set(J)
        return sum( c in info for c in S )
```
