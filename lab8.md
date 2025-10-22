### Plotting

#### Code from class

```
# create a histogram for fare
sns.displot(data = taxis, x = "fare")
plt.show()

# create a bar plot for pickup_borough
sns.displot(data = taxis, x = "pickup_borough")
plt.show()
```

#### Exercises
1. **(CW) Create a histogram for each quantitative variable in the penguins dataset**
1. **(CW) Create a bar chart for each categorical variable in the penguins dataset**
1. Create a histogram of `bill_length_mm` of Adelie penguins.
1. There are many different kinds of plots you can make with the `displot()` function. What happens when you use an x and y variable? 
1. Test out other displot options based on this document: https://seaborn.pydata.org/tutorial/distributions.html 

## Part 2


### Exercises 

1. **(CW) Download the college majors dataset and load it using pandas: https://drive.google.com/file/d/1WK9sQdr_S7RHDUIdEBPZ88dPeOUvTY7E/view?usp=sharing (you can find documentation about this dataset here: https://data.world/fivethirtyeight/college-majors/workspace/file?filename=readme.md
)**
1. Find the number of rows and columns of the DataFrame.
1. **(CW) What is the data type of each column?**
1. Use the `value_counts()`  function to find the count of each unique value in every categorical column.
1. **(CW) Filter the data based on one categorical variable value. Compute summary statistics before and after filtering. Do any of the summary statistics change?**
1. **(CW) Make at least one plot based on this data using the `displot` function.**
1. **(CW) Brainstorm at least three plots that would help you understand this data. Which variable(s) are involved? Are they quantitative or categorical?**

## Part 3

1. **(CW) Summarize the information presented in this plot in ~1 sentence.**
<img src="https://raw.githubusercontent.com/juliaolivieri/COMP_162_2024/main/lecture16/flipper_density.png" height="400" />
1. **(CW) Summarize the information presented in this plot in ~1 sentence.**
<img src="https://raw.githubusercontent.com/juliaolivieri/COMP_162_2024/main/lecture16/example_scatter.png" height="400" />
1. **(CW) Summarize the information presented in this plot in ~1 sentence.**
<img src="https://raw.githubusercontent.com/juliaolivieri/COMP_162_2024/main/lecture16/example_box.png" height="400" />

## Part 1

Example code from class:

```
import seaborn as sns
import matplotlib.pyplot as plt

# Create a histogram of the "total_bill" variable
sns.displot(data=tips, x="total_bill")
plt.show()

# Create a histogram of the "total_bill" variable colored by "smoker" and faceted by "time"
sns.displot(data=tips, x="total_bill",hue = "smoker", col="time", kind = "hist")
plt.show()

sns.displot(data=tips, x = "tip", hue="time", kind="kde")
plt.show()

# Create a scatterplot of "total_bill" vs "tip"
sns.relplot(
    data=tips,
    x="total_bill", y="tip"
)
plt.show()

# Create a scatterplot of "total_bill" vs "tip" colored by "smoker", faceted by "time", with marker style determined by "smoker" and size of the marker determined by "size"
sns.relplot(
    data=tips,
    x="total_bill", y="tip", col="time",
    hue="smoker", style="smoker", size="size"
)
plt.show()

sns.relplot(
    data=penguins,
    x="bill_length_mm", y="bill_depth_mm", col="sex",
    hue="species", style="island", size="body_mass_g"
)
plt.show()

# Create a barplot of "day" by "total_bill" colored by "smoker"
sns.catplot(data=tips, kind="bar", x="day", y="total_bill", hue="smoker")
plt.show()

sns.catplot(data = penguins, x = "species", y = "body_mass_g", kind = "box", hue="sex")
plt.show()
```

Documentation for functions:
* `displot`: https://seaborn.pydata.org/generated/seaborn.displot.html
* `relplot`: https://seaborn.pydata.org/generated/seaborn.relplot.html
* `catplot`: https://seaborn.pydata.org/generated/seaborn.catplot.html

Use the college majors dataset: https://drive.google.com/file/d/1WK9sQdr_S7RHDUIdEBPZ88dPeOUvTY7E/view?usp=sharing (you can find documentation about this dataset here: https://data.world/fivethirtyeight/college-majors/workspace/file?filename=readme.md

1. **(CW) Make a plot of a quantitative variable using `displot()`. Set `hue` equal to a categorical variable. Try with `kind = "hist"` and `kind = "kde"`. Which provides a better representation of your data?**
1. **(CW) Make a plot of a categorical variable vs a quantitative variable using `catplot()`. Set `hue` equal to a categorical variable. Try with `kind` equal to each of the following: `"strip", "swarm", "box", "violin", "boxen", "point", "bar"`. Which provides the best representation of your data?**
1. **(CW) Create at least one of the plots you brainstormed in last classwork (Brainstorm at least three plots that would help you understand this data).**
1. Work on improving one of your plots so that it enhances understanding of the dataset. Save it by including `plt.savefig("my_img.png")` on the line before `plt.show()`.
1. **(CW) Submit your favorite plot: [https://forms.gle/P7ZEUeKV8JSZei4m9](https://forms.gle/P7ZEUeKV8JSZei4m9)**

