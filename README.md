# dip225-projekta-darbs-hkalnins
# Web Scraping with Selenium and Openpyxl

This repository contains a Python script that automates the process of searching for products on the salidzini.lv website and outputs the results to an Excel file.

## Contents

1. `projektdarbs.py` - This script asks the user to input a product and a minimum price. It then automates the user's input on the salidzini.lv website, including the minimum price the user would be willing to spend on the product. After applying these filters, the script outputs an Excel file showing the product, its price, and a link. Considering the advantages of salidzini.lv, these are the most advantageous offers from Latvian online stores.

## Libraries Used

### `Openpyxl`

- **Description**: `Openpyxl` is a Python library for reading and writing Excel files. It provides a high-level interface for creating and manipulating .xlsx files.
- **Usage in this Project**: In this project, `Openpyxl` is used to output the results of the web scraping into an Excel file. Each row in the Excel file represents a product with its price and a link.

### `Selenium`

- **Description**: `Selenium` is a powerful tool for controlling a web browser through the program. It is functional for all browsers.
- **Usage in this Project**: In this project, `Selenium` is used to automate user interactions and retrieve information from the salidzini.lv website. It inputs the user-specified product and price information and retrieves the resulting product data.

## Setup & Usage

### Prerequisites

- Python 3.x
- Openpyxl and Selenium libraries

### Running the Scripts

To run a script, simply execute it with Python. For example:

This will prompt you to enter a product and a minimum price. The script will then search for the product on the salidzini.lv website and output the results to an Excel file.
Note: If you want to change the web browser you are running the script you will need to change in the script the browser you are using in the lines 

## Output

The output of the script is an Excel file that is named as the word the User inputted and it is filled with the following columns:

1. Product: The name of the product.
2. Price: The price of the product.
3. Link: A link to the product.
4. Image: An image of the product.

The Excel file is saved in the same directory as the script.
