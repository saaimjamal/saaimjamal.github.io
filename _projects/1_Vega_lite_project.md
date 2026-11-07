---
name: Vega Lite Example Project
tools: [Python, HTML, vega-lite]
image: assets/pngs/cars.png
description: This is a "showcase" project that uses vega-lite for interactive viz!
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Business Licenses Data Visualizations

## Visualization 1: Top 10 Most Common License Types

<vegachart schema-url="{{ site.baseurl }}/assets/json/viz_1.json" style="width: 100%"></vegachart>

For my first visualization, I used the Business Licenses dataset. I created a horizontal bar chart which showcases the top ten most common license types found in the dataset. Horizontal bars improves the readability of the chart because it provides extra room in the margine for the license types with longer names. Additionally, I sorted each license type in ascending order with the top bar being the most common license type and the bottom bar being the least common license type. The x-axis (Number of Licenses), uses encoding type Q (Quantitative) because it is dealing with numerical data. The y-axis (License Type) uses encoding type N (Nominal), because we are dealing with categorical data. For this visualization I did not use a color scheme because the axis labels and titles were enough to explain the bar graph. I chose to stay with the standard blue color for all the bars because adding more colors would complicate the graph as they wouldn't be representative of any new variable. For this bar chart, I performed four data transformations. First, I used value_counts() to see how many records there were for each license type. Then I used head(10) so that the chart only displays the top 10 most common license types. After the records were counted, I used reset_index() to convert those results into a dataframe. Finally, I used columns = ["License Type", "Count"] to rename the columns into a more clear name.

## Visualization 2: License Status by License Type

<vegachart schema-url="{{ site.baseurl }}/assets/json/viz_2.json" style="width: 100%"></vegachart>

For my second visualization, I used the same Business Licenses dataset. I created a heatmap which showcases the number of every license type and license status combo in the dataset. Heat map was the best option because it makes it easy to see and compare different combinations of license types and license statuses in our dataset. Additionally, the color-coded cells makes it easy for the viewer to identify how many instances a combo occured in the dataset. The x-axis (License Status) and the y-axis (License Type), both use encoding type N (Nominal) because they involve categorical data. The colors of the cells in the heatmap use encoding type Q (Quantitative) because it measures the number of liceses which is numerical data. I am coloring by the "Count" varibale where a low number or licenses has a light pale green cell color and a cell representing a higher number of licenses will have a darker blue shade. I chose this color gradient scheme becuse it helps the person looking at the heatmap have an easier time identifying with license type-status combos have the highest count. As for the data transformations, I began by using groupby() to group the dataset by each unique license type and status combination. Then I used size() to count how many licenses belong to each combination. Lastly, I used the reset_index(name = "Count) to convert the license count into a a dataframe.

## Interactivity

For my first visualization, I used an interactive tooltips that displays the license type and count when the user hovers over a bar. This helps makes my visualization more clear because the user can see the direct number of licenses rather than having to estimate based off where the bar seems to end relative to the x-axis. For my second visualization, I added a dropdown that focuses on one specific license type selected by the user. This makes my heatmap more clear because there is less clutter since the user can focus on one license type rather than having to see all of them at once.

## The Data & Analysis

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/licenses_fall2022.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/saaimjamal/saaimjamal.github.io/blob/main/python_notebooks/HW5_Business_Licenses.ipynb" text="The Analysis" %}
</div>
