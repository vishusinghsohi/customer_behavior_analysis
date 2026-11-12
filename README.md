# Customer Shopping Behavior Analysis

## What this project does

This project looks at **3,900 customer purchases** to help a retailer understand what customers buy and how they shop. It uses Python to prepare the data, PostgreSQL to answer business questions, and Power BI to show results in an interactive dashboard. A report and presentation summarize the findings.

**Main question:** How can a retailer use purchase data to improve customer engagement and make better marketing and product decisions?

## What the data contains

The source file, `customer_shopping_behavior.csv`, has 3,900 rows and 18 columns. Each row represents a purchase. The columns describe:

- The customer: age, gender, location, and subscription status
- The purchase: item, category, amount, season, size, and color
- The shopping experience: discount use, previous purchases, purchase frequency, rating, shipping type, and payment method

There are **37 missing review ratings**. The project fills them using the median rating for the product category. It also standardizes column names, removes a duplicate promotion field after checking it against the discount field, and adds age-group and purchase-frequency features.

> Check the dataset’s license and attribution requirements before sharing or redistributing the source data.

## What the project includes

1. **Prepare the data** in a Jupyter notebook using Python and Pandas.
2. **Store the cleaned data** in a PostgreSQL database table named `customer`.
3. **Analyze customer behavior** with SQL, including spending, discounts, ratings, shipping, subscriptions, repeat purchases, and popular products.
4. **Explore the results** in an interactive Power BI dashboard.
5. **Share recommendations** in the PDF report and presentation.

The report recommends promoting subscriber benefits, rewarding repeat purchases, reviewing discount performance, featuring well-rated popular products, and tailoring marketing to customer groups and shipping preferences. See the report and dashboard for details; this README does not list verified numerical findings.

## Project files

| File | What it is for |
| --- | --- |
| `customer_shopping_behavior.csv` | Original purchase data |
| `Customer_Shopping_Behavior_Analysis.ipynb` | Data inspection, cleaning, feature creation, and database loading |
| `customer_behavior_sql_queries.sql` | SQL questions and analysis queries |
| `Customer_Behavior_Dashboard.pbix` | Interactive Power BI dashboard |
| `Customer Shopping Behavior Analysis.pdf` | Written analysis and recommendations |
| `Customer_Shopping_Behavior.pptx` | Stakeholder presentation |
| `Business Problem  Document.pdf` | Project question and requirements |

## Run the analysis

### 1. Install Python packages

Create a virtual environment, activate it, and install the packages:

```bash
python -m venv .venv
```

macOS or Linux:

```bash
source .venv/bin/activate
```

Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

Then install the required packages:

```bash
pip install pandas sqlalchemy psycopg2-binary jupyter
```

### 2. Add the data and open the notebook

Put `customer_shopping_behavior.csv` in your working folder. The notebook currently uses a computer-specific file path, so update that path if needed.

Start Jupyter:

```bash
jupyter notebook
```

Open `Customer_Shopping_Behavior_Analysis.ipynb` and run the cells in order.

### 3. Set up PostgreSQL

Install and start PostgreSQL, then create a database called `customer_behavior` (or update the notebook’s connection settings). Set your own database username, password, host, and port. Keep passwords out of the notebook and source control; use environment variables or a local configuration file that is not committed.

The notebook writes the prepared data to a table called `customer`. Once it finishes, run `customer_behavior_sql_queries.sql` in pgAdmin’s Query Tool or with `psql`.

### 4. Open the dashboard

Open `Customer_Behavior_Dashboard.pbix` in Power BI Desktop. If Power BI asks for a PostgreSQL connection, update the data source settings and refresh the dashboard.

### 5. Read the results

Open the PDF report for the written analysis and recommendations. Use the presentation for a shorter stakeholder summary.

## Important limits

This dataset has no purchase dates, so it cannot show changes over time. The analysis describes patterns in the available records; it does not prove that one factor caused another. Interpret results within the limits of the dataset and its fields.
