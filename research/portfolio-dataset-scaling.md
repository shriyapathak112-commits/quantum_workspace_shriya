# Portfolio dataset scaling

````
## Overview
Quantum hardware constraints (qubit limitations and noise) require deliberate data reduction strategies. This page outlines how we scale large financial datasets down to match current NISQ-era hardware capacity.

## Reduction & Clustering Strategies
1. **Principal Component Analysis (PCA)**: Compressing asset features into orthogonal dimensions.
2. **Hierarchical Risk Parity (HRP) Clustering**: Using tree-based clustering to select representative prototype assets from highly correlated industrial sectors.
3. **Qubit Mapping**: Dynamically allocating $N$ filtered target assets to an equivalent $N$-qubit formulation on a quantum processor.
```
````
