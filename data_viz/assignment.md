## Visualizations

### Plot 1: Bar Chart of License Counts by Type

**Overview:**  
The first visualization is a bar chart that offers a clear, straightforward comparison of how many licenses are issued for each License Type found in the dataset. This plot gives viewers an immediate understanding of which license types are more prevalent by displaying the count of each category as a distinct bar.

**Detailed Description:**

- **What’s Being Visualized:**  
  In this bar chart, each bar represents a different License Type present in the dataset. The height of each bar corresponds directly to the number of occurrences (or rows) associated with that License Type. This provides a quick visual ranking – from the most common license types to the least common – making it easy to determine which categories are dominant.

- **Encodings:**  
  - **X-axis:** Encodes the `License Type`, thereby mapping categorical data along a horizontal line.
  - **Y-axis:** Encodes the count of records for each License Type using the aggregation function `count()`.
  
  By directly mapping license types to these axes, the chart facilitates an immediate comparison of license frequencies.

- **Color Choices:**  
  Each bar is assigned a unique color based on its License Type. Utilizing Altair’s built-in color palette not only simplifies the design process but also ensures that even when bars are of similar heights, the distinct colors help differentiate between them visually. This careful color-coding supports the viewer in quickly distinguishing and comparing the various license categories.

- **Data Transformations:**  
  Before visualization, the data undergoes necessary cleaning steps. Specifically:
  - Rows missing the “Original Issue Date” or “License Type” are removed.
  - This filtering step ensures accuracy and prevents any misrepresentation in the aggregated counts.
  
  No further transformations are required because the purpose of this chart is merely to display a straightforward count of each license category.

---

### Plot 2: Interactive Monthly License Trends

**Overview:**  
The second visualization is an interactive time-series line chart that dives deeper into the trends of license issuance over time. It displays how many licenses were issued each month while allowing users to filter the data dynamically by License Type. This interactive feature makes it possible to isolate and scrutinize the issuance patterns specific to any one category.

**Detailed Description:**

- **What’s Being Visualized:**  
  This plot reveals the monthly evolution of license issuance. The x-axis represents time segmented by month (derived from the “Original Issue Date”), and the y-axis shows the count of licenses issued in each corresponding month. By presenting data as a continuous series, the chart exposes potential trends such as spikes in license issuance during particular months, seasonal fluctuations, or steady trends over the period analyzed.

- **Encodings:**  
  - **X-axis:** Encodes the month extracted from the “Original Issue Date”. The date information is transformed into a “year-month” format to create a coherent timeline.
  - **Y-axis:** Encodes the aggregated count of licenses issued in each month.
  - **Color & Points:**  
    The currently selected License Type is highlighted via a distinct color. Moreover, individual data points on the line help to emphasize the exact count for each month, adding granularity to the overall trend display.

- **Data Transformations:**  
  - The “Original Issue Date” field is first converted into a datetime format.
  - A new column, `Month`, is then created by extracting the year and month from this datetime.
  - Following the data cleaning step (removing rows with missing values), the data is aggregated by both License Type and Month to compute the monthly issuance counts.

- **Interactivity:**  
  This visualization is made dynamic by incorporating an Altair dropdown menu. Users can select a specific License Type from the dropdown, which filters the data to display only the monthly trends associated with that category. This interactive feature allows:
  - A focused examination of one license category at a time without overlaying multiple data series, thereby avoiding visual clutter.
  - Quick comparisons and the opportunity to identify any sudden spikes or consistent patterns within that license category over time.

---

- **The Data:** [licenses_fall2022.csv](https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/licenses_fall2022.csv)  
- **The Analysis:** [View Notebook Here](https://github.com/trisharane/trisharane.github.io/blob/main/data_viz/Homework5.ipynb
)
