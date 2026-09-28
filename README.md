Overview:
This document explains how to import data using a spreadsheet and Transform Maps. This method is used to import bulk data safely without manual entry.

Purpose:
To keep business data accurate, updated and relevant. Regular imports prevent data errors and loss of customer trust.

What You Need:
1. An Excel or CSV file with proper data
2. Access to Import Sets
3. A Transform Map

Steps to Import:

Step 1 - Prepare Your Spreadsheet:
Make sure the first row has clear column names like name, email, department.
Remove empty columns and duplicate rows.
Keep date format as YYYY-MM-DD.

Step 2 - Create Data Source:
Go to System Import Sets, then Administration, then Data Sources.
Create a new Data Source and upload your spreadsheet file.
This will create a temporary import table.

Step 3 - Create Transform Map:
Go to System Import Sets and click Create Transform Map.
Select your temporary import table as Source Table.
Select your final table as Target Table, for example sys_user or cmdb_ci.

Step 4 - Map the Fields:
Map each column from your spreadsheet to the correct field in the target table.
Example: user_name in sheet maps to user_name in target.
Set Coalesce as true for unique fields like email or user_name to avoid duplicates.

Step 5 - Load and Transform:
First use Test Load with 20 records to check for errors.
If there are no errors, Load All Records.
Then click on Transform to move data to the final table.

Step 6 - Check Results:
Check Transform History to see how many records were inserted or updated.
Check Import Log for any errors.
Check the final target table to confirm the data.

Common Problems and Solutions:
If you get Invalid Insert error, check if mandatory fields are empty.
If you get Reference field error, check if the referenced record exists.
If you get Choice value error, make sure the value matches exactly.
If duplicate records are created, check your coalesce field.

Best Practices:
Always test with few records first.
Always use a temporary import table, never import directly.
Always set a coalesce field.
Take a backup of target table before bulk import.
Keep your field mapping documented.

This process can be used for any table like Users, Assets, CI, Incidents.
