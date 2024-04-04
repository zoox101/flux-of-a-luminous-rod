# flux-of-a-luminous-rod
Equation governing the flux experienced by a zero dimensional observer positioned on the perpendicular bisector of a uniform luminous one dimensional rod:

$$F = \frac{L}{2 \pi H D} * arctan(\frac{H}{2 D})$$

Where $F$ is the flux experienced by the observer, $L$ is the luminosity of the rod, $H$ is the length of the rod, and $D$ is the distance between the center of the rod and the observer.

## Python Function

```python
import math

def get_flux_rod(
  L: float, # Total luminosity of the rod
  D: float, # Distance of the observer from the center of the rod
  H: float  # Length of the rod
):

  # Flux of a point, prevents divide by zero error when H == 0
  if H == 0:
    return L / (4 * math.pi * (D ** 2))

  # Flux of a uniform rod
  else:
    return (L / (2 * math.pi * H * D)) * math.arctan(H / (2 * D))
```
