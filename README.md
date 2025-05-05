# 🚀 Data Ingestion and Transformation with Microsoft Fabric Lakehouse

This project demonstrates how to use **Microsoft Fabric** to create a Lakehouse, ingest data from an external source via a pipeline, and transform it using a Spark notebook.

## 🧰 Technologies Used

- **Microsoft Fabric** (Trial required)
- **Lakehouse**
- **Pipelines (ETL/ELT)**
- **Apache Spark**
- **PySpark**
- **Delta Tables**

---

## 📌 Steps Overview

### 1. Create a Workspace
Navigate to [Microsoft Fabric](https://app.fabric.microsoft.com/) and create a new workspace with Fabric capacity enabled.

### 2. Create a Lakehouse
In the workspace, create a new Lakehouse. Under the `Files` node, create a subfolder called `new_data`.

### 3. Create a Pipeline and Ingest Data
- Create a pipeline named `Ingest Sales Data`.
- Use the **Copy Data** activity to fetch the CSV file from:  
  `https://raw.githubusercontent.com/MicrosoftLearning/dp-data/main/sales.csv`
- Save the file to: `Files/new_data/sales.csv`

### 4. Create and Configure a Notebook
- Create a Spark notebook.
- Add transformations:
  - Extract `Year` and `Month` from `OrderDate`
  - Split `CustomerName` into `FirstName` and `LastName`
  - Reorder and select relevant columns
- Save the transformed data as a delta table named `sales`.

### 5. Enhance the Pipeline
- Add a **Delete old files** activity to remove existing `.csv` files.
- Add a **Notebook activity** to run the transformation notebook and save data as `new_sales`.
- Link all activities in sequence (Delete → Copy → Notebook).

---

## 📊 Results

After running the pipeline:
- `sales.csv` is stored in the `new_data` folder.
- Two delta tables (`sales`, `new_sales`) are created under the Lakehouse `Tables` section.
- The data is cleaned and structured according to Spark transformation logic.

---

## 🧹 Cleanup (Optional)

If you want to remove the trial environment:
- Go to workspace settings.
- Click **Remove this workspace** and confirm deletion.

---

## 📎 References

- [Microsoft Fabric](https://app.fabric.microsoft.com/)
- [Source CSV File](https://raw.githubusercontent.com/MicrosoftLearning/dp-data/main/sales.csv)

---

## 🧑‍💻 Author

This project is based on hands-on labs from Microsoft Learn for data engineering with Microsoft Fabric.

