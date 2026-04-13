This webpage presents two visualizations built from the same UFO sightings dataset. The first visualization focuses on how UFO reports change over time, while the second focuses on how reported UFO shapes vary across countries.

## Visualization 1: UFO Sightings Over Time

<iframe src="charts/chart1.html" width="800" height="450" frameborder="0"></iframe>

This visualization shows the number of UFO sightings reported in each year. It is designed to answer how the volume of reported sightings changes over time across the full dataset. By aggregating reports by year, the chart makes it easier to see broad trends in reporting rather than focusing on individual sightings.

For the visual design, I used a line chart because the primary variable of interest is time, and line charts are a natural way to show continuous change across years. The x-axis encodes **year**, and the y-axis encodes the **number of UFO sightings** in that year. I also included points along the line so that individual yearly values are easier to inspect. I did not use a categorical color scheme in this chart because the visualization is focused on one aggregated trend rather than comparing multiple categories, so keeping the figure visually simple makes the trend easier to read.

To prepare the data for this chart, I read the UFO dataset directly from the provided URL in the notebook. Then I parsed the raw `datetime` field into a proper datetime format and extracted the `year` as a new variable. After that, I grouped the dataset by year and counted the number of sightings in each year. These transformations were necessary because the original dataset is stored at the level of individual sightings rather than yearly summaries.

## Visualization 2: Most Common UFO Shapes by Country

<iframe src="charts/chart2.html" width="800" height="500" frameborder="0"></iframe>

This visualization shows the most common reported UFO shapes for a selected country. It is designed to answer among reports from a given country, which UFO shapes appear most often. The chart summarizes the relative frequency of different reported shapes and allows the viewer to compare how common each one is within the currently selected country.

For the design, I used a horizontal bar chart because bar charts are effective for comparing counts across discrete categories. In this plot, the x-axis encodes the **number of sightings**, and the y-axis encodes **UFO shape** as a categorical variable. I used color to distinguish the different shape categories, which helps separate the bars visually and makes the ranking easier to scan. Because there are many possible shape values in the raw data, I restricted the display to the most common shapes so that the figure would remain readable and not become cluttered with rare categories.

To transform the data for this chart, I first cleaned text fields such as `country` and `shape` by trimming whitespace and converting them to lowercase so that categories would be grouped consistently. I then counted the frequency of each reported shape and kept only the most common categories for display. This step was important because the raw dataset contains many shape labels, and including all of them would make the chart harder to interpret.

## Interactivity

The second visualization includes interaction in two ways. First, it provides a dropdown menu that allows the user to select a country, which updates the chart to display only sightings from that country. Second, it includes hover highlighting so that when the user moves the cursor over one bar, that bar is emphasized while the others fade into the background. This interaction changes both the subset of data being displayed and the visual emphasis within the chart. The country dropdown supports direct comparison of shape distributions across countries without forcing all countries into the same crowded chart. The hover highlighting also helps the viewer focus on one category at a time while still preserving the overall ranking context. Together, these choices make the chart feel more exploratory and easier to read than a static version.

## Data Source

- [The Data](https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/ufo-scrubbed-geocoded-time-standardized-00.csv)

## Analysis Notebook

- [The Analysis](https://github.com/kclung99/is445-hw5/blob/main/notebooks/is445_hw5.ipynb)