# Ansatz Design

The choice of ansatz determines the search space of the variational state $$ $|\psi(\theta)\rangle$ $$. During Week 3, we evaluated two primary structures for our 10-asset universe:

#### Hardware-Efficient Ansatz (HEA)

* Structure: Composed of alternating layers of single-qubit rotations ($$ $R_y, R_z$ $$) and standard entangling gates (CNOTs) matching the native device topology.
* Pros: Low circuit depth; easily executed on current NISQ hardware.
* Cons: Prone to barren plateaus (vanishing gradients) as qubit counts scale.

#### TwoLocal Ansatz

* Structure: A parameterizable circuit containing reusable rotation layers and entanglement configurations.
* Implementation: For our optimization benchmarks, we configured a `TwoLocal` circuit with linear entanglement topology using $$ $R_y$ $$ variational gates:

Python

```
from qiskit.circuit.library import TwoLocal
ansatz = TwoLocal(num_qubits=4, rotation_blocks=
```
