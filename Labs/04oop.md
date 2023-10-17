---
title: "Lab 4: Object-Oriented Programming and Pandas"
layout: single
author_profile: false
classes: wide
excerpt: Practice writing python classes and integrate OOP concepts with the functionality of the pandas library.
---

### Instructions
* *Accept the Assignment*: When you accept the assignment in GitHub Classroom, a repository named `lab-04` will be automatically generated for you under the "s386Fall2023" organization.
* *Locate Your Repository*: Your personal repository for this homework can be found at `https://github.com/s386Fall2023/lab-04-your_user_name`.
* *Clone the Repository*: 
    - Open your terminal and navigate to the directory where you want to download the repository.
    - Run `git clone [your repository URL]` to clone the repository onto your local machine.
* *Working Directory*: The cloning process will create a new directory named `lab-04-your_user_name`. Ensure that you perform all your work inside this directory.
* *Commit Your Progress*: As you work on the assignment, remember to commit your changes periodically. You can easily do this using Visual Studio Code (VS Code).
* *Remote Connection*: If you've cloned the repository correctly and are working within the created directory, the remote link to your GitHub repository should already be configured.
* *File and Function Names*: 
    - Your Classes should be in the file `digital_library.py`.  
    - You should include a file that tests the classes in the file `library_test.py`
    - **Do not** change the names of the files, functions, methods, or Classes.
* *Virtual Environment*: Ensure that you are using the class's virtual environment while working on this assignment.
   - Note:  There is no way to tell from your submission whether or not you use the class environment.  However, if you are working in the virtual environment set up for our class, then you can be sure that you are using the correct versions of the packages.
* *Other Files:*
   - You are free to include other `.py` or `.ipynb` files with more of your work. However, ensure that `digital_library.py` contains the final code for each Class and `test_library.py` contains the code to test your classes. 

* *Submitting on Gradescope*: 
    - Once you've completed the assignment, go to Gradescope and select your personal homework repository (`https://github.com/s386Fall2023/lab-04-your_user_name`) as the source for your submission.
    
### Data
The data for this lab is `library_books.csv` found in the "CleanData" folder of my GitHub [Data Repository](https://github.com/esnt/Data/tree/main/CleanData).  This data is a simplified and cleaned subset from [Zenodo](https://zenodo.org/record/4265096).  It has the following columns:
1. `book_id`: Unique identifier for each book.
2. `title`: Title of the book.
3. `author`: Author of the book.
4. `genre`: Genre of the book (e.g., Fiction, Non-Fiction, Mystery, Sci-Fi).
5. `pages`: Number of pages in the book.
6. `published_year`: The year the book was published.

#### Objective: 
The goal of this assignment is to merge foundational concepts from object-oriented programming with the utility of the Pandas library. By the end, you should be able to create classes that can effectively interact with and manipulate Pandas data structures.

#### Problem Statement:  
You are a data analyst at a digital library. Your task is to design a system that can process, manipulate, and analyze data regarding different books available in the library.


---
### Task 1: Create a `Book` class
#### Attributes:
- `book_id`
- `title`
- `author`
- `genre`
- `pages`
- `published_year`

#### Methods:
- `get_age()`: Should return the age of the book based on the current year.
- `is_long()`: Should return `True` if the book has more than 300 pages; otherwise, `False`.
- `summary()`: Should return a string with the format: "Book ID `book_id`: `title` by `author` has `pages` pages. It was first published in `published_year` and belongs to the `genre` genre."

---
### Task 2: Create a `Library` class
#### Attributes:
- `data`: A pandas DataFrame loaded from the provided CSV file.
- `size`: Number of books in the library.
- `authors`: Number of unique authors in the library.

#### Methods:
- `add_book(book: Book)`: Takes an instance of `Book` and adds it to the DataFrame. All `Library` attributes should be updated accordingly.
   * If the book already exists in library the method should return the string "Error: book_id `book_id` is already in the library."
- `remove_book(book_id: str)`: Takes a `book_id` and removes the corresponding book from the DataFrame. All `Library` attributes should be updated accordingly.  
   * If the `book_id` is not in the library, the method should return the string: "Error: `book_id` is not in the library."
- `get_books_by_author(author: str)`: Takes an author's name and returns a DataFrame containing all books by that author.
   * If `author` is not in the library, the method should return the string: "No books by `author` in library"
- `get_genre_count()`: Should return a series with the count of books in each genre.
- `get_book_summary(book_id: str)`: Takes a `book_id` and returns a string with the format:  
   * "Book ID `book_id`: `title` by `author` has `pages` pages. It was first published in `published_year` and belongs to the `genre` genre."  
   * If the `book_id` is not in the library, it should return "No matching book in the library."
- `__str__()`: Should return a string representing the library. When a `Library` object is printed, the string "There are `size` books in the library by `authors` unique authors. The oldest book in the library is `title` by `author` published in `published_year`." should be output.

#### Additional Notes:
- Please ensure to update the `size` and `authors` attributes of the `Library` class appropriately whenever a book is added or removed.

---
### Task 3:  Test your Classes
In the `test_library.py` file write python code that:
* Creates instances of the `Book` class
* Initializes a `Library` using [`library_books.csv`](https://github.com/esnt/Data/tree/main/CleanData)
* Tests all methods of both classes to ensure they work as expected
* Ensure that your code is well-commented and that both files are free of syntax errors and run without issues

