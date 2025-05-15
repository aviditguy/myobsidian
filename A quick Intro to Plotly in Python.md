First thing to do is to install Matplotlib. I am on arch,
```bash
sudo pacman -S python-plotly
```

After Installing we have to import it to use it
```run-python
import plotly.express as px
import numpy as np
import pandas as pd
```

### Your first Plotly Plot (Line Chart)

```run-python
x = [1, 2, 3, 4, 5]
y = [10, 20, 15, 30, 25]

fig = px.line(x=x, y=y, title="Simple Line Chart")
fig.show()
```

## Common Plotly Express Charts
### 1. Line Plot

```run-python
fig = px.line(x=[1, 2, 3], y=[3, 1, 6], title="Line Plot")
fig.show()
```

### 2. Bar Chart

```run-python
fig = px.bar(x=["A", "B", "C"], y=[4, 7, 1], title="Bar Chart")
fig.show()
```

### 3. Scatter Plot (with Hover Tooltips)

```run-python
df = pd.DataFrame({
    "x": [1, 2, 3, 4],
    "y": [10, 11, 12, 13],
    "label": ["A", "B", "C", "D"]
})

fig = px.scatter(df, x="x", y="y", hover_name="label", title="Scatter Plot with Labels")
fig.show()
```

### 4. Pie Chart

```run-python
fig = px.pie(names=["Python", "JavaScript", "C++"], values=[40, 35, 25], title="Language Share")
fig.show()
```

### 5. Histogram

```run-python
data = np.random.randn(500)

fig = px.histogram(data, nbins=30, title="Histogram")
fig.show()
```

### 6. 3D Scatter Plot

```run-python
df = pd.DataFrame({
    "x": np.random.randn(100),
    "y": np.random.randn(100),
    "z": np.random.randn(100),
    "label": np.random.choice(['A', 'B'], size=100)
})

fig = px.scatter_3d(df, x="x", y="y", z="z", color="label", title="3D Scatter Plot")
fig.show()
```

### 7. Animation (Dynamic Plot)

```run-python
df = px.data.gapminder()

fig = px.scatter(df,
                 x="gdpPercap", y="lifeExp",
                 animation_frame="year",
                 animation_group="country",
                 size="pop", color="continent",
                 hover_name="country",
                 log_x=True, size_max=60,
                 title="Gapminder: GDP vs Life Expectancy Over Time")
fig.show()
```

### Export to HTML (share your plot anywhere)

```run-python
fig = px.bar(x=["A", "B", "C"], y=[10, 20, 15], title="Exportable Bar Chart")

# Save to HTML
fig.write_html("bar_chart.html")

# Optional: open it in your browser
import webbrowser
webbrowser.open("bar_chart.html")
```
