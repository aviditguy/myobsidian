First thing to do is to install Matplotlib. I am on arch,
```bash
sudo pacman -S python-matplotlib
```

After Installing we have to import it to use it
```run-python
import matplotlib.pyplot as plt
import numpy as np
```

### Your First Plot

```run-python
x = [1, 2, 3, 4, 5]
y = [1, 4, 9, 16, 25]

plt.plot(x, y)
plt.title("Simple Line Plot")
plt.xlabel("X Axis")
plt.ylabel("Y Axis")
plt.grid(True)
plt.show()
```

### Bar Chart

```run-python {import="block"}
categories = ['A', 'B', 'C', 'D']
values = [10, 15, 7, 12]

plt.bar(categories, values, color='skyblue')
plt.title("Bar Chart Example")
plt.show()
```

### Histogram

```run-python
data = np.random.randn(1000)

plt.hist(data, bins=30, color='purple', alpha=0.7)
plt.title("Histogram Example")
plt.show()
```

### Scatter Plot

```run-python
x = np.random.rand(50)
y = np.random.rand(50)

plt.scatter(x, y, color='red')
plt.title("Random Scatter Plot")
plt.xlabel("X")
plt.ylabel("Y")
plt.show()
```

### Customize Plots

```run-python
x = [1, 2, 3, 4, 5]
y = [10, 12, 8, 6, 15]

plt.plot(x, y, linestyle='--', marker='o', color='green')
plt.title("Customized Plot")
plt.xlabel("X Axis")
plt.ylabel("Y Axis")
plt.grid(True)
plt.show()
```

### Multiple Plots (Subplots)

```run-python
fig, axs = plt.subplots(1, 2, figsize=(10, 4))

axs[0].plot(x, y)
axs[0].set_title("Plot 1")

axs[1].bar(categories, values)
axs[1].set_title("Plot 2")

plt.tight_layout()
plt.show()
```

### Basic Pie Chart

```run-python
labels = ['Apples', 'Bananas', 'Cherries', 'Dates']
sizes = [30, 20, 25, 25]

plt.pie(sizes, labels=labels)
plt.title("Basic Pie Chart")
plt.show()
```

### Customized Pie Chart

```run-python
labels = ['Python', 'C++', 'Java', 'JavaScript']
sizes = [215, 130, 245, 210]
colors = ['gold', 'yellowgreen', 'lightcoral', 'lightskyblue']
explode = (0.1, 0, 0, 0)  # "explode" the 1st slice

plt.pie(sizes, explode=explode, labels=labels, colors=colors,
        autopct='%1.1f%%', shadow=True, startangle=140)
plt.title("Programming Language Usage")
plt.axis('equal')  # Equal aspect ratio ensures pie is drawn as a circle.
plt.show()
```
