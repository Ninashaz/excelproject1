# Excel Text Transformation with Power Query & Formulas

This project demonstrates how to use **Power Query** and **Excel formulas** to clean and transform text data.  
It highlights two different approaches to solving the same problems — automated transformations in **Power Query** and classic **Excel formulas**.

---

## 📊 Dataset
The dataset contains customer information, including:
- First Name / Last Name
- Phone number
- Street Address
- Zipcode
- Request Date

---

## 🎯 Objectives
Using **Power Query** and **Excel formulas**, the exercise covers:

1. Combining text fields → Merging first and last names.  
2. Extracting substrings → Getting area codes and phone segments.  
3. Cleaning data → Removing unwanted characters (e.g., dashes, parentheses).  
4. Standardizing addresses → Extracting only street names.  
5. Fixing zip codes → Preserving leading zeros.  
6. Creating custom identifiers → Generating short unique IDs.  
7. Date formatting → Transforming dates into a custom text format like `(19, July, 2014)`.  
8. Extracting date parts → Isolating the year from dates.  

---

## 🛠️ Skills Demonstrated
- **Power Query transformations**
  - Split Columns
  - Merge Columns
  - Extract Text (Start, End, Range)
  - Replace Values
  - Change Data Types
  - Custom Columns with formulas  
- **Excel Formulas** for text manipulation  
- **Data Cleaning & Preparation**  
- **Automation** with Power Query (refresh when new data is added)  

---

## 📐 Excel Formulas Used

- **Full Name (Column Q)**  
  ```excel
  =[@[First Name]] & " " & [@[Last Name]]

- **Phone Number Components (Columns R, S)** 
  ```excel
  =LEFT([@Phone], FIND(")", [@Phone])-1)         // Area Code
  =MID([@Phone], FIND(") ", [@Phone])+2, 8)     // Phone Digits

- **Numeric Phone (Column T)**
  ```excel
  =SUBSTITUTE(SUBSTITUTE([@Phone], "(", ""), ")", "")

- **Street Name Extraction (Column U)**
  ```excel
  =TRIM(RIGHT(SUBSTITUTE([@[Street Address]], " ", REPT(" ", 100)), 100))

- **Address-Zipcode Combination (Column V)**
  ```excel
  =[@[Street Address]] & " -" & [@Zipcode]

- **Username Generation (Column W)**
  ```excel
  =LEFT([@[First Name]],3) & LEFT([@[Last Name]],3) & [@Area Code]

- **Formatted Date (Column O)**
  ```excel
  ="(" & DAY([@[Req Date]]) & "," & TEXT([@[Req Date]],"MMMM") & "," & YEAR([@[Req Date]]) & ")"

- **Year Extracted (Column P)**
  ```excel
  =YEAR([@[Req Date]])

<img width="1139" height="661" alt="Screenshot 2025-08-21 at 13 27 29" src="https://github.com/user-attachments/assets/a21580fd-95f8-40ee-a9c3-f160fc417b67" />

