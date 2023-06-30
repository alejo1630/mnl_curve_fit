# Multi Variable Non-Linear Curve Fit

This Python Notebook uses the curve fit method to find the constant parameters of constitutive models for the dynamic behavior of materials based on strain and stress curves for several strain rates

## 🔰 How does it work?

- Data is uploaded with the following values
  1. Strain $(\varepsilon)$
  2. Stress $(\sigma)$
  3. Strain Rate $(\dot{\varepsilon})$
- The [Curve Fit](https://docs.scipy.org/doc/scipy/reference/generated/scipy.optimize.curve_fit.html) method from Scipy library is used to fit the mathematical models with the experimental data
- The following constitutive models are used
    - **Power Law**:
      $$\sigma = k\varepsilon^{m}\dot{\varepsilon}^{n}$$
      
    - **Johnson-Cook**:
      $$\sigma = [A + B\varepsilon^{n}]\left[1 + K\ln{\left(\frac{\dot{\varepsilon}}{\dot{\varepsilon}_{0}}\right)}\right]$$
      
    - **Cowper-Symonds**:
      $$\sigma = E_{tan}\varepsilon + \sigma_{Y} - \frac{E_{tan}\sigma_{Y}}{E}$$
      $$\sigma_{Y} = \sigma_{0}\left[1 + \left(\frac{\dot{\varepsilon}}{D}\right)^{\frac{1}{p}}\right]$$

     - The $R^{2}$ is calculated for each fit:
       -  Power Law: **0.86**
       -  Johnson-Cook: **0.71**
       -  Cowper-Symonds: **0.76**

