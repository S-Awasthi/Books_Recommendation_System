# Data Mining Preprocessing

## Overview
This project focuses on preprocessing data for a data mining application. The primary goal is to prepare the dataset for mining frequent patterns using the FP-Growth algorithm, an efficient and scalable method for mining the complete set of frequent itemsets.

## Features
- **Data Loading:** Import and preprocess data from CSV files.
- **Data Cleaning:** Handle missing values and data inconsistencies.
- **FP-Growth Algorithm:** Implement the FP-Growth algorithm to find frequent patterns.

## Installation
1. Clone the repository or download the project files.
2. Install the required libraries:
    ```bash
    !pip install pandas
    !pip install matplotlib
    !pip install seaborn
    ```

## Usage
1. **Load Data:**
    ```python
    import pandas as pd
    from IPython.display import display
    import matplotlib.pyplot as plt
    import seaborn as sns

    books = pd.read_csv('books_data/books.csv', sep=";", encoding="latin-1", on_bad_lines='skip')
    books.columns = ['ISBN', 'bookTitle', 'bookAuthor', 'yearOfPublication', 'publisher', 'imageUrlS', 'imageUrlM', 'imageUrlL']
    books.drop(['imageUrlS', 'imageUrlM', 'imageUrlL'], axis=1, inplace=True)

    users = pd.read_csv('books_data/users.csv', sep=';', encoding="latin-1", on_bad_lines='skip')
    users.columns = ['userID', 'Location', 'Age']
    users.drop(['Location'], axis=1, inplace=True)

    ratings = pd.read_csv('books_data/ratings.csv', sep=';', encoding="latin-1", on_bad_lines='skip')
    ratings.columns = ['userID', 'ISBN', 'bookRating']

    print(books.shape)
    print(users.shape)
    print(ratings.shape)
    ```
2. **Display Data:**
    ```python
    display(books.head(10))
    display(users.head(10))
    display(ratings.head(10))
    ```

3. **FP-Growth Algorithm:**
    - **Frequency Counting:** Compute the support count for each item.
    - **FP-Tree Construction:** Create the FP-tree.
    - **FP-Tree Mining:** Recursively mine the FP-tree to extract frequent itemsets.

## Contributing
Contributions are welcome! Please fork the repository and submit a pull request for any improvements.

## Acknowledgements
This project utilizes Pandas, Matplotlib, and Seaborn for data handling and visualization.

## References
- [FP-Growth Algorithm](https://en.wikipedia.org/wiki/FP-growth_algorithm)

## Project Links
- [Google Colab Project](https://colab.research.google.com)
- [Dataset](https://example.com/dataset)

