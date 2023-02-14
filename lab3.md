# Lab Report 3
---

# Grep Command and Options
The grep filter is used to search a file for a particular pattern of characters and displays all lines that containes the pattern.   
`grep [options] pattern [files]`
Here are some examples of options that you can use with grep.
```
-c : This prints only a count of the lines that match a pattern
-h : Display the matched lines, but do not display the filenames.
-i : Ignores, case for matching
-l : Displays list of a filenames only.
-n : Display the matched lines and their line numbers.
```
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
**Input**   
`$grep -i "tHe" file.txt`   
**Output**    
```
Eating an apple a day is said to keep the doctor away due to the fruit's high nutritional value.
The logo of the technology company Apple Inc. features a stylized apple with a bite taken out of it.
In Greek mythology, the golden apple was a symbol of temptation and was the catalyst for the Trojan War.
Apple cider is a popular autumn beverage made from fermented apples and often spiced with cinnamon and other flavors.
```
