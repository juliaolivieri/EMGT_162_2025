# Lecture 17: Plotting, joining, and aggregate functions

Links to roller coaster dataset:
* coasters.csv: https://drive.google.com/file/d/1OWspBvnysh6Bf7dyBLywId6ZVS1RzXgV/view?usp=sharing
* parks.csv: https://drive.google.com/file/d/14WvN9oId5zdBVkqRZggxnn3WnH5CJ-qy/view?usp=sharing

Links to penguins dataset:
* penguins.csv: https://drive.google.com/file/d/1ESxaIakPh6IpsA_x1H1798003CuqJP8r/view
* penguin_species.csv: https://drive.google.com/file/d/1ZuDVMF-6BM6bKV2SHKwkg9sG2w8OCh5-/view?usp=sharing

## Part 1: Practice from last class

Try to minimize the amount you look at the examples from last week while you're working on these problems. The goal is to be able to access these commands from memory.

1. Load the relevant python libraries (pandas, seaborn, matplotlib).
2. Load the data from `coasters.csv`.
3. Display the first five rows of the resulting dataframe.
4. Show the categories and frequencies for the `Status` and `Type_Main` columns (use `value_counts()`). Do NA values show up in the results?
5. How fast is the fastest roller coaster? How fast is the slowest roller coaster?
6. Use `displot()` to make a plot of one of the variables.

## Part 2: Joining Data Frames

### Code from class:

```
penguins = pd.read_csv("penguins.csv")
species = pd.read_csv("penguin_species.csv")

# inner join
penguins.merge(species, how = "inner", left_on = "species", right_on = "name")

# outer join
penguins.merge(species, how = "outer", left_on = "species", right_on = "name")

# left join
penguins.merge(species, how = "left", left_on = "species", right_on = "name")

# right join
penguins.merge(species, how = "right", left_on = "species", right_on = "name")
```

1. Load the data from `parks.csv`.
2. Try each of the following join types. Keep track of the number of rows in each resulting dataframe.
   * inner
   * outer
   * left
   * right
3. Which join type would you choose if you were analyzing this data?
4. Save the resulting merged dataframe with your chosen join type to a new variable name.
5. Create a plot showing the number of coasters from each state.

## Part 3: Plotting

### Code from class:

```
# histogram
sns.displot(penguins, x = "flipper_length_mm", hue = "island")

# kde plot
sns.displot(penguins, x = "flipper_length_mm", hue = "island", kind = "kde")

# scatter plot
sns.relplot(penguins, x = "bill_length_mm", y = "bill_depth_mm", col = "sex", size = "body_mass_g", hue = "species")

# swarm plot
sns.catplot(penguins, x = "species", y = "body_mass_g", hue = "sex")

# box plot
sns.catplot(penguins, x = "species", y = "body_mass_g", hue = "sex", kind = "box")
```

1. Create a scatterplot of `Drop` vs `speed`. Color by `Type_Main`. What can you learn from this plot?
2. Create a box plot of `Type_main` vs `year_introduced`. What can you learn from this plot?
3. Choose two quantitative variables. Create a scatterplot of them. Try changing the size/shape/color of the points to make an informative plot.
4. Choose a quantitative variable and a categorical variable. Make multiple plots showing the relationship between these two variables (histogram colored by categorical, box plot, etc). Which plot is most informative?

## Part 4: Aggregation

### Code from class:

```

```



