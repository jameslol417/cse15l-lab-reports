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
`$cat > file.txt`
```
Apples are a type of fruit that come in various colors such as red, green, and yellow.
Eating an apple a day is said to keep the doctor away due to the fruit's high nutritional value.
Apples can be used in a variety of dishes such as pies, crisps, and sauces.
The logo of the technology company Apple Inc. features a stylized apple with a bite taken out of it.
In Greek mythology, the golden apple was a symbol of temptation and was the catalyst for the Trojan War.
Apple cider is a popular autumn beverage made from fermented apples and often spiced with cinnamon and other flavors.
```

## Case Insensitive Search -i
The -i option enables to search for a string case insensitively in the given file. "ApPle" and "APpLe" will result in the same result.  
**Input**   
`$grep -i "APpLe" file.txt`     
**Output**    
```
Apples are a type of fruit that come in various colors such as red, green, and yellow.
Eating an apple a day is said to keep the doctor away due to the fruit's high nutritional value.
Apples can be used in a variety of dishes such as pies, crisps, and sauces.
The logo of the technology company Apple Inc. features a stylized apple with a bite taken out of it.
In Greek mythology, the golden apple was a symbol of temptation and was the catalyst for the Trojan War.
Apple cider is a popular autumn beverage made from fermented apples and often spiced with cinnamon and other flavors.
```
The above command is looking for a line that contains the same case-insensitive string pattern for "APpLe" in file.txt. It is useful for searching up all instances of a word without thinking about the uppercase and lowercase of each letter.

**Input**   
`$grep -i "tHe" file.txt`   
**Output**    
```
Eating an apple a day is said to keep the doctor away due to the fruit's high nutritional value.
The logo of the technology company Apple Inc. features a stylized apple with a bite taken out of it.
In Greek mythology, the golden apple was a symbol of temptation and was the catalyst for the Trojan War.
Apple cider is a popular autumn beverage made from fermented apples and often spiced with cinnamon and other flavors.
```
* The above command is looking for a line that contains the same case-insensitive string pattern for "tHe" in file.txt. It is useful for searching up all instances of a word without thinking about the uppercase and lowercase of each letter.    
## Displaying the Number of Matches -c
We can find the number of lines that matches the given string/pattern.    
**Input**   
`$grep -c "Apple" file.txt`     
**Output**    
```
4
```
The above command is looking for the number of lines that contains the exact same string pattern for "Apple" in file.txt. It is useful for searching up the number of instances a specific word is used within a file.
**Input**   
`$grep -c "the" file.txt`     
**Output**    
```
4
```
The above command is looking for the number of lines that contains the exact same string pattern for "the" in file.txt. It is useful for searching up the number of instances a specific word is used within a file.
## Show line number with Output -n
To show the line number of file with the line matched. 
**Input**   
`$grep -n "Apple" file.txt`     
**Output**    
```
4: The logo of the technology company Apple Inc. features a stylized apple with a bite taken out of it.
6: Apple cider is a popular autumn beverage made from fermented apples and often spiced with cinnamon and other flavors.
```
The above command is looking for lines and number of line within the file that contains the exact same string pattern for "Apple" in file.txt. It is useful for searching up for where exactly the string is located within a file.
**Input**   
`$grep -n "the" file.txt`   
**Output**    
```
2: Eating an apple a day is said to keep the doctor away due to the fruit's high nutritional value.
4: The logo of the technology company Apple Inc. features a stylized apple with a bite taken out of it.
5: In Greek mythology, the golden apple was a symbol of temptation and was the catalyst for the Trojan War.
```
The above command is looking for lines and number of line within the file that contains the exact same string pattern for "the" in file.txt. It is useful for searching up for where exactly the string is located within a file.
## Inverting the Pattern Match -v 
You can display the lines that are not matched with the specified search string pattern using the -v option.  
**Input**   
`$grep -v "Apple" file.txt`     
**Output**    
```
Apples are a type of fruit that come in various colors such as red, green, and yellow.
Eating an apple a day is said to keep the doctor away due to the fruit's high nutritional value.
Apples can be used in a variety of dishes such as pies, crisps, and sauces.
In Greek mythology, the golden apple was a symbol of temptation and was the catalyst for the Trojan War.
```
The above command is looking for lines within the file that does **not** contain the exact same string pattern for "Apple" in file.txt. It is useful for looking up lines that does not include a specific string.
**Input**   
`$grep -v "the" file.txt`   
**Output**    
```
Apples are a type of fruit that come in various colors such as red, green, and yellow.
Apples can be used in a variety of dishes such as pies, crisps, and sauces.
Apple cider is a popular autumn beverage made from fermented apples and often spiced with cinnamon and other flavors.
```
The above command is looking for lines within the file that does **not** contain the exact same string pattern for "the" in file.txt. It is useful for looking up lines that does not include a specific string.
