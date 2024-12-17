# Finding Optimal Window Size to Calculate Integrated Autocorrelation Time for Lattice QCD Ensembles

## Project Overview
This project focuses on optimizing the calculation of integrated autocorrelation time (τint) for lattice Quantum Chromodynamics (QCD) ensembles using an automatic windowing algorithm. The study examines the role of τint in time series analysis, emphasizing its significance for efficient sampling, error estimation, and algorithm optimization in lattice QCD simulations.

---

## Key Features
- **Concepts Explored**:
  - Autocorrelation time and its importance in time series analysis.
  - Integration of autocorrelation time for accurate statistical error estimation.
  - Optimization of window size for Monte Carlo simulations.
- **Algorithm**: Implementation of an automatic windowing algorithm to determine the optimal window size for τint calculations.
- **Lattice QCD Application**:
  - SU(3) Wilson gauge theory.
  - Observable: Polyakov loop.

---

## Methodology

### What is Autocorrelation Time?
Autocorrelation time (τ) measures the timescale over which a time series becomes uncorrelated. The integrated autocorrelation time (τint) is defined as:
$$
\tau_{\text{int}} = \frac{1}{2} + \sum_{t=1}^{T} \frac{C(t)}{C(0)}
$$
Where:
- $C(t)$: Autocorrelation function at lag $t$.
- $T$: Truncation lag where $C(t) \approx 0$.

### Automatic Windowing Algorithm
The algorithm selects an optimal window size $W$ for error estimation by:
1. Assuming $\tau \approx S \cdot \tau_{\text{int}}$, with $S$ typically set to 1.5.
2. Calculating estimators and verifying plateau behavior for $\tau_{\text{int}}(W)$.
3. Determining $W$ where the statistical errors stabilize.

---

## Experiments
### Data Details
- **Lattice Dimensions**: $24 \times 24 \times 24 \times 4$.
- **Gauge Coupling Range**: $\beta$ from 5.6 to 5.9 (non-linear steps).
- **Generated Configurations**: 1000 per value of $\beta$.
- **Observable**: Norm of the Polyakov loop.

### Visualization
Plots of autocorrelation trends and integrated τ values reveal:
- Configurations become more correlated near the phase transition ($\beta \in [5.68, 5.692]$).
- Optimal $W$ values calculated using Python implementation.

---

## Results
- Optimal window sizes ($W$) determined for each $\beta$ using the automatic windowing algorithm.
- Integrated autocorrelation times ($\tau_{\text{int}}$) calculated and visualized for all $\beta$ values.
- Observed stabilization of $\tau_{\text{int}}$ at the optimal $W$ values, validating the hypothesis parameter $S = 1.6$.

---

## Significance
### In Lattice QCD Simulations
1. **Efficient Sampling**:
   - Optimizes Monte Carlo sampling strategies.
   - Reduces computational costs.
2. **Statistical Accuracy**:
   - Improves precision of observable calculations by minimizing error bars.
3. **Algorithm Design**:
   - Enhances development of tailored algorithms for lattice QCD.

---

## Visuals
### Data Correlation
![Correlation Trends](https://github.com/user-attachments/assets/fdb05033-5c00-4a69-86fd-511b3f5aa9f0)

### Optimal Window Size
![Integrated Autocorrelation Time](https://github.com/user-attachments/assets/cfb69e79-fa28-4ec9-a5dd-0703414a5dec)


---

## Future Directions
- Apply the method to larger lattice sizes and other observables.
- Investigate the relationship between $S$ and phase transition dynamics.
- Develop advanced Python implementations to further automate the process.

---

## References
1. Wolff, U. *Monte Carlo errors with less errors*. arXiv:hep-lat/0306017.
2. Madras, N., Sokal, A.D. *The pivot algorithm: A highly efficient Monte Carlo method for the self-avoiding walk*. Journal of Statistical Physics, 1988.
