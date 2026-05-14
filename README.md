# Overview
The following project demonstrates detailed steps how data can be cleaned in Excel in different ways.
The following Excel file contains sample employee dataset that is unclean.
It moves from basic manual techniques to advanced automated workflows to demonstrate real-world fixes.

# Types
## Manual
- Flash Fill
- Text to Columns
- Remove Duplicates

## Automated
- Formulas
- Power Query

## Issues in excel file
1. Several blank values in gender column.
2. Department has incorrect values as null.
3. Format in date column is messed up.
4. Location details are messed up.

## Data Cleaning using Flash Fill
- To get first name
  1. Create a new column at the end named as First Name and start typing the first name from Name column.
  2. When you type the 2nd value excel predicts the rest of the first names.
  3. On pressing enter all first names will be entered in excel automatically.

- To get just the city name alone
  1. Create a new column named City and start typing the city names.
  2. Flash predicts all city names, but for remote location as name its incorrect, which is a limitation.

## Data Cleaning using Text to columns
- To get just the city name alone
  1. Select the location column using Ctrl+Shift+Down_Arrow_Key, then go to Data ribbon – Text to column.
  2. On clicking, you get this, select Delimited and Click next, select comma and remove Tab and click on next, leave it at General and click Finish.
  3. The work location is split into 2 columns

- Splitting cost centre & ID number
  1. Take copy of employee ids, put it on new sheet and select Data – Text to columns
  2. Changed to fixed width and click next, when excel askes which are the fixed bits, point at first two chars, the header also gets split, then set it to text data type so leading zeros are preserved when data goes into excel.
  3. On finish, this is the employee ID is split into Cost Centre which is initial 2 alphabets and employee ID. 

## Data Cleaning using Removing Duplicates
- Duplicate values  in Name and Employee ID Column
  1. For searching for duplicates, sort the name column and check.
  2. From Data – Remove Duplicates function
  3. Start by selecting all data, select Remove duplicates and unselect everything and only select EmpID as its unique.
  4. It will remove duplicates on clicking OK.

## Data Cleaning using Formulas
- Remove extra spaces from name
  1. Some names have an extra space at the beginning.
  2. Create a new column as Clean Name and use the TRIM function =trim(column_name)
  3. It will give names without extra spaces.

- Based on FTE, whether employee is Full time or Part time
  1. In this case, IF function can be used, =IF(column_name<1,"Part time","Full time")
  2. When formula is copy pasted down, the column will display jobs as Full time and Part according to FTE duration where if its less than 1 then Part time else its full time.

## Data Cleaning using Power Query
  1. Data is copy pasted into a new sheet.
  2. This sheet has to be loaded into Power Query, for that all data needs to be selected.
  3. Data ribbon – From within excel sheet

- Splitting Cost Centre & ID
  1. Right Click on Emp ID.
  2. Split Column – By Numbers of Characters.
  3. On clicking OK, will get both parts of Employee ID.
  4. Rename both the Columns as Cost centre and other as Employee ID.

- Fixing inconsistent dates
  1. Right click on Date column – Change Type - Date.
  2. Date is sorted.
  3. If date is of more complicated type (from different geography and hence different arrangement), right click on start date – Change type – Use Locale.

- Adding a Full / Part column
  1. Go to Add Column Ribbon – Conditional Column.
  2. Specify the condition - New Column name: Full/Part, If Column name: FTE, Operator: equals, Value: 1, Output: Full time, Else: Part time.
  3. On clicking OK, new column with Full time and Part time Data is displayed.

- Fixing or Removing incomplete data
  1. Gender column has missing values and Department column has Null values.
  2. Right click on Gender Column – Replace Values
  3. Replace value to find: null with Condition: Other. So anytime it finds a 'Null', it will replace with 'Other'.
  4. For removing null from department, click on the downward arrow button and Uncheck the NULL and all Null values are removed.
  5. Now go to Home – Close and Load.
  6. It will add a new table in a new worksheet with the cleaned data which is further used for Analysis.

### When new data is added, in power query – right click on table – refresh and all latest data is added too.
