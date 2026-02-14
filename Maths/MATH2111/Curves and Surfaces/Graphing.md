Here I will outline how to use MatPlotLib and Python to graph curves and surfaces
## Curves in 2d
The following are all different ways of plotting the top half of the unit circle:
```Python
import numpy as np
from matplotlib import pyplot as plt

## Parametric
t = np.linspace(0, np.pi)

x = np.cos(t)
y = np.sin(t)

plt.plot(x, y)
plt.show()

## Functionally

x = np.linspace(-1, 1)
f_x = np.sqrt(1 - x**2)

plt.plot(x, f_x)
plt.show()


## Implcitly
def implicit_equ(x, y):
    # x^2 + y^2 = 1
    return x**2 + y**2


x = np.linspace(-1, 1)
y = np.linspace(0, 1)

X, Y = np.meshgrid(x, y)
Z = implicit_equ(X, Y)

plt.contour(X, Y, Z, levels=[1])
plt.show()
```
## Curves in 3d
Curves in 3d described parametrically can be plotted like this:
```python
import numpy as np
from matplotlib import pyplot as plt

ax = plt.figure().add_subplot(projection="3d")

t = np.linspace(0, np.pi)

c = (np.cos(t), np.sin(t), t)

ax.plot(c[0], c[1], c[2])
plt.show()
```

## Surfaces in 3d
