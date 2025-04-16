# License Visualizations

Welcome to my license visualizations.

## Bar Chart of License Types

This chart shows the number of licenses issued for each License Type.

![License Type Chart](chart1.html)

In my first visualization, I created a bar chart that displays the number of licenses issued for each License Type. For my x-axis, I encoded the nominal field License Type. For my y-axis, I used a quantitative count aggregation (count()). This allowed me to show how many records fall into each category. For my design, I chose to color each bar by License Type using Altair’s default categorical color scheme. This way, observers can tell each license type apar,t and it is easy to compare at a glance.

For my analysis, I did not filter out any rows and performed a group transformation. The only way I manipulated my data for this plot was the implicit aggregation performed by Altair’s count(). The purpose of this chart is to provide an overview of which licenses are most and least common. This visualization could be used by administrators to see where to focus outreach, training, or renewal reminders.

## Interactive License Type Chart

Click below to view the interactive chart.

[Interactive License Type Chart](chart2.html)

For the second plot, I built an interactive line chart showing how the number of licenses issued changes across years for different license types.

First, transformed the "Original Issue Date column" using:

df['Original Issue Date'] = pd.to_datetime(df['Original Issue Date'])

and

df['Year'] = df['Original Issue Date'].dt.year.

This allowed me to extract the Year field, then I grouped by Year and License Type to compute counts. I encoded x='Year:T' (temporal) and y='count():Q' (quantitative). I used color='License Type:N' so each line has a distinct color, like my last plot had.

For interactivity, I added a dropdown selector for License Type allowing the user to choose which license type’s trend line they want to look at. This aids in reducing clutter by showing only the selected line. This makes it easier to focus on the evolution of a single license category without losing context of the overall dataset.

This plot is helpful because it helps identify any trends in license types over the years. It's simple to spot unusual spikes or recurring patterns. Additionally, if a particular license type shows steady growth year‑over‑year, the department can plan for increased processing capacity or put aside more resources for that license type.





## [The Data](https://github.com/arosedale/arosedale.github.io/raw/main/hw_5.csv)
Link to the data file used in the analysis.

## [The Analysis](https://github.com/arosedale/arosedale.github.io/blob/main/license_visualizations.ipynb)
Link to the Jupyter notebook used for the analysis.
