1. Data Loading:
   - I began by using Pandas to load the FIFA21 dataset from the CSV file.
   - To get a preliminary perspective, examine the first five rows using `data.head(5)`.
   - To improve comprehension, I used `data.info()` to verify data types and missing values.

2. Columns for Handling:
   - At indices 3, 4, and 18, superfluous columns were removed with the help of `data.drop(data.columns[[3, 4, 18]], axis=1, inplace=True)`.
   - Zeros were used to fill in the missing values in the "Hits" column: `data['Hits'].fillna(0, inplace=True)`.

3. Formatting and Renaming Columns:
   - Used `data=data.rename(columns={'LongName':'FullName'})` to rename the 'LongName' column to 'FullName'.
   - Changed the format of the 'Joined' column to a datetime format ('YYYY-MM-DD').
   - The '↓OVA' column has been renamed to 'OVA'.
   - The 'Club' column's extraneous characters were eliminated.

4. Managing Player Status:
   - 'on_loan' and 'free' columns were added to record certain player statuses.
   - Based on the updated status indicators, modified the 'Status' column.

5. Rearranging Columns:
   - The columns were rearranged to improve readability.
   - The 'Contract' column format was standardized.
   - The dataset's final three columns were eliminated.

6. Height and Weight Standardization:
    - Converted the columns for height and weight to a single unit (kilograms for weight and centimeters for height).

7. Monetary Values Conversion:
   - Took numeric values in euros for the "Release Clause," "Wage," and "Value" columns.

8. Numeric Consistency:
   - To guarantee consistent numerical representation, star symbols were eliminated from the 'IR', 'SM', and 'W/F' columns.
   - Made certain columns into integers ('Hits', 'W/F', 'SM', 'IR').

9. Sorting and Cleaning Positions:
    - By sorting the positions within each entry alphabetically, I was able to sort and clean the 'Positions' column.

10. Saving the Cleaned Data:
    - Used `data.to_csv('cleaned fifa21.csv')} to save the cleaned dataset to a new CSV file called 'cleaned fifa21.csv'.
