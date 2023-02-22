# Lab Report 3
---

# Grep Command and Options
The grep filter is used to search a file for a particular pattern of characters and displays all lines that containes the pattern.   
`grep [options] pattern [files]`
Here are some examples of options that you can use with grep.
```
-c : This prints only a count of the lines that match a pattern
-i : Ignores, case for matching
-n : Display the matched lines and their line numbers.
-v : This prints out all the lines that do not matches the pattern
```

## Examples
Consider the following .txt file as input  
written_2/written_2/berlitz2/Bahamas-History.txt

## Case Insensitive Search -i | Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/
The -i option enables to search for a string case insensitively in the given file. "LuCaYans" and "lucayanS" will result in the same result.  
**Input**   
`james@MacBook-Pro-2 berlitz2 % grep -i "LuCaYans" Bahamas-History.txt`     
**Output**    
```
Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```
**Input**   
`james@MacBook-Pro-2 berlitz2 % grep -i "lucayanS" Bahamas-History.txt`  
**Output**    
```
Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```
The above commands are looking for a line that contains the same case-insensitive string pattern for "LuCaYans" and "lucayanS" which is all variations of "lucayans" in Bahamas-History.txt. Since 2 lines in Bahamas-History.txt include the string pattern "lucayans" in any form, the command returns 2 lines. This command is useful for searching up all instances of a string pattern without thinking about the uppercase and lowercase of each letter.
  
## Displaying the Number of Matches -c | Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/
We can find the number of lines that matches the given string/pattern.    
**Input**   
`james@MacBook-Pro-2 berlitz2 % grep -c "Lucayans" Bahamas-History.txt`     
**Output**    
```
2
```
**Input**   
`james@MacBook-Pro-2 berlitz2 % grep -c "lucayans" Bahamas-History.txt`    
**Output**    
```
0
```
The above command is looking for the number of lines that contains the exact same string pattern for "Apple" in file.txt. Since 2 lines include the string pattern "Lucayans", the command returns 2. However, if the string pattern searched is "lucayans" the command will return 0 since the exact string pattern does not exist within the file. This command is useful for searching up the number of instances a (case sensitive) specific string pattern is used within a file.

## Show line number with Output -n | Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/
To show the line number of file with the line matched. 
**Input**   
`$grep -n "Apple" file.txt`     
**Output**    
```
1:Apples are a type of fruit that come in various colors such as red, green, and yellow.
3:Apples can be used in a variety of dishes such as pies, crisps, and sauces.
4:The logo of the technology company Apple Inc. features a stylized apple with a bite taken out of it.
6:Apple cider is a popular autumn beverage made from fermented apples and often spiced with cinnamon and other flavors.
```
The above command is looking for lines and number of line within the file that contains the exact same string pattern for "Apple" in file.txt.
Since lines 1, 3, 4, 6 include the string pattern "Apple", the command returns each line with its line number like above.
This command is useful for searching up for where exactly the string pattern is located within a file and the contents of each line that has it.

**Input**   
`$grep -n "the" file.txt`   
**Output**    
```
2:Eating an apple a day is said to keep the doctor away due to the fruit's high nutritional value.
4:The logo of the technology company Apple Inc. features a stylized apple with a bite taken out of it.
5:In Greek mythology, the golden apple was a symbol of temptation and was the catalyst for the Trojan War.
6:Apple cider is a popular autumn beverage made from fermented apples and often spiced with cinnamon and other flavors.
```
The above command is looking for lines and number of line within the file that contains the exact same string pattern for "the" in file.txt. Since lines 2, 4, 5, 6 include the string pattern "the", the command returns each line with its line number like above. This command is useful for searching up for where exactly the string pattern is located within a file and the contents of each line that has it.

## Inverting the Pattern Match -v | Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/
You can display the lines that are not matched with the specified search string pattern using the -v option.  
**Input**   
`$grep -v "Apple" file.txt`     
**Output**    
```
Eating an apple a day is said to keep the doctor away due to the fruit's high nutritional value.
In Greek mythology, the golden apple was a symbol of temptation and was the catalyst for the Trojan War.
```
The above command is looking for lines within the file that does **not** contain the exact same string pattern for "Apple" in file.txt. Since lines 2, 5 do not include the specific string pattern "Apple", the command only returns the two lines. This command is useful for looking up lines that does not include a specific string pattern.

**Input**   
`$grep -v "the" file.txt`   
**Output**    
```
Apples are a type of fruit that come in various colors such as red, green, and yellow.
Apples can be used in a variety of dishes such as pies, crisps, and sauces.
```
The above command is looking for lines within the file that does **not** contain the exact same string pattern for "the" in file.txt. Since lines 1, 3 do not include the string pattern "the", the command only returns the two lines. This command is useful for looking up lines that does not include a specific string pattern.
