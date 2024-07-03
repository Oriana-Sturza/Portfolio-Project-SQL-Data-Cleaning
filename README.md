PROJECT OVERVIEW:

Standardizing Date Formats: I began by ensuring consistency in the SaleDate column across the dataset. Using SQL's CONVERT() function, I transformed SaleDate into a standardized Date format, essential for uniformity in date handling across different operations and queries. To ensure data integrity and provide a fallback option in case of issues with the conversion process, I also added a new column named SaleDateConverted, which stored the converted date values.

Populating Missing Property Addresses: Another crucial aspect of the project involved addressing missing PropertyAddress data. Using SQL joins and conditional logic (ISNULL() function), I identified records where PropertyAddress was null. By leveraging self-joins on the ParcelID and UniqueID columns, I systematically populated these missing addresses from related records within the same dataset. This approach not only filled in gaps but also maintained relational integrity within the dataset, ensuring each property record had a complete address.

Address Parsing and Segmentation: I undertook the task of breaking down complex address fields (PropertyAddress and OwnerAddress) into distinct components—namely, Address, City, and State. This required careful use of SQL string functions (SUBSTRING(), CHARINDEX()) and data parsing techniques (PARSENAME()) to extract and separate relevant parts of the address data. By creating additional columns (PropertySplitAddress, PropertySplitCity, OwnerSplitAddress, OwnerSplitCity, OwnerSplitState) and populating them with parsed values, I enhanced the granularity and usability of the address information for analytical purposes.

Categorical Data Transformation: To enhance clarity and consistency in the dataset, I tackled the transformation of categorical data in the SoldAsVacant field. Using SQL's CASE statement, I mapped 'Y' and 'N' values to more descriptive terms—'Yes' and 'No', respectively. This transformation not only standardized the representation of vacant property status but also facilitated easier interpretation and reporting of this crucial attribute.

Duplicate Management: Addressing duplicate records was another significant challenge. I utilized a Common Table Expression (CTE) combined with the ROW_NUMBER() function to identify and subsequently remove duplicate entries based on key fields (ParcelID, PropertyAddress, SalePrice, SaleDate, LegalReference). This approach allowed me to retain only unique records while ensuring data integrity and eliminating redundancy in the dataset.

Optimizing Table Structure: As part of the data cleaning process, I optimized the table structure by removing unnecessary columns (OwnerAddress, TaxDistrict, PropertyAddress, SaleDate). This strategic column management not only simplified the dataset but also improved query performance and reduced storage requirements, leading to more efficient data management and analysis.

Problem-Solving Approach:

Throughout the project, my approach was characterized by systematic and structured problem-solving:
Comprehensive Data Handling: I adopted a methodical approach to data cleaning, addressing each aspect—date standardization, missing data population, address parsing, categorical transformation, duplicate management, and column optimization—with careful consideration and attention to detail.

Advanced SQL Techniques: Leveraging advanced SQL techniques such as joins, CTEs, string manipulation functions, and conditional statements, I effectively managed complex data challenges while maintaining data integrity and relational consistency.

Iterative Improvement: By iteratively refining SQL queries and procedures, I ensured continuous improvement in data quality and usability, aligning the dataset more closely with analytical and reporting requirements.

Challenging Aspect:

One of the most challenging tasks in this project was accurately parsing and segmenting complex address data (PropertyAddress and OwnerAddress) into distinct components (Address, City, State). This involved navigating varying formats and structures within the address data, as well as ensuring that the parsing logic was robust enough to handle different edge cases effectively. By employing a combination of SQL string functions and parsing techniques, I successfully overcame this challenge, enhancing the granularity and usability of address information within the dataset.

