This is in the HashMap part of leetcode, so technically solution should use HashMap but there are two good solutions:

## Solution 1 - HashMap
``` java
class Solution {
    public boolean canConstruct(String ransomNote, String magazine) {
	
		HashMap<Character,Integer>map=new HashMap<>();

		//for each char in magazine, add to has map with count
        for(int i=0;i<magazine.length();i++){
            char c=magazine.charAt(i);
            if(!map.containsKey(c)){
                map.put(c,1);
            }else{
                map.put(c,map.get(c)+1);
            }
        }

		//traverse through ransom note
        for(int i=0;i<ransomNote.length();i++){
            char c=ransomNote.charAt(i);
            // if the map has ransom note letter
            // and the count is over 0
            // remove a count and keep going
            if(map.containsKey(c) && map.get(c)>0){
                map.put(c,map.get(c)-1);
            }
            else {
            // otherwise, if the char in ransom note 
            // is not present in map, return false
                return false;
            }
        }
        return true;
    }
}
```

## Solution 2 - Array
``` java
class Solution {
    public boolean canConstruct(String ransomNote, String magazine) {
	
			char[] ransom = ransomNote.toCharArray();
			char[] mag = magazine.toCharArray();
			//keep track of count of letter using 
			//characters index
			int[] letters = new int[26];

			for (char c : ransom) {
				// character - 'a' give the alphabetical index
				// ++ adds one to signify count to the index
				letters[c - "a"]++;
			}

			for (char c : mag) {
			// for the char in mag, it takes away count 1
			// from the index (character - 'a')
				letters[c - "a"]--;
				if (letters[c - "a"] == -1) {
				// if the count s =1, this mean it doesn't
				//contain letter, so can return false
					return false;
				}
			}
			
		return true;
    }
}

```


## Alphabetical Index

We can take an int Array and use as index for the alphabet. This is simple.

Initialise the array with 26 as there are 26 letters in the alphabet.

``` java
int[] alphabet = new int[26];
```

Then, we can use the following expression to convert a character into an index for an array, where index correspond to a letter in the alphabet.

``` java
letter - 'a'

//example : 'a' - 'a' = 0
```

**How?**
In Java, characters are represented using their ASCII (or Unicode) values. The characters all have specific number values;
- `a` has ASCII value of 97
- `b` has ASCII value of 98
- `c` has ASCII value of 99

Therefore, to get the index value, you must perform the following arithmetic:
- `a` : `letter - "a" = 97 - 97 = 0`
- `b` : `letter - "a" = 98 - 97 = 1`
- `c` : `letter - "a" = 99 - 97 = 2`

These index values now corresponds to a letter in the English alphabet.