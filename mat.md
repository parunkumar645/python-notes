# Matplotlib Tutorial Notes

## Introduction to Matplotlib

Matplotlib is a powerful Python library used for creating static, animated, and interactive visualizations in Python. It provides an object-oriented API for embedding plots into applications.

### What is Matplotlib?
Matplotlib is a comprehensive library for creating static, animated, and interactive visualizations in Python. It was created by John D. Hunter in 2003 and is built on NumPy arrays.

### Why Use Matplotlib?
- **Versatility**: Creates a wide variety of plots and charts
- **Customization**: Offers extensive control over every element of a figure
- **Integration**: Works well with NumPy and other scientific Python libraries
- **Publication Quality**: Generates high-quality figures suitable for publications
- **Cross-platform**: Works across different operating systems

### Where We Use Matplotlib
- **Data Analysis**: Visualizing patterns and trends in data
- **Scientific Research**: Presenting experimental results
- **Financial Analysis**: Plotting stock market trends and financial data
- **Machine Learning**: Visualizing model performance and data distributions
- **Education**: Teaching statistical concepts through visualization

## Matplotlib Pyplot

Pyplot (`plt`) is a collection of functions that make matplotlib work like MATLAB. Each pyplot function makes some change to a figure.

### Definition
Pyplot is a state-based interface to the matplotlib library. It provides a MATLAB-like interface with functions that manipulate the current figure.

### Basic Plotting

```python
import matplotlib.pyplot as plt
import numpy as np

xpoints = np.array([0, 6])
ypoints = np.array([0, 250])

plt.plot(xpoints, ypoints)
plt.show()
```

**Explanation**: This code creates a simple line plot connecting two points (0,0) and (6,250). The `plot()` function takes x and y coordinates as arguments and draws a line between them.

**Output**: A straight line from the origin (0,0) to the point (6,250).

Another example:

```python
import matplotlib.pyplot as plt
import numpy as np

xpoints = np.array([1, 8])
ypoints = np.array([3, 10])

plt.plot(xpoints, ypoints)
plt.show()
```

**Output**: A straight line from point (1,3) to point (8,10).

## Customizing Plots

### Markers

Markers are used to emphasize data points on a plot.

```python
import matplotlib.pyplot as plt
import numpy as np

ypoints = np.array([3, 8, 1, 10])

plt.plot(ypoints, marker='o')
plt.show()
```

**Explanation**: The `marker` parameter adds a circular marker ('o') at each data point. Matplotlib automatically assigns x-coordinates (0, 1, 2, 3) when only y-coordinates are provided.

**Output**: A line plot with circular markers at each data point.

### Common Marker Symbols
- `'o'`: Circle
- `'*'`: Star
- `'.'`: Point
- `'+'`: Plus
- `'x'`: X
- `'s'`: Square
- `'D'`: Diamond

### Linestyle

The linestyle parameter controls the appearance of the line connecting data points.

```python
import matplotlib.pyplot as plt
import numpy as np

ypoints = np.array([3, 8, 1, 10])

plt.plot(ypoints, linestyle='dotted')
# Alternative short form: plt.plot(ypoints, ls='dotted')
plt.show()
```

**Explanation**: The `linestyle` (or short form `ls`) parameter changes the appearance of the line. In this case, we're using a dotted line.

**Output**: A dotted line connecting the data points.

### Common Linestyles
- `'solid'` or `'-'`: Solid line (default)
- `'dotted'` or `':'`: Dotted line
- `'dashed'` or `'--'`: Dashed line
- `'dashdot'` or `'-.'`: Dash-dot line
- `'None'` or `' '`: No line

## Labels and Titles

### Adding Labels to Axes

```python
import numpy as np
import matplotlib.pyplot as plt

x = np.array([80, 85, 90, 95, 100, 105, 110, 115, 120, 125])
y = np.array([240, 250, 260, 270, 280, 290, 300, 310, 320, 330])

plt.plot(x, y)

plt.xlabel("Average Pulse")
plt.ylabel("Calorie Burnage")

plt.show()
```

**Explanation**: The `xlabel()` and `ylabel()` functions add descriptive labels to the x and y axes, making the plot more informative.

**Output**: A line plot with "Average Pulse" on the x-axis and "Calorie Burnage" on the y-axis.

### Adding a Title

```python
import numpy as np
import matplotlib.pyplot as plt

x = np.array([80, 85, 90, 95, 100, 105, 110, 115, 120, 125])
y = np.array([240, 250, 260, 270, 280, 290, 300, 310, 320, 330])

plt.title("Sports Watch Data")
plt.xlabel("Average Pulse")
plt.ylabel("Calorie Burnage")

plt.plot(x, y)
plt.show()
```

**Explanation**: The `title()` function adds a title to the plot, providing context for the visualization.

### Adding Grid Lines

Grid lines help in reading values from the plot more accurately.

```python
import numpy as np
import matplotlib.pyplot as plt

x = np.array([80, 85, 90, 95, 100, 105, 110, 115, 120, 125])
y = np.array([240, 250, 260, 270, 280, 290, 300, 310, 320, 330])

plt.title("Sports Watch Data")
plt.xlabel("Average Pulse")
plt.ylabel("Calorie Burnage")

plt.plot(x, y)

plt.grid()  # Add grid lines

plt.show()
```

**Explanation**: The `grid()` function adds grid lines to the plot, making it easier to read values.

**Output**: A line plot with grid lines, title, and axis labels.

## Multiple Plots

### Subplots

The `subplot()` function allows you to display multiple plots in one figure.

```python
import numpy as np
import matplotlib.pyplot as plt

# Plot 1:
x = np.array([0, 1, 2, 3])
y = np.array([3, 8, 1, 10])

plt.subplot(1, 2, 1)  # (rows, columns, position)
plt.plot(x, y)

# Plot 2:
x = np.array([0, 1, 2, 3])
y = np.array([10, 20, 30, 40])

plt.subplot(1, 2, 2)  # (rows, columns, position)
plt.plot(x, y)

plt.show()
```

**Explanation**: 
- `subplot(1, 2, 1)` divides the figure into 1 row and 2 columns, and places the first plot in position 1
- `subplot(1, 2, 2)` places the second plot in position 2
- The three arguments represent (rows, columns, position)

**Output**: Two side-by-side line plots.

## Scatter Plots

Scatter plots display values for two variables as a collection of points.

```python
import matplotlib.pyplot as plt
import numpy as np

x = np.array([5, 7, 8, 7, 2, 17, 2, 9, 4, 11, 12, 9, 6])
y = np.array([99, 86, 87, 88, 111, 86, 103, 87, 94, 78, 77, 85, 86])

plt.scatter(x, y)
plt.show()
```

**Explanation**: The `scatter()` function creates a scatter plot with one dot for each data point. It requires two arrays of the same length for x and y coordinates.

**Output**: A scatter plot showing the relationship between two variables.

### Why Use Scatter Plots?
- To identify correlations between variables
- To spot clusters and outliers
- To visualize the distribution of data points
- To compare groups of data

## Bar Charts

Bar charts display categorical data with rectangular bars.

```python
import matplotlib.pyplot as plt
import numpy as np

x = np.array(["A", "B", "C", "D"])
y = np.array([3, 8, 1, 10])

plt.bar(x, y)
plt.show()
```

**Explanation**: The `bar()` function creates a vertical bar chart. The height of each bar represents the value in the y-array.

**Output**: A vertical bar chart with categories A, B, C, and D on the x-axis.

### Horizontal Bar Charts

```python
import matplotlib.pyplot as plt
import numpy as np

x = np.array(["A", "B", "C", "D"])
y = np.array([3, 8, 1, 10])

plt.barh(x, y)  # Notice barh() instead of bar()
plt.show()
```

**Explanation**: The `barh()` function creates a horizontal bar chart.

**Output**: A horizontal bar chart with categories on the y-axis.

### Bar Width

You can control the width of bars using the `width` parameter:

```python
import matplotlib.pyplot as plt
import numpy as np

x = np.array(["A", "B", "C", "D"])
y = np.array([3, 8, 1, 10])

plt.bar(x, y, width=0.1)  # Narrow bars
plt.show()
```

**Explanation**: The `width` parameter adjusts the width of the bars. The default is 0.8.

**Output**: A bar chart with narrower bars than the default.

## Histograms

Histograms show the distribution of numerical data.

```python
import matplotlib.pyplot as plt
import numpy as np

# Generate 250 random values with a normal distribution
# mean=170, standard deviation=10
x = np.random.normal(170, 10, 250)

plt.hist(x)
plt.show()
```

**Explanation**: The `hist()` function creates a histogram. The random data is generated with a normal distribution around a mean of 170 with a standard deviation of 10.

**Output**: A histogram showing the frequency distribution of the randomly generated data.

### Why Use Histograms?
- To visualize the distribution of data
- To identify patterns in data
- To spot outliers and anomalies
- To check if data follows a particular distribution (e.g., normal)

## Pie Charts

Pie charts show the proportion of each category in a dataset.

```python
import matplotlib.pyplot as plt
import numpy as np

y = np.array([35, 25, 25, 15])

plt.pie(y)
plt.show()
```

**Explanation**: The `pie()` function creates a pie chart. Each wedge represents a proportion of the whole.

**Output**: A basic pie chart with four wedges of different sizes.

### Adding Labels to Pie Charts

```python
import matplotlib.pyplot as plt
import numpy as np

y = np.array([35, 25, 25, 15])
mylabels = ["Apples", "Bananas", "Cherries", "Dates"]

plt.pie(y, labels=mylabels)
plt.show()
```

**Explanation**: The `labels` parameter adds category names to each wedge of the pie chart.

**Output**: A pie chart with labeled wedges.

### Exploding Pie Chart Sections

```python
import matplotlib.pyplot as plt
import numpy as np

y = np.array([35, 25, 25, 15])
mylabels = ["Apples", "Bananas", "Cherries", "Dates"]
myexplode = [0.2, 0, 0, 0]  # Only "explode" the first wedge

plt.pie(y, labels=mylabels, explode=myexplode)
plt.show()
```

**Explanation**: The `explode` parameter pulls out specific wedges from the pie chart. The values in the `myexplode` array determine how far each wedge is offset from the center.

**Output**: A pie chart with the "Apples" wedge pulled out slightly from the center.

### Why Use Pie Charts?
- To show proportions of a whole
- To compare parts of a whole
- To display percentage distribution
- For simple data visualization when there aren't too many categories

## Conclusion

Matplotlib is a versatile and powerful plotting library in Python that allows for the creation of a wide variety of visualizations. This tutorial covered the basics of line plots, scatter plots, bar charts, histograms, and pie charts, as well as how to customize them with markers, line styles, labels, and titles.

By mastering these fundamentals, students will have a solid foundation for more advanced data visualization techniques.