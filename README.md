# Tableau Troubleshoot - Preventing auto-concatenation of Dimension Rows or Columns

When more than 50 fields are placed in Columns/Rows, the first 2 fields are grouped, seperated by a comma

Environment
Tableau Desktop 2021.4

Solution:
Step 1: Select Analysis > Table Layout > Advanced
Step 2: Adjust the number of rows or columns to 49 (or any number less than 50 so that Step 5 will work properly)
Step 3: Save the workbook as .twb file
Step 4: Open this xml file in notepad
Step 5: Search for 'col-level' and change the value.
        </style-rule>
          <style-rule element='table'>
            <format attr='col-levels' value='60' />
            <format attr='row-levels' value='60' />
            <format attr='row-horiz-levels' value='60' />
            <format attr='background-color' value='#e6e6e6' />
            <format attr='band-size' scope='rows' value='1' />
            <format attr='band-size' scope='cols' value='1' />
          </style-rule>
