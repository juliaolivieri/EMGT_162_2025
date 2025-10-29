# Lab 9

## Aggregation

| Function | Description |
|--|--|
| `.mean()` | Average |
| `.sum()`  | Sum total | 
| `.count()` | Number of non-null values |
| `min()` | Smallest value |
| `max()` | Largest value |
| `median()` | Median value |
| `.std()` | Standard deviation | 
| `.var()` | Variance | 
| `.nunique()`  | The number of unique values |

### Code from class:

```
# mean body mass of each species
penguins.groupby("species")["body_mass_g"].mean()

# median body mass from each island
penguins.groupby("island")["body_mass_g"].median()

# minimum body mass by sex
penguins.groupby("sex")["body_mass_g"].min()
```

## Lab questions

1. Download this bikesharing data:
   * `bikesharing.csv`: [https://drive.google.com/file/d/1r_5a9odlnxs1DGPbvWP-s8hsdxOWBO14/view?usp=sharing](https://drive.google.com/file/d/1O32iI5wnlsNWNyuXuE0QhmSP-X6u5p3N/view?usp=sharing)
   * `monthly_info.csv`: https://drive.google.com/file/d/1GBJ3QyVpE31v8kPWCL-4epPFRThrpuL9/view?usp=sharing 



