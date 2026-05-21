# Task 4- Literature Review batch 1
# Deliverable 1: Review Table
| Paper # | Topic | Title & Authors | Key Methodology / Core Idea | Strengths / Use Case | Limitations / Challenges |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | VQE | "A variational eigenvalue solver on a photonic quantum processor" (Peruzzo et al., 2014) | Combines quantum hardware for state preparation with classical optimization to find molecular energies. | Ideal for NISQ era devices; minimizes quantum coherence depth. | High measurement overhead; sensitive to hardware noise. |
| 2 | VQE | "The Variational Quantum Eigensolver: a review of methods and applications" (Tilly et al., 2022) | Synthesizes state-of-the-art VQE strategies, ansatz selections, and error mitigation routines. | Comprehensive guide for choosing error mitigation and optimizers. | Optimization landscapes still suffer from barren plateaus. |
| 3 | QML | "Quantum machine learning" (Biamonte et al., 2017) | Explores how quantum algorithms can accelerate classical machine learning tasks like matrix inversion. | Highlights exponential speedups for specific linear algebra tasks. | Requires fault-tolerant QRAM, which does not exist yet. |
| 4 | QML | "Power of data in quantum machine learning" (Huang et al., 2021) | Evaluates when quantum ML models provide a verifiable advantage over classical models. | Outlines precise mathematical bounds for true quantum advantage. | Classical models still outperform QML on many standard datasets. |
| 5 | Quantum Kernels | "Supervised learning with quantum-enhanced features" (Havlíček et al., 2019) | Maps data non-linearly into quantum state spaces where a linear classifier can separate it. | Provides a clear path to quantum supremacy using noisy hardware. | Finding the right feature map for specific data is difficult. |
| 6 | Quantum Kernels | "Quantum Machine Learning in Feature Hilbert Spaces" (Schuld & Killoran, 2019) | Frame quantum circuits explicitly as kernel estimators operating in high-dimensional spaces. | Unifies quantum circuit design with established classical kernel theory. | Kernel matrix evaluation scales poorly with large dataset sizes. |
| 7 | Hybrid Systems | "Variational Quantum Algorithms" (Cerezo et al., 2021) | Details the feedback loop where classical optimizers update parameterized quantum circuits. | Highly flexible; adaptable to optimization, chemistry, and ML. | Vulnerable to trainability issues like barren plateaus. |
| 8 | Hybrid Systems | "Quantum Computing in the NISQ era and beyond" (Preskill, 2018) | Defines the capabilities and hybrid limits of noisy intermediate-scale quantum devices. | Establishes realistic expectations for near-term hybrid algorithms. | Noise limits the depth of the hybrid quantum circuits. |
| 9 | PennyLane | "PennyLane: Automatic differentiation of quantum circuits" (Bergholm et al., 2018) | Introduces a software framework for hardware-yielding gradients of quantum circuits. | Seamlessly integrates quantum circuits with PyTorch and TensorFlow. | Simulating large quantum circuits classically is very slow. |
| 10 | PennyLane | "Evaluating analytic gradients on quantum hardware" (Schuld et al., 2019) | Explains the parameter-shift rule used by PennyLane to compute hardware gradients. | Does not require ancilla qubits; works directly on real hardware. | Requires twice as many circuit evaluations per parameter. |
## Deliverable 2:Research Summary notes
# Research Summary Notes

## 1. Variational Quantum Eigensolver (VQE)

### Paper 1: A variational eigenvalue solver on a photonic quantum processor (Peruzzo et al., 2014)
* **Objective:** To calculate the ground state energy of molecules using near-term quantum processors.
* **Key Findings:** Successfully demonstrated that a hybrid quantum-classical optimization loop allows shallow-depth circuits to accurately simulate molecular structures despite hardware noise.
* **PennyLane Relevance:** Serves as the fundamental algorithmic baseline for PennyLane’s `qchem` template library.

### Paper 2: The Variational Quantum Eigensolver: a review of methods and applications (Tilly et al., 2022)
* **Objective:** To catalog and evaluate modern advancements, ansatz configurations, and optimization strategies for VQE.
* **Key Findings:** Identifies that while VQE is highly flexible, performance heavily relies on mitigating trainability bottlenecks like barren plateaus through smart state initialization.
* **PennyLane Relevance:** Provides the core theoretical framework for choosing structural optimizers and ansatz layouts built into the platform.

---

## 2. Quantum Machine Learning (QML)

### Paper 3: Quantum machine learning (Biamonte et al., 2017)
* **Objective:** To outline the theoretical capabilities and limits of merging quantum computing with data analysis.
* **Key Findings:** Shows that quantum algorithms can achieve exponential speedups for linear algebra subroutines, but are severely throttled by the "data loading" bottleneck.
* **PennyLane Relevance:** Outlines the core quantum neural network (QNN) nodes that PennyLane translates into differentiable structures.

### Paper 4: Power of data in quantum machine learning (Huang et al., 2021)
* **Objective:** To mathematically define the exact boundaries where QML holds a verifiable advantage over classical ML.
* **Key Findings:** Proves that quantum speedup is realistic only when dealing with data generated from quantum distributions or highly entangled processes.
* **PennyLane Relevance:** Guides researchers on choosing datasets that will show performance gains when modeled with PennyLane classifiers.

---

## 3. Quantum Kernels

### Paper 5: Supervised learning with quantum-enhanced features (Havlíček et al., 2019)
* **Objective:** To construct and test a quantum feature map capable of mapping data into a complex quantum state space.
* **Key Findings:** Experimentally proved that non-linear, classical datasets become linearly separable when projected into a high-dimensional quantum Hilbert space.
* **PennyLane Relevance:** Maps directly onto PennyLane’s kernel optimization modules (`pennylane.kernels`).

### Paper 6: Quantum Machine Learning in Feature Hilbert Spaces (Schuld & Killoran, 2019)
* **Objective:** To mathematically unite the field of variational quantum circuits with established classical kernel methods.
* **Key Findings:** Demonstrated that any parameterized quantum circuit can be evaluated as a linear model operating implicitly on a quantum-generated kernel matrix.
* **PennyLane Relevance:** Provides the mathematical backing for utilizing standard machine learning frameworks (like Scikit-Learn) alongside PennyLane circuits.

---

## 4. Hybrid Systems

### Paper 7: Variational Quantum Algorithms (Cerezo et al., 2021)
* **Objective:** To provide a unified overview of algorithms that rely on co-processing between classical CPUs and quantum QPUs.
* **Key Findings:** Illustrates that hybrid architectures are the most viable pathway to achieving practical quantum utility prior to full fault-tolerant hardware.
* **PennyLane Relevance:** Establishes the core operational theory behind PennyLane's multi-device hybrid pipeline interfaces.

### Paper 8: Quantum Computing in the NISQ era and beyond (Preskill, 2018)
* **Objective:** To define the realistic capabilities and physical boundaries of Noisy Intermediate-Scale Quantum hardware.
* **Key Findings:** Coined the term "NISQ" and formalized why hybrid algorithms are necessary to error-mitigate physical systems containing fewer than a few hundred noisy qubits.
* **PennyLane Relevance:** Defines the targeted operational hardware space that PennyLane is engineered to maximize.

---

## 5. PennyLane Applications

### Paper 9: PennyLane: Automatic differentiation of quantum circuits (Bergholm et al., 2018)
* **Objective:** To introduce an open-source software framework capable of treating quantum circuits as differentiable nodes.
* **Key Findings:** Created a seamless ecosystem allowing quantum functions to be trained natively using PyTorch, TensorFlow, and JAX optimizers.
* **PennyLane Relevance:** This is the primary documentation and architectural design blueprint for the tool being evaluated.

### Paper 10: Evaluating analytic gradients on quantum hardware (Schuld et al., 2019)
* **Objective:** To implement a method for evaluating exact, analytic gradients of quantum circuits directly on real hardware.
* **Key Findings:** Standardized the "parameter-shift rule," which computes exact gradients by evaluating the circuit at shifted parameter values, bypassing noisy finite-difference methods.
* **PennyLane Relevance:** Describes the default method used by PennyLane whenever `diff_method="parameter-shift"` is compiled.
