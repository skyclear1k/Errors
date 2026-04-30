Here's a full walkthrough of the theory and then we'll apply it to your permeability measurement.

---

## What is error propagation?

Every experimental measurement has uncertainty. When you compute a result from several measured quantities, each measurement's uncertainty contributes to the final uncertainty of the result. Error propagation is the mathematical framework for tracking how those individual uncertainties combine.

**The general rule** for a function $k = f(x_1, x_2, \ldots, x_n)$, the absolute uncertainty $\delta k$ is:

$$\delta k = \sqrt{ \left(\frac{\partial k}{\partial x_1}\delta x_1\right)^2 + \left(\frac{\partial k}{\partial x_2}\delta x_2\right)^2 + \cdots }$$

This is the *quadrature* (RSS — root sum of squares) formula, and it applies when errors are **independent and random**. For a **worst-case (maximum) error**, you instead sum the absolute values:

$$\delta k = \left|\frac{\partial k}{\partial x_1}\right|\delta x_1 + \left|\frac{\partial k}{\partial x_2}\right|\delta x_2 + \cdots$$

---

## Applying it to your formula

Your formula is:

$$k = \frac{h \cdot \mu \cdot L}{T \cdot \Delta p}$$

This is a product/quotient of all variables — that's the ideal case, because the **relative (percentage) errors add directly**. Taking the logarithm and differentiating:

$$\frac{\delta k}{k} = \frac{\delta h}{h} + \frac{\delta T}{T} + \frac{\delta \mu}{\mu} + \frac{\delta L}{L} + \frac{\delta \Delta p}{\Delta p}$$

(worst-case) or in quadrature (RSS):

$$\frac{\delta k}{k} = \sqrt{ \left(\frac{\delta h}{h}\right)^2 + \left(\frac{\delta T}{T}\right)^2 + \left(\frac{\delta \mu}{\mu}\right)^2 + \left(\frac{\delta L}{L}\right)^2 + \left(\frac{\delta \Delta p}{\Delta p}\right)^2 }$$

