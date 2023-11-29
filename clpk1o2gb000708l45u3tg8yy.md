---
title: "Mastering Data Visualization with Matplotlib: A Comprehensive Tutorial"
datePublished: Wed Nov 29 2023 17:32:10 GMT+0000 (Coordinated Universal Time)
cuid: clpk1o2gb000708l45u3tg8yy
slug: mastering-matplotlib
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701269628119/93f7c965-fde4-4426-858f-f04e4ba4d1d0.webp
tags: python, data-science, data-analysis, matplotlib

---

---

# Installing MatPlotLib:

```bash
pip install matplotlib
```

---

# Matplotlib Plotting:

To plot x and y points in Matplotlib, you can use the plot function. To do so, you’ll need to identify the x and y values for each point, respectively. Let’s dive into an example below.

```python
import matplotlib.pyplot as plt
import numpy as np

xpoints = np.array([1, 8])
ypoints = np.array([3, 10])

plt.plot(xpoints, ypoints)
plt.show()
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701278182951/520fa9e0-5458-45cb-be9b-a282b4c7caff.png align="center")

---

# Matplotlib Markers:

You can use the keyword argument `marker` to emphasize each point with a specified marker:

Types of markers available:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701278374419/b36424f6-bb55-465c-9cd1-34dcc963f868.png align="center")

```python
import numpy as np
import matplotlib.pyplot as plt
X = [1, 2, 3, 4]
Y = [1, 4, 9, 16]
plt.plot(X,Y,marker="o")
plt.show()
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701278246251/10f48202-ddec-4a16-bfd2-802700754e7e.png align="center")

---

Matplotlib Types of Lines:

Dotted:

```python
plt.plot(X,Y, linestyle = 'dotted')
```

Dashed:

```python
plt.plot(X,Y, linestyle = 'dashed')
```

Dashdot:

```python
plt.plot(X,Y, linestyle = 'dashdot')
```

---

# Matplotlib Line colors:

You can use the keyword argument `color` or the shorter `c` to set the color of the line:

```python
#Set line color to red
plt.plot(X,Y, color = 'r')

#Hexadeciamal code for colours
plt.plot(X,Y, color = '#FF0000')
```

![](https://www.w3schools.com/python/img_matplotlib_line_red.png align="center")

---

# Matplotlib Titles and Markers:

With Pyplot, you can use the `xlabel()` and `ylabel()` functions to set a label for the x- and y-axis.

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

![](https://www.w3schools.com/python/img_matplotlib_labels.png align="center")

With Pyplot, you can use the `title()` function to set a title for the plot.

```python
plt.title("Sports Watch Data")
```

---

# Matplotlib Gridlines:

With Pyplot, you can use the `grid()` function to add grid lines to the plot.

```python
plt.grid()
```

![](https://www.w3schools.com/python/img_matplotlib_grid.png align="center")

---

# Matplotlib Subplot:

## Display Multiple Plots

With the `subplot()` function you can draw multiple plots in one figure:

```python
plt.subplot(1, 2, 1)
# this denotes 1 row 2 columns and 1st elemnt
```

```python
plt.subplot(1, 2, 2)
#this denotes 1 row of 2 columns and 2nd plot or element
```

```python
import matplotlib.pyplot as plt
import numpy as np

#plot 1:
x = np.array([0, 1, 2, 3])
y = np.array([3, 8, 1, 10])

plt.subplot(1, 2, 1)
plt.plot(x,y)

#plot 2:
x = np.array([0, 1, 2, 3])
y = np.array([10, 20, 30, 40])

plt.subplot(1, 2, 2)
plt.plot(x,y)

plt.show()
```

![](https://www.w3schools.com/python/img_matplotlib_subplots1.png align="center")

## Title each plot with title():

```python
import matplotlib.pyplot as plt
import numpy as np

#plot 1:
x = np.array([0, 1, 2, 3])
y = np.array([3, 8, 1, 10])

plt.subplot(1, 2, 1)
plt.plot(x,y)
plt.title("SALES")

#plot 2:
x = np.array([0, 1, 2, 3])
y = np.array([10, 20, 30, 40])

plt.subplot(1, 2, 2)
plt.plot(x,y)
plt.title("INCOME")

plt.show()
```

![](https://www.w3schools.com/python/img_matplotlib_subplots4.png align="center")

## Supertitle (Title for entire plotting):

```python
import matplotlib.pyplot as plt
import numpy as np

#plot 1:
x = np.array([0, 1, 2, 3])
y = np.array([3, 8, 1, 10])

plt.subplot(1, 2, 1)
plt.plot(x,y)
plt.title("SALES")

#plot 2:
x = np.array([0, 1, 2, 3])
y = np.array([10, 20, 30, 40])

plt.subplot(1, 2, 2)
plt.plot(x,y)
plt.title("INCOME")

plt.suptitle("MY SHOP")
plt.show()
```

![](https://www.w3schools.com/python/img_matplotlib_subplots5.png align="center")

---

# Matplotlib Bars:

```python
import matplotlib.pyplot as plt
import numpy as np

x = np.array(["A", "B", "C", "D"])
y = np.array([3, 8, 1, 10])

plt.bar(x,y)
plt.show()
```

## Horizontal Bars:

```python
import matplotlib.pyplot as plt
import numpy as np

x = np.array(["A", "B", "C", "D"])
y = np.array([3, 8, 1, 10])

plt.barh(x,y)
plt.show()
```

### Bar color:

```python
plt.bar(x, y, color = "red")
```

---

# Matplotlib Scatter Plots:

```python
import matplotlib.pyplot as plt
import numpy as np

x = np.array([5,7,8,7,2,17,2,9,4,11,12,9,6])
y = np.array([99,86,87,88,111,86,103,87,94,78,77,85,86])

plt.scatter(x, y)
plt.show()
```

![](https://www.w3schools.com/python/img_matplotlib_scatter.png align="center")

## Compare Plots:

```python
import matplotlib.pyplot as plt
import numpy as np

#day one, the age and speed of 13 cars:
x = np.array([5,7,8,7,2,17,2,9,4,11,12,9,6])
y = np.array([99,86,87,88,111,86,103,87,94,78,77,85,86])
plt.scatter(x, y)

#day two, the age and speed of 15 cars:
x = np.array([2,2,8,1,15,8,12,9,7,3,11,4,7,14,12])
y = np.array([100,105,84,105,90,99,90,95,94,100,79,112,91,80,85])
plt.scatter(x, y)

plt.show()
```

![](https://www.w3schools.com/python/img_matplotlib_scatter_compare.png align="center")

---

# Matplotlib Histogram:

```python
import matplotlib.pyplot as plt
import numpy as np

x = np.random.normal(170, 10, 250)

plt.hist(x)
plt.show() 
```

![](https://www.w3schools.com/python/img_matplotlib_histogram1.png align="center")

---

# Matplotlib Pie Charts:

```python
import matplotlib.pyplot as plt
import numpy as np

y = np.array([35, 25, 25, 15])

plt.pie(y)
plt.show() 
```

![](https://www.w3schools.com/python/img_matplotlib_pie1.png align="center")

## Piechart labels:

```python
import matplotlib.pyplot as plt
import numpy as np

y = np.array([35, 25, 25, 15])
mylabels = ["Apples", "Bananas", "Cherries", "Dates"]

plt.pie(y, labels = mylabels)
plt.show() 
```

![](https://www.w3schools.com/python/img_matplotlib_pie_labels.png align="center")

## Piechart Legends:

```python
import matplotlib.pyplot as plt
import numpy as np

y = np.array([35, 25, 25, 15])
mylabels = ["Apples", "Bananas", "Cherries", "Dates"]

plt.pie(y, labels = mylabels)
plt.legend()
plt.show() 
```

![](https://www.w3schools.com/python/img_matplotlib_pie_legend.png align="center")