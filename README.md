# Grouping-anagram
Explanation:
The code is written in Java and is used to group anagrams together from a given list of strings. An anagram is a word formed by rearranging the letters of another word.

Here's a step-by-step explanation of the code:

The solver method takes an ArrayList of strings as input and returns an ArrayList of ArrayList of strings, which represents the groups of anagrams.

Inside the solver method, a HashMap named map is created. This map is used to store the anagram groups. The keys of the map are HashMap<Character, Integer> objects, which represent the frequencies of characters in a string. The values are ArrayList objects that store the strings belonging to the same anagram group.

The code iterates over each string in the input list.

For each string, a temporary HashMap named tempMap is created to count the frequency of characters in that string.

The code loops through each character of the current string and updates the frequency count in the tempMap. If the character is already present in the tempMap, its frequency is incremented by 1. Otherwise, a new entry is added with a frequency of 1.

After counting the frequencies of characters in the current string, the code checks if the tempMap already exists as a key in the map.

If the tempMap exists in the map, it means there is already an anagram group with the same frequency of characters. The current string is then added to the corresponding ArrayList value in the map.

If the tempMap is not present in the map, it means it's a new anagram group. In that case, a new ArrayList named tempList is created, the current string is added to it, and the tempMap and tempList pair is added to the map.

After processing all the strings in the input list, the code creates a new ArrayList named result to store the final grouped anagrams.

The code iterates over each key temp in the map, retrieves the corresponding value (which is an ArrayList of strings), and adds it to the result list.

Finally, the result list, which contains the grouped anagrams, is returned.

In the main method, a sample input list is created with some strings.

The solver method is called with the list as an argument, and the result is printed using System.out.println.

In this specific example, the input list contains the strings "cat", "dog", "ogd", "god", and "atc". Among these, "cat" and "atc" are anagrams, and "dog", "ogd", and "god" are anagrams. Therefore, the expected output is [[cat, atc], [dog, ogd, god]], which represents the two groups of anagrams.


Time Complexity: Let there be N-words and each word has a maximum of M characters. The upper bound is O(NM). 
Space Complexity: Let there be N-words and each word has maximum M characters, therefore max. storage space for each word with at max. M characters will be O(M), therefore for max N-words, it will be O(N*M). Therefore, the upper bound is O(NM).

