# 🚗 Car Rental Data Warehouse & Business Intelligence

## 📋 Project Overview

This repository contains the complete implementation of a **Data Warehousing and Business Intelligence** solution for a **Car Rental Management System**, developed as part of the IT3021 module at Sri Lanka Institute of Information Technology (SLIIT).

| Detail | Information |
|--------|-------------|
| **Student** | L. G. Piyumi Bhagya Rajasekara |
| **Module** | IT3021 - Data Warehousing and Business Intelligence |
| **Academic Year** | Year 3, Semester 1 - 2026 |
| **Institution** | Sri Lanka Institute of Information Technology (SLIIT) |

---

## 📁 Repository Structure

```
car-rental-dwbi/
│
├── 📂 DataWarehouse/
│   ├── CarRentalSSIS/
│   │   ├── CarRental_Load_Staging.dtsx      # SSIS: Load Staging
│   │   ├── CarRental_Load_DW.dtsx           # SSIS: Load Data Warehouse
│   │   ├── CarRental_Update_AccumFact.dtsx  # SSIS: Update Accumulating Fact
│   │   ├── Data_Profiling.dtsx              # SSIS: Data Profiling
│   │   ├── CarRentalSSIS.dtproj             # SSIS Project file
│   │   └── Project.params                   # Project parameters
│   └── README.md
│       ⚠️ Note: Database backup (.bak) not included due to file size.
│
├── 📂 CubeProject/
│   ├── CarRental_SSAS.slnx                  # Visual Studio Solution
│   └── CarRental_SSAS/
│       ├── Cube_CarRental.cube              # SSAS Cube definition
│       ├── Cube_CarRental.partitions        # Cube partitions
│       ├── Dim Branch.dim                   # Branch dimension
│       ├── Dim Customer.dim                 # Customer dimension
│       ├── Dim Date.dim                     # Date dimension
│       ├── Dim Insurance.dim                # Insurance dimension
│       ├── Dim Staff.dim                    # Staff dimension
│       ├── Dim Vehicle.dim                  # Vehicle dimension
│       ├── DimEndDate.dim                   # End Date dimension
│       ├── DS_CarRental_DW.ds               # Data Source
│       ├── DSV_CarRental_DW.dsv             # Data Source View
│       └── CarRentalSSIS.dtproj             # Project file
│
├── 📂 Excel/
│   └── OLAP_Operations.xlsx                 # Excel OLAP Operations
│
├── 📂 PowerBIReports/
│   └── CarRental_Reports.pbix               # Power BI Reports
│
├── 📂 Documents/
│   ├── Assignment1_Report.pdf               # Assignment 1 Documentation
│   └── Assignment2_Report.pdf               # Assignment 2 Documentation
│
└── README.md
```

---

## 🏗️ Assignment 1 — Data Warehouse

### 📊 Dataset
A **Car Rental Management System** dataset tracking vehicle rentals, customers, branches, staff, and insurance across multiple years.

### ⭐ Data Warehouse Schema — Star Schema

**Fact Table:**
- `FactRental` — Rental transactions with measures: Total Amount LKR, Daily Rate LKR, Rental Duration Days, Fuel Charge LKR, Insurance Fee LKR

**Dimension Tables:**
| Dimension | Description |
|-----------|-------------|
| DimVehicle | Vehicle details — Car Brand, Model, Transmission |
| DimCustomer | Customer information — Name, License Type |
| DimDate | Date hierarchy — Year → Quarter → Month → Day |
| DimBranch | Branch details — City, Location |
| DimStaff | Staff information — Role, Branch |
| DimInsurance | Insurance types and coverage |

### 🔄 ETL Pipeline (SSIS)

| Package | Description |
|---------|-------------|
| `CarRental_Load_Staging.dtsx` | Extract data from CSV, Excel, Text sources into staging |
| `CarRental_Load_DW.dtsx` | Transform and load from staging to data warehouse |
| `CarRental_Update_AccumFact.dtsx` | Update accumulating fact table with completion times |
| `Data_Profiling.dtsx` | Data quality profiling |

### 📂 Data Sources (Multiple Types)
- **CSV files** — Rental transactions, Vehicle data, Customer information, Branch and Staff records
- **SQL Server tables** — Staging and reference data

---

## 📊 Assignment 2 — Business Intelligence

### 🧊 SSAS Cube
- **Cube Name:** Cube_CarRental
- **Server:** SQL Server Analysis Services 2022
- **Measures:** Total Amount LKR, Daily Rate LKR, Rental Duration Days, Fuel Charge LKR
- **Dimensions:** 6 dimensions connected to FactRental

**Hierarchies Implemented:**
- 📅 **Date Hierarchy:** Year → Quarter → Month → Day
- 🚗 **Vehicle Hierarchy:** Car Brand → Car Model

### 📈 OLAP Operations (Excel)

| Operation | Description |
|-----------|-------------|
| **Pivot** | Swap Car Brand ↔ Year axes to change data perspective |
| **Roll-Up** | Aggregate quarterly data to yearly summary |
| **Drill-Down** | Expand from Car Brand level to Car Model level |
| **Slice** | Filter data by single dimension — Year 2023 |
| **Dice** | Filter by multiple dimensions — Year 2023 + Toyota |

### 📊 Power BI Reports

| Report | Description |
|--------|-------------|
| **Report 1** | Matrix visual — Car Brand × Year with Total Amount and Rental Count |
| **Report 2** | Cascading slicers — City → Branch filter with multiple charts |
| **Report 3** | Drill-down — Date hierarchy Year → Quarter → Month |
| **Report 4** | Drill-through — Summary page to Vehicle detail page |

🔗 **Published to Power BI Service:** (accessible with authorized Microsoft account).

---

## 🛠️ Technologies Used

- Microsoft SQL Server
- SQL Server Integration Services (SSIS)
- SQL Server Analysis Services (SSAS)
- Microsoft Power BI
- Microsoft Excel
- Visual Studio 2022

---

## ⚠️ Notes

> **Database Backup:** The `.bak` file is not included in this repository due to GitHub file size limitations (file size: ~21MB). The backup is available upon request.

> **Power BI Service:** Reports are published to Power BI Service. Screenshots of online reports are included in the documentation PDF.

---

## 📄 Documentation

Full step-by-step documentation with screenshots is available in the `Documents/` folder:
- Assignment 1 Report — Dataset, Schema Design, ETL Development
- Assignment 2 Report — SSAS Cube, OLAP Operations, Power BI Reports

---

*Sri Lanka Institute of Information Technology — Faculty of Computing*  
*Department of Computer Science — IT3021 Data Warehousing and Business Intelligence*
