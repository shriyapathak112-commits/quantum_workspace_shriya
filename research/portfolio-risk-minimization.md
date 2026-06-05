# Portfolio Risk Minimization

In financial engineering, the Modern Portfolio Theory (MPT) framework seeks to minimize portfolio risk (variance) for a targeted budget or asset allocation strategy.

We map the classical portfolio variance problem into a quantum formulation by mapping a selection vector $$ $x \in \{0, 1\}^n$ $$ into an Ising Hamiltonian. Given a covariance matrix $$ $\Sigma$ $$ and a risk-aversion factor $$ $q$ $$, the objective operator is expressed as:

$$$
$$\hat{H} = q \sum_{i,j} \Sigma_{ij} \hat{Z}_i \hat{Z}_j$$
$$$

Where $$ $\hat{Z}_i$ $$ is the Pauli-Z operator acting on qubit $$ $i$ $$. Finding the ground state of this Hamiltonian explicitly yields the asset combination that minimizes the portfolio's absolute risk profile.
