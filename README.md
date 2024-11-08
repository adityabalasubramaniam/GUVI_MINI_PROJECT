
# Census Data Standardization and Analysis Pipeline

This project provides a comprehensive pipeline for cleaning, processing, and analyzing census data, focusing on standardizing data for accurate insights and enabling data visualization.

## Technologies Used
- **Python**: Data processing, cleaning, and transformation
- **SQL**: Relational database for storing and querying data
- **MongoDB**: NoSQL database for initial data storage
- **Streamlit**: Dashboard for data visualization

---

## Project Workflow and Execution

### Phase 1: Initial Setup and Data Extraction

1. **Set Up the Environment**
   - **Install Required Libraries**:
     Ensure the following libraries are installed: `pandas`, `sqlalchemy`, `pymongo`, `streamlit`, `os`, and `numpy`.
   - **Configure Database Connections**:
     Set up connections to both MongoDB and an SQL database using MongoDB URI and SQLAlchemy connection strings.

2. **Extract Data**
   - **Load Dataset**: Download or connect to the dataset URL and load it into a Pandas DataFrame.
   - **Load Additional Files**:
     Load auxiliary files such as Telangana district list (`Telangana.txt`) and any other mappings or required external data.

---

### Phase 2: Data Cleaning and Transformation

#### Task 1: Rename Column Names
- **Execution**:
  - Create a dictionary mapping old column names to new names (e.g., `{"State name": "State/UT", ...}`).
  - Use Pandas `rename()` function to update column names in the DataFrame.
- **Validation**:
  - Print column names to confirm that the renaming was successful.

#### Task 2: Standardize State/UT Names
- **Execution**:
  - Apply a function to format State/UT names with title casing, ensuring words like “and” remain lowercase.
- **Validation**:
  - Check unique values in the State/UT column to verify correct formatting.

#### Task 3: New State/UT Formation
- **Execution**:
  - Load Telangana districts from `Telangana.txt` and update the State/UT from "Andhra Pradesh" to "Telangana" for matching districts.
  - Change "Leh" and "Kargil" districts from "Jammu and Kashmir" to "Ladakh".
- **Validation**:
  - List affected districts to confirm the correct State/UT assignments.

---

### Phase 3: Handle Missing Data

#### Task 4: Calculate and Fill Missing Data
- **Execution**:
  - Calculate missing data percentages for each column.
  - Fill missing data based on relationships, e.g., `Population = Male + Female`.
  - Log and compare missing data before and after filling.
- **Validation**:
  - Print a summary of missing data before and after filling to verify completeness.

---

### Phase 4: Data Storage in MongoDB

#### Task 5: Save Processed Data to MongoDB
- **Execution**:
  - Convert the DataFrame to a dictionary format and insert it into MongoDB in a collection named `census`.
- **Validation**:
  - Query MongoDB to confirm successful data insertion and correct structure.

---

### Phase 5: Data Migration to SQL Database

#### Task 6: Load Data from MongoDB to SQL Database
- **Execution**:
  - Retrieve data from MongoDB and insert it into SQL database tables, with table names matching the file names (excluding extensions).
  - Define primary and foreign keys according to the data schema.
- **Validation**:
  - Verify SQL tables by running queries to ensure data integrity and relationships.

---

### Phase 6: Data Analysis and Visualization with Streamlit

#### Task 7: Query and Display Data in Streamlit
- **Execution**:
  - **Write SQL Queries**: Define queries for each analysis, such as total population per district, literacy rates, and household characteristics.
  - **Implement Streamlit Dashboard**:
    - Create an interactive dashboard with separate sections/tabs for each query.
    - Use tables, charts, and other visuals to display query results.
- **Validation**:
  - Test each query in Streamlit to ensure correct data display and clear visualizations.

---

### Final Output
The final output is displayed in a local Streamlit application running on `localhost`, as shown in the image below


---

## Cloning and Running the Project

### Clone the Project Repository

1. **Copy the Repository URL**:
   - Click the **Code** button in the repository on GitHub, and copy the HTTP URL.

2. **Open the Command Line**:
   - Open the command line by pressing `Win + R`, typing `cmd`, and pressing **Enter**.

3. **Clone the Repository**:
   ```bash
   git clone <repository-url>
   ```
   - This will create a local copy of the repository in a folder with the repository name.

4. **Navigate into the Project Folder**:
   ```bash
   cd <repository-name>
   ```

5. **Open in VS Code**:
   - To open the project in Visual Studio Code, run:
     ```bash
     code .
     ```

---

### Run the Code

1. **Install Dependencies**:
   - Make sure required dependencies are installed by running:
     ```bash
     pip install pandas sqlalchemy pymongo streamlit os numpy
     ```

2. **Install Database Tools**:
   - **MySQL Workbench** and **MongoDB** are required for data storage and retrieval.

3. **Execute the Pipeline**:
   - Follow the project workflow to run the pipeline from data extraction through visualization.

---

By following this structured README, you can set up, run, and manage the census data pipeline effectively.

