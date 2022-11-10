# Week 5: Lab Report 3

## grep

**grep** is used to find a given pattern inside a file. The command would return the line where the pattern is found.

### -c

We can use -c to return only the **count** of lines that match to the pattern.

> Example 1:
> 
> ```bash
> grep -c "three" rr74.txt
> ```
>
> ![](week5_6.png)

> Example 2:
> 
> ```bash
> grep -c "as" rr74.txt
> ```
> 
> ![](week5_9.png)

> Example 3:
> 
> ```bash
> grep -c "apple" rr74.txt
> ```
> 
> ![](week5_10.png)

### -i

We can use -i to **ignore case** on the pattern we are looking for.

> Example 1:
>
> ```bash
> grep -i "section" rr74.txt
> ```
> 
> ![](week5_7.png)

> Example 2:
>
> ```bash
> grep -i "Sample" rr74.txt
> ```
> 
> ![](week5_11.png)

> Example 3:
>
> ```bash
> grep -i "conclusion" rr74.txt
> ```
> 
> ![](week5_12.png)

### -w

We can use -w to find lines with **whole** words that match the pattern.

> Example 1:
>
> ```bash
> grep -w "as" rr74.txt
> ```
> 
> ![](week5_8.png)

> Example 2:
>
> ```bash
> grep -w "As" rr74.txt
> ```
> 
> ![](week5_13.png)

> Example 3:
>
> ```bash
> grep -w "section" rr74.txt
> ```
>
> ![](week5_14.png)
>
> (Note that in Example 1 of **grep -i**, **-i "section"** returned lines with the pattern "section" regardless if it is a whole word; however, since no **whole words** in the file is "section", nothing is returned in this example.)