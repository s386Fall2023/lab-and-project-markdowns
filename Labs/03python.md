---
title: "Lab 3: Anaconda , VS Code, and Python Practice"
layout: single
author_profile: false
classes: wide
excerpt: Finish setting up Anaconda and VS code.  Practice basic python skills.
---

## 1. Anaconda virtual environment 
In order to ensure that we are all running the same version of python and of the packages we'll be using, create a (conda) virtual environment for our class. Type (or copy and paste) the following commands in order (and one at a time) in the terminal or Anaconda prompt.  Type `y` when you are asked if you want to proceed after each command.
1. Create the environment

    ```conda create --name stat386 python==3.10.12```
2. Activate the environment you just created:

    ```conda activate stat386```
3. Install necessary packages into the environment (these packages are available in the conda channel)

    ```conda install beautifulsoup4=4.12.2 hdf5=1.12.1 html5lib=1.1 ipykernel=6.25.0 jupyter=1.0.0 ipython=8.12.2 matplotlib=3.7.1 matplotlib-inline=0.1.6 nltk=3.8.1 notebook=6.5.4 numpy=1.25.2 openpyxl=3.0.10 pandas=1.5.3 pillow=9.4.0 requests=2.31.0 scikit-learn=1.3.0 scrapy=2.8.0 seaborn=0.12.2 scipy=1.11.1 statsmodels=0.14.0 selenium=3.141.0```
4. Install plotly (available from the plotly channel)

    ```conda install -c plotly plotly=5.16.0```
5. Install streamlit (available from pip)

    ```pip install streamlit```

## 2. VS Code
1. Install the following extensions.  To install an extension, click on the "Extensions" icon on the left most toolbar, search for the extension name in the search bar, and click the "Install" button.  
    * GitHub Pull Requests and Issues
    * Python (by Microsoft)
    * Jupyter (by Microsoft)
2. Sign into GitHub through VS Code by clicking on the "GitHub" icon on the left most toolbar and clicking "Sign in". 

## 3. Finish Blog Setup

1. If you haven't already, finish setting up your blog following [these instructions]({{site.url}}/{{site.baseurl}}/resources/blogsetup).


## 4. Python review questions.

* *Accept the Assignment*: When you accept the assignment in GitHub Classroom, a repository named `lab-03` will be automatically generated for you under the "s386Fall2023" organization.
* *Locate Your Repository*: Your personal repository for this homework can be found at `https://github.com/s386Fall2023/lab-03-your_user_name`.
* *Clone the Repository*: 
    - Open your terminal and navigate to the directory where you want to download the repository.
    - Run `git clone [your repository URL]` to clone the repository onto your local machine.
* *Working Directory*: The cloning process will create a new directory named `lab-03-your_user_name`. Ensure that you perform all your work inside this directory.
* *Commit Your Progress*: As you work on the assignment, remember to commit your changes periodically. You can easily do this using Visual Studio Code (VS Code).
* *Remote Connection*: If you've cloned the repository correctly and are working within the created directory, the remote link to your GitHub repository should already be configured.
* *File and Function Names*: 
    - Place all functions for this lab in a file named `lab3.py`.
    - Inside `lab3.py`, you'll find functions with `pass` statements. Replace `pass` with your own code.
    - **Do not** change the names of the functions or the file.
* *Virtual Environment*: Ensure that you are using the class's virtual environment while working on this assignment.
    - You are free to include other `.py` or `.ipynb` files with more of your work. However, ensure that `lab3.py` only contains your final code for each function. 

* *Submitting on Gradescope*: 
    - Once you've completed the assignment, go to Gradescope and select your personal homework repository (`https://github.com/s386Fall2023/lab-03-your_user_name`) as the source for your submission.
    

 

**1.  Write a Python function that will compute the Euclidean distance between any two points.  The function should accept as input two tuples in the form of ((x<sub>1</sub>, y<sub>1</sub>),(x<sub>2</sub>, y<sub>2</sub>)) and return the Euclidean distance.**

*Example output:*

```
In [1]: euclid_dist((1,3),(7,11))
out[1]: 10
```

-----
**2. Write a Python function that computes the value of ``n + nn + nnn`` where ``n`` is an integer.  For example if,  ``n=2``, the function should return ``246`` (which is the sum of 2+22+222).**  

*Example output:*

```
In [1]: sum_ns(2)
Out[1]: 246
```

-----
**3. Write a Python function that determines if ``n`` is a perfect square, where ``n`` is an integer.  The function return either "False" or "n is a perfect square of x"  (where ``n`` and ``x`` are appropriate for the input).**

*Example output:*

```
In [1]: perfect_square(24)
Out[1]: False

In [2]: perfect_square(25)
Out[2]: 25 is a perfect square of 5
```

----
**4. Write a Python function that checks whether a string is a palindrome or not.  A palindrome is a word or phrase that reads the same forwards and backwards (ignoring spaces), such as "madam" or "nurses run".**

*Example output:*

```
In [1]: is_palindrome('madam')
Out[1]: True

In [2]: is_palindrome('nurses run')
Out[2]: True

In [3]: is_palindrome('starlight')
Out[3]: False
```

----
**5. Write a Python function that accepts a string and calculates the number of upper case letters, the number of lower case letters, and the number of spaces.  The function should return a dictionary where the keys are "upper", "lower", and "space" and the value is the number of occurrences.  See the example output below.**    
(Hint:  check out what methods are available for strings.)  

 *Example output:*

```
In [1]: count_letter_types("HELLO!! How are you today?")
Out[1]: {'upper': 6, 'lower': 13, 'space': 4}

```


----
**6. Write a Python function that accepts a string a returns a dictionary where the key word is a word length and the value is a list of all the words that are that word length.  See the example output below.**  

*Example output: (note, it's okay if the keys of your dictionary are in a different order)*

```
In [1]: s = "It is a truth universally acknowledged that a single man in possession of a good fortune must be in want of a wife"

In [2]: count_word_lengths(s)

Out[2]: {1: ['a', 'a', 'a', 'a'],
         2: ['It', 'is', 'in', 'of', 'be', 'in', 'of'],
         3: ['man'],
         4: ['that', 'good', 'must', 'want', 'wife'],
         5: ['truth'],
         6: ['single'],
         7: ['fortune'],
         10: ['possession'],
         11: ['universally'],
         12: ['acknowledged']}
```


----
**7.  Write a python function that accepts an integer `n` (where 2 $\le$ `n` $\le$ 9) and returns a list of all the numbers between 0 and `n`00 that have an `n` in them AND are divisible by `n`. The function should produce the message `Invalid input: enter a number between 2 and 9` if an invalid number is used. See the example output below.**  

```
In [1]: n_list(3)
Out[1]: [3,
         30,
         33,
         36,
         39,
         63,
         ...
         300]

In [2]: n_list(10)
Out[2]: "Invalid input: enter a number between 2 and 9"
```


---
**8. Write a Python function that takes a list of numbers as input and calculates the sum of all even numbers in the list. Additionally, find the maximum value among these even numbers and determine how many times it appears in the list. Finally, print both the sum and the maximum value along with its frequency. See the example output below.**


```
In [1]: evens_mean_max([1,2,3,4,5,6])
Out[1]: The sum of the even numbers is 12.
        The maximum of the even numbers is 6 and it appears 1 time(s) in the list.

In [2]: evens_mean_max([1,7,2,3,7,4,5,6,7,6])
Out[1]: The sum of the even numbers is 18.
        The maximum of the even numbers is 6 and it appears 2 time(s) in the list.
```




