Here's a thorough explanation of the theory, followed by the specific calculation for your permeability formula.

---

## Error and uncertainty analysis — the foundations

When you measure a quantity that depends on several independent variables, each measured with some uncertainty, the question is: *how do those individual errors combine into the final result's uncertainty?*

### The general law of error propagation

If you have a result $k = f(x_1, x_2, ..., x_n)$ where each variable $x_i$ has an absolute uncertainty $\delta x_i$, the absolute uncertainty in $k$ is:

$$\delta k = \sqrt{\left(\frac{\partial k}{\partial x_1}\delta x_1\right)^2 + \left(\frac{\partial k}{\partial x_2}\delta x_2\right)^2 + \cdots}$$

This is the **quadratic sum** (RSS — root sum of squares). It assumes errors are random and independent. If errors might be correlated or systematically biased, you use the more conservative **linear sum** instead:

$$\delta k = \left|\frac{\partial k}{\partial x_1}\right|\delta x_1 + \left|\frac{\partial k}{\partial x_2}\right|\delta x_2 + \cdots$$

### The power-law shortcut

For functions of the form $k = C \cdot x_1^{a} \cdot x_2^{b} \cdot x_3^{c} \cdots$, the **relative uncertainty** (percentage error) has a beautifully simple form. Taking the logarithm and differentiating:

$$\frac{\delta k}{k} = \sqrt{\left(a\frac{\delta x_1}{x_1}\right)^2 + \left(b\frac{\delta x_2}{x_2}\right)^2 + \left(c\frac{\delta x_3}{x_3}\right)^2 + \cdots}$$

Each term is simply the **exponent times the relative error** of that variable. This is the key tool for your problem.

### Applying this to the Darcy-Weisbach permeability formula

Your formula is:

$$k = \frac{h \cdot \mu \cdot L}{T \cdot \Delta p \cdot A}$$

Every variable appears with exponent **±1**, so the relative uncertainty is:

$$\frac{\delta k}{k} = \sqrt{\left(\frac{\delta h}{h}\right)^2 + \left(\frac{\delta \mu}{\mu}\right)^2 + \left(\frac{\delta L}{L}\right)^2 + \left(\frac{\delta T}{T}\right)^2 + \left(\frac{\delta(\Delta p)}{\Delta p}\right)^2 + \left(\frac{\delta A}{A}\right)^2}$$

### Finding the maximum allowable error on h

You want $\delta k / k \leq 5\%$, and all other variables are known to ±1%. You need to find the budget left for $h$.

Rearranging:

$$\left(\frac{\delta h}{h}\right)^2 = \left(\frac{\delta k}{k}\right)^2 - \left(\frac{\delta \mu}{\mu}\right)^2 - \left(\frac{\delta L}{L}\right)^2 - \left(\frac{\delta T}{T}\right)^2 - \left(\frac{\delta(\Delta p)}{\Delta p}\right)^2 - \left(\frac{\delta A}{A}\right)^2$$

$$\left(\frac{\delta h}{h}\right)^2 = (5\%)^2 - 5 \times (1\%)^2 = 25 - 5 = 20 \quad (\%^2)$$

$$\frac{\delta h}{h} = \sqrt{20} \approx 4.47\%$$

The interactive calculator below lets you explore this — adjust the target uncertainty for $k$ and the errors on the other variables to see what headroom remains for $h$.---

### Key takeaways

**The answer to your question:** with all 5 other variables known to ±1%, the maximum allowable error on $h$ is **≈ ±4.47%**, or about **0.45 mm** on your 10 mm sample.

**Why this works the way it does:**

Each variable contributes its squared relative error to the total variance budget. With a 5% target on $k$, you have a "variance budget" of $5^2 = 25\,\%^2$. The five known variables each consume $1^2 = 1\,\%^2$, leaving $25 - 5 = 20\,\%^2$ for $h$, giving $\sqrt{20} \approx 4.47\%$.

**Important practical notes:**

- This analysis assumes the **RSS method** (random, independent errors). If errors might be systematic and correlated, use linear summation instead — this gives a more conservative (larger) total uncertainty.
- The area $A$ (cross-section) is often overlooked but worth checking: it typically depends on a diameter measurement, so its error is *doubled* if computed from a radius ($A = \pi r^2$ → $\delta A/A = 2\,\delta r/r$).
- The formula treats $\Delta p$ as directly measured. If it's derived from a pressure sensor with its own calibration chain, that uncertainty may be larger than ±1%.