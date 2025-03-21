# Parks and Recreation Database ETL Project

## Overview

This project involves the extraction, transformation, and loading (ETL) of data from a MySQL database for the Parks and Recreation department. The goal is to create a streamlined process for handling and analyzing employee data, including salary and demographics information.

## Project Structure

```
Parks_and_recreation DB/
    .vscode/
        settings.json
    ETL/
        Extracting.ipynb
        MySQL Database.session.sql
        Transformations.ipynb
```

- **.vscode/**: Contains configuration files for Visual Studio Code.
- **ETL/**: Contains Jupyter notebooks and SQL session files for the ETL process.
  - **Extracting.ipynb**: Notebook for extracting data from the MySQL database.
  - **MySQL Database.session.sql**: SQL session file for database interactions.
  - **Transformations.ipynb**: Notebook for transforming the extracted data.

## Data Extraction

The data extraction process is handled in the `Extracting.ipynb` notebook. This notebook connects to the MySQL database, executes SQL queries to retrieve employee salary and demographics data, and loads the results into Pandas DataFrames for further processing.

### Extracting.ipynb

```python
import mysql.connector
import pandas as pd

# Establish connection to MySQL
conn = mysql.connector.connect(
    host='localhost',
    user='root',
    password='Dennyd4116$',  # Leave blank if no password is set
    database='parks_and_recreation'
)

# Define the query
query_1 = "SELECT * FROM employee_salary"
query_2 = "SELECT * FROM employee_demographics"

# Load data into a DataFrame
df_1 = pd.read_sql(query_1, conn)
df_2 = pd.read_sql(query_2, conn)

# Close the connection
conn.close()

# Display the DataFrame
print(df_1, df_2)
```

## Data Transformation

The transformation process is handled in the `Transformations.ipynb` notebook. This notebook will include steps to clean, normalize, and enrich the extracted data to prepare it for analysis.

## Data Loading

The final step of the ETL process involves loading the transformed data into a target data store, which could be another database, a data warehouse, or a file system for further analysis.

## Getting Started

To get started with this project, follow these steps:

1. Clone the repository to your local machine.
2. Install the required dependencies.
3. Set up the MySQL database and ensure it is running.
4. Open the `Extracting.ipynb` notebook in Jupyter and run the cells to extract data.
5. Open the `Transformations.ipynb` notebook and perform the necessary transformations.
6. Load the transformed data into the target data store.

## Dependencies

- Python 3.x
- Jupyter Notebook
- MySQL Connector
- Pandas

## Contributing

Contributions are welcome! Please feel free to submit a pull request or open an issue if you have any suggestions or improvements.

## License

This project is licensed under the MIT License.
