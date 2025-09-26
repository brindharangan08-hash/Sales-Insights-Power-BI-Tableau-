# INSTRUCTIONS — Upload & Open (Power BI Web / Power BI Desktop / Tableau Public)

## Option A — Power BI Web (ready for upload)
1. Go to app.powerbi.com and sign in (or create a free account).
2. Click **Create > Upload a file > Local file** and upload `orders.csv`. Repeat to upload the other CSVs.
3. In the workspace, go to **Datasets** and click **Create report** on the combined dataset (you can merge tables in the report editor or transform before).
4. Use the **Model** view to create relationships:
   - orders.CustomerID -> customers.CustomerID
   - orders.ProductID -> products.ProductID
   - orders.OrderDate -> calendar.Date (make sure types align)
5. Create measures (see `DAX_measures.txt`) by clicking the dataset and **New measure**.
6. Build visuals: time series (Sales by OrderDate), bar charts (Top Products), map/treemap by Region, KPI cards, slicers for Category and Year.
7. Save and publish. Use **File > Publish to web** (or publish to a workspace) to share a public link or embed.

## Option B — Power BI Desktop (recommended for full features)
1. Open Power BI Desktop.
2. Get Data > Text/CSV > import `orders.csv`, `products.csv`, `customers.csv`, `calendar.csv`.
3. In Transform Data (Power Query), paste queries from `PowerQuery_M.txt` if needed.
4. Model relationships as above.
5. Create calculated measures using `DAX_measures.txt`.
6. Build the report pages:
   - Overview (KPIs: Total Sales, Profit, Orders, Avg Order Value)
   - Time Analysis (YTD, MoM, Trend)
   - Product & Category (Top products, category share)
   - Customer & Region (Sales by region, customer segmentation)
7. File > Save as `.pbix`. You can then publish to Power BI Service.

## Option C — Tableau Public
1. Open Tableau Public (free) or Tableau Desktop.
2. Connect > Text File > choose `orders.csv`, then use Add > Text File to add `products.csv` and `customers.csv`.
3. Define joins:
   - orders.ProductID = products.ProductID
   - orders.CustomerID = customers.CustomerID
4. Create calculated fields similar to the DAX measures (see `DAX_measures.txt` for logic).
5. Build dashboards: use sheets for charts and then combine into a Dashboard.
6. File > Save to Tableau Public to publish.

## What's ready-to-upload
All CSVs and instruction files in this repo are ready to push to GitHub. You can also create a quick `index.html` screenshot or `report.pbix` (if using Desktop) and add it to the repo.
