# flux-of-a-luminous-rod
Equation governing the flux experienced by an observer of negligible size positioned on the perpendicular bisector of a uniform luminous one dimensional rod:

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

## Proof

### Assumptions

The equation for flux from a point source:
$F = \frac{L}{4 \pi D^2}$

The distance from a point $x$ on the rod to the observer:
$D_{seg} = \sqrt{D^2 + x^2}$

The luminosity of an infinitely small segment of the rod:
$L_{seg} = L * \frac{dx}{H}$

### Process

$F_{seg} = \frac{L_{seg}}{4 \pi D_{seg}^2}$

$F_{seg} = \frac{L dx / H}{4 \pi (D^2 + x^2)}$

$F_{seg} = \frac{L}{4 \pi H} * \frac{dx}{D^2 + x^2}$

$F = \frac{L}{4 \pi H} * \int_{-H/2}^{H/2}{ \frac{1}{D^2 + x^2} dx}$

$F = \frac{L}{4 \pi H} * \left[\frac{1}{D}*\arctan(\frac{x}{D})\right]_{-H/2}^{H/2}$

$F = \frac{L}{4 \pi H D} * \left(\arctan(\frac{H / 2}{D}) - \arctan(\frac{-H / 2}{D})\right)$

$F = \frac{L}{4 \pi H D} * \left(\arctan(\frac{H}{2 D}) + \arctan(\frac{H}{2 D})\right)$

$F = \frac{L}{2 \pi H D} * \arctan(\frac{H}{2 D})$

$Q.E.D.$
