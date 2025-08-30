# PROGRAMMING ASSIGNMENT 2

This repository contains my Jupyter Notebook submission for **ECE 2112: Advanced Computer Programming and Algorithms – Experiment 2**, covering two Python problems:
**Normalization** and **Divisible by 3**.

> Source of problems: *EXPERIMENT 2 - Numerical Python.pdf*

---

## Project Structure

```
.
├─ 2ECEB_LUCAS_PA2.ipynb   # Jupyter notebook with solutions
└─ README.md               # You're here
```

---

# NORMALIZATION

## Problem Description
**NORMALIZATION PROBLEM**: Normalization is one of the most basic preprocessing techniques in
data analytics. This involves centering and scaling process. Centering means subtracting the data from the
mean and scaling means dividing with its standard deviation. Mathematically, normalization can be
expressed as: 

$$
Z = \frac{X - \mu}{\sigma}
$$

In Python, element-wise mean and element-wise standard deviation can be obtained by using .mean() and
.std() calls. 

In this problem, create a random 5 x 5 ndarray and store it to variable X. Normalize X. Save your normalized
ndarray as *X_normalized.npy*

---

## Implementation and Explanation

### 1. Define the function
We first define a function named `alphabet_soup()` with `x` as the parameter representing the input string.  

```python
def alphabet_soup(x):
```

### 2. Convert string to list and sort
Convert the string `x` into a list so that each character can be worked with individually. After this, the list is sorted alphabetically using the `sort()` method.  

```python
    x = list(x)            
    x.sort()               
```

### 3. Initialize a placeholder
Initialize an empty string `y` which will act as the placeholder for the final result.  

```python
    y = ""                 
```

### 4. Build the sorted string
Use a `for` loop to go through each character in the sorted list. During every iteration, the character is appended to `y`.  

```python
    for z in x:            
        y = y + z          
```

### 5. Print the result
After the loop, all the characters are combined into one string that is alphabetically arranged. Finally, the function prints the result to display the output.  

```python
    print(y)               
```

### 6. Test the function
The function is tested using the strings `"hello"` and `"hacker"`.  

```python
alphabet_soup("hello")    
alphabet_soup("hacker")    
```

**Sample Output:**  

```
ehllo
acehkr
```

---

# EMOTICON PROBLEM

## Problem Description
**EMOTICON PROBLEM:** Create a function that changes specific words into emoticons. Given a sentence as a string, replace the words **smile**, **grin**, **sad**, and **mad** with their corresponding emoticons:  

- `smile` → `:)`  
- `grin`  → `:D`  
- `sad`   → `:((`  
- `mad`   → `>:(`  

---

## Implementation and Explanation

### 1. Define the function
We define a function named `emotify()` with `x` as the parameter representing the input string.  

```python
def emotify(x):
```

### 2. Copy the input string
Copy the input string `x` into a working variable `y`, which will be used for making replacements.  

```python
    y = x
```

### 3. Replace "smile" with emoticon
Check if `"smile"` is in the string. If found, replace it with `:)`.  

```python
    if "smile" in x:
        for z in ["smile", "Smile", "SMILE"]:
            y = y.replace(z, ":)")
```

### 4. Replace "grin" with emoticon
Check if `"grin"` is in the string. If found, replace it with `:D`.  

```python
    if "grin" in x:
        for z in ["grin", "Grin", "GRIN"]:
            y = y.replace(z, ":D")
```

### 5. Replace "sad" with emoticon
Check if `"sad"` is in the string. If found, replace it with `:((`.  

```python
    if "sad" in x:
        for z in ["sad", "Sad", "SAD"]:
            y = y.replace(z, ":((")
```

### 6. Replace "mad" with emoticon
Check if `"mad"` is in the string. If found, replace it with `>:(`.  

```python
    if "mad" in x:
        for z in ["mad", "Mad", "MAD"]:
            y = y.replace(z, ">:(")
```

### 7. Print the result
After processing all keywords, print the final string with the emoticons.  

```python
    print(y)
```

### 8. Test the function
Test the function with example strings.  

```python
emotify("Make me smile")
emotify("I am mad")
```

**Sample Output:**  

```
Make me :)
I am >:(
```

---

# UNPACKING LIST PROBLEM

## Problem Description
**UNPACKING LIST PROBLEM:** Unpack the list `writeyourcodehere` into three variables:  

- `first` → the first element  
- `middle` → everything between the first and last element  
- `last` → the last element  

Then print all three variables.  

---

## Implementation and Explanation

### 1. Define the list
Start with the given list.  

```python
lst = [1, 2, 3, 4, 5, 6]
```

### 2. Extract the first element
Assign the first element of the list to the variable `first`.  

```python
first = lst[0]    # input the first element (index 0) of the list as "first"
```

### 3. Extract the middle elements
Assign all elements between the first and last to the variable `middle`.  

```python
middle = lst[1:-1]    # input the elements between first and last (index 1 to -1) as "middle"
```

### 4. Extract the last element
Assign the last element of the list to the variable `last`.  

```python
last = lst[-1]    # input the last element (-1) as "last"
```

### 5. Print the results
Print the three variables to display their values.  

```python
print("first:", first, " middle:", middle, " last:", last)
```

**Sample Output:**  

```
first: 1  middle: [2, 3, 4, 5]  last: 6
```

---

**Author:** LUCAS, Beatrice Sophia

**Section:** 2ECE-B

**Course:** ECE 2112 (Advanced Computer Programming and Algorithms)  
