# VQE Fundamentals

The Variational Quantum Eigensolver (VQE) is a hybrid quantum-classical algorithm designed to find the ground state energy (lowest eigenvalue) of a given Hamiltonian $$ $\hat{H}$ $$. It operates on the Variational Principle, which guarantees that the expectation value of a Hermitian operator $$ $\hat{H}$ $$ with respect to any parameterized quantum state $$ $|\psi(\theta)\rangle$ $$ is always greater than or equal to the true ground state energy $$ $E_0$ $$:

\$$\langle\hat{H}\rangle\_{\theta} = \frac{\langle\psi(\theta)|\hat{H}|\psi(\theta)\rangle}{\langle\psi(\theta)|\psi(\theta)\rangle} \ge E\_0\$$

#### The Hybrid Optimization Loop

1. Quantum Processor (QPUs/Simulators): Prepares the parameterized ansatz state $$ $|\psi(\theta)\rangle$ $$ and measures the expectation value $$ $\langle\hat{H}\rangle_{\theta}$ $$.
2. Classical Optimizer: Receives the energy estimate, evaluates convergence, and updates the parameters $$ $\theta$ $$ using algorithms like SPSA or COBYLA to minimize the energy objective.
