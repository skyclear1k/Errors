# Darcy-Weisbach Formula — Fluid Mechanics Reference

## Formula

$$
h_f = f \cdot \frac{L}{D} \cdot \frac{V^2}{2g}
$$

## Variables

| Symbol | Description              | Unit (SI) |
|--------|--------------------------|-----------|
| h_f    | Head loss due to friction | m         |
| f      | Darcy friction factor    | dimensionless |
| L      | Pipe length              | m         |
| D      | Pipe diameter            | m         |
| V      | Flow velocity            | m/s       |
| g      | Gravitational acceleration (9.81) | m/s² |

## Notes

- Use the **Moody chart** or **Colebrook equation** to find `f`
- For laminar flow (Re < 2300): `f = 64 / Re`
- For turbulent flow, use the Colebrook-White equation:

$$
\frac{1}{\sqrt{f}} = -2 \log\left(\frac{\varepsilon}{3.7D} + \frac{2.51}{Re\sqrt{f}}\right)
$$

## Example

Given:
- L = 100 m
- D = 0.05 m
- V = 2 m/s
- f = 0.02

$$
h_f = 0.02 \cdot \frac{100}{0.05} \cdot \frac{2^2}{2 \times 9.81} \approx 4.08 \, m
$$