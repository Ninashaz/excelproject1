# Excel Data Transformation Project
## 📁 Project Overview
This project demonstrates data cleaning and transformation techniques using Microsoft Excel. The dataset contains customer information, and the goal was to create new calculated columns using text functions and formulas.

## 📊 Original Data Structure
The dataset includes the following columns:

First Name, Last Name

Phone

Street Address

Zipcode

Req Date (Request Date)

## 🛠️ Transformations Applied
I created several new columns using Excel formulas:

1. Full Name (Column Q)
Formula: =[@[First Name]] & " " & [@[Last Name]]
Combines first and last names into a single column.

2. Phone Number Components (Columns R, S)
Formulas:

Area Code: =LEFT([@Phone], FIND(")", [@Phone])-1)

Phone Digits: =MID([@Phone], FIND(") ", [@Phone])+2, 8)

3. Numeric Phone (Column T)
Formula: =SUBSTITUTE(SUBSTITUTE([@Phone], "(", ""), ")", "")
Removes parentheses from the phone number.

4. Street Name Extraction (Column U)
Formula: =TRIM(RIGHT(SUBSTITUTE([@[Street Address]], " ", REPT(" ", 100)), 100))
Extracts the street name (e.g., "Drive", "Avenue") from the full address.

5. Address-Zipcode Combination (Column V)
Formula: =[@[Street Address]] & " -" & [@Zipcode]
Combines street address and zipcode into a single string.

6. Username Generation (Column W)
Formula: =LEFT([@[First Name]],3) & LEFT([@[Last Name]],3) & [@Area Code]
Creates a username from the first 3 letters of the first name, last name, and area code.

7. Formatted Date (Column O)
Formula: ="(" & DAY([@[Req Date]]) & "," & TEXT([@[Req Date]],"MMMM") & "," & YEAR([@[Req Date]]) & ")"
Formats the date into a readable style (e.g., (19,July,2014)).

8. Year Extracted (Column P)
Formula: =YEAR([@[Req Date]])
Extracts the year from the request date.

## 📈 Skills Demonstrated
Advanced Excel functions (LEFT, RIGHT, MID, FIND, SUBSTITUTE, TEXT, TRIM)

Data cleaning and transformation

String manipulation

Date formatting

Formula automation

## 🚀 How to Use
Download the Tamrin6_Nina.xlsx file.

Open it in Microsoft Excel.

Explore the formulas in columns Q:W to understand the transformations.

