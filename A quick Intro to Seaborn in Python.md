First thing to do is to install Matplotlib. I am on arch,
```bash
sudo pacman -S python-seaborn
```

After Installing we have to import it to use it
```run-python
import seaborn as sns
import numpy as np
import matplotlib.pyplot as plt
```

## Why Seaborn?
* **Easier syntax** than raw Matplotlib for many common plots
* Built-in **themes and color palettes**
* Works directly with **Pandas Dataframes**
* Great for **statistical visualization** (categorical vs. numerical data)

### Your First Seaborn Plot

```run-python
# Sample data
tips = sns.load_dataset("tips")

# Basic scatter plot
sns.scatterplot(data=tips, x="total_bill", y="tip")
plt.title("Total Bill vs Tip")
plt.show()
```

## Seaborn Plot Types
### 1. Line Plot
```run-python
sns.lineplot(data=tips, x="size", y="total_bill")
plt.show()
```

### 2. Scatter Plot with Hue (color by category)

```run-python
sns.scatterplot(data=tips, x="total_bill", y="tip", hue="sex")
plt.show()
```

### 3. Box Plot

```run-python
sns.boxplot(data=tips, x="day", y="total_bill", hue="day", palette="Set3", legend=False)
plt.show()
```

### 4. Violin Plot

```run-python
sns.violinplot(data=tips, x="day", y="total_bill", hue="sex", split=True)
plt.show()
```

### 5. Histogram (with KDE)

```run-python
sns.histplot(data=tips, x="total_bill", kde=True, bins=20)
plt.show()
```

### 6. Count Plot (like bar plot for counts)

```run-python
sns.countplot(data=tips, x="day")
plt.show()
```

### 7. Pair Plot (matrix of scatter plots + histograms)

```run-python
sns.pairplot(tips, hue="sex")
plt.show()
```

### 8. If you already have NumPy arrays

```run-python
import pandas as pd
import numpy as np
df = pd.DataFrame({
	"x": np.random.randn(100),
	"y": np.random.randn(100),
	"category": np.random.choice(["A", "B"], size=100)
})
sns.scatterplot(data=df, x="x", y="y", hue="category")
plt.show()
```
