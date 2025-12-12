Import Required Libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

2️⃣ Reading CSV Files (LOTR Datasets)
df1 = pd.read_csv(r"C:\Users\ATCHAYA\Desktop\PYTHON\PANDAS\LOTR.csv")
df2 = pd.read_csv(r"C:\Users\ATCHAYA\Desktop\PYTHON\PANDAS\LOTR 2.csv")

df1
df2

3️⃣ Merging DataFrames (SQL-style Joins)
# Default merge
df1.merge(df2)

# Inner join
df1.merge(df2, how='inner')

# Inner join on specific column
df1.merge(df2, how='inner', on='FellowshipID')

# Inner join on multiple columns
df1.merge(df2, how='inner', on=['FellowshipID', 'FirstName'])

# Outer join
df1.merge(df2, how='outer', on='FellowshipID')

# Left join
df1.merge(df2, how='left', on='FellowshipID')

# Right join
df1.merge(df2, how='right', on='FellowshipID')

# Cross join
df1.merge(df2, how='cross')

4️⃣ Join Using Index
df4 = df1.set_index('FellowshipID').join(
    df2.set_index('FellowshipID'),
    how='outer',
    lsuffix='_Left',
    rsuffix='_Right'
)

df4

5️⃣ Concatenation
# Column-wise concat
pd.concat([df1, df2], axis=1, join='outer')

# Row-wise concat
pd.concat([df1, df2], axis=0, ignore_index=True)

🍦 Ice Cream Ratings – Visualization
6️⃣ Read CSV and Set Date Index
df = pd.read_csv(r"C:\Users\ATCHAYA\Desktop\PYTHON\PANDAS\Ice Cream Ratings.csv")
df['Date'] = pd.to_datetime(df['Date'])
df = df.set_index('Date')

df

7️⃣ Line & Bar Charts
df.plot()
plt.show()

df.plot(kind='bar')
plt.show()

df.plot(kind='bar', subplots=True)
plt.show()

8️⃣ Scatter, Histogram & Boxplot
df.plot.scatter(x='Texture Rating', y='Overall Rating', s=500, c='green')
plt.show()

df.plot.hist(bins=10)
plt.show()

df.plot.hist(bins=15)
plt.show()

df.boxplot()
plt.show()

9️⃣ Area Charts
df.plot.area(figsize=(10,5))
plt.show()

df.plot.area(figsize=(10,5), cmap='Reds')
plt.show()

df.plot.area(figsize=(10,5), cmap='Oranges')
plt.show()

🔟 Pie Charts
df.plot.pie(y='Flavor Rating', figsize=(10,10))
plt.show()

df.plot.pie(y='Flavor Rating', figsize=(10,10), cmap='Blues')
plt.show()

📞 Customer Call List – Data Cleaning
1️⃣1️⃣ Read Excel File
df = pd.read_excel(r"C:\Users\ATCHAYA\Desktop\PYTHON\PANDAS\Customer Call List.xlsx")
df

1️⃣2️⃣ Remove Duplicates & Unwanted Columns
df = df.drop_duplicates()
df = df.drop(columns='Not_Useful_Column')

df

1️⃣3️⃣ Clean Last Name Column
df['Last_Name'] = df['Last_Name'].astype(str).str.strip("123._/")
df

1️⃣4️⃣ Clean Phone Number Column
df['Phone_Number'] = df['Phone_Number'].astype(str)
df['Phone_Number'] = df['Phone_Number'].str.replace('nan--', '', regex=False)
df['Phone_Number'] = df['Phone_Number'].str.replace('Na--', '', regex=False)

df

1️⃣5️⃣ Split Address into Columns
df[['Street_Address', 'State', 'Zip_Code']] = df['Address'].str.split(',', n=2, expand=True)
df

1️⃣6️⃣ Standardize Do Not Contact Column
df['Do_Not_Contact'] = df['Do_Not_Contact'].replace({'Yes': 'Y', 'No': 'N'})
df = df.fillna('')
df

1️⃣7️⃣ Remove Unwanted Rows
df = df[df['Do_Not_Contact'] != 'Y']
df = df[df['Phone_Number'] != '']
df = df.reset_index(drop=True)

df

1️⃣8️⃣ Save Cleaned File (Optional)
df.to_csv('Customer_Call_List_Cleaned.csv', index=False)
