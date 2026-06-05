# VQE Convergence Analysis

An optimization baseline was established using simulated 4-asset portfolios over 120 structural iterations.

#### Key Performance Findings

* Optimizer Stability: `SPSA` outperformed `COBYLA` in noise-resilient convergence simulation trials, demonstrating robustness against sampling variance.
* Loss Evaluation: The convergence behavior steadily advanced to a stable minimization boundary, establishing a benchmark optimal portfolio variance value of $$ $0.042$ $$.

#### Experiment Metadata Registry

All algorithmic runs are audited using MLflow Tracking. Registered execution components securely capture parameter weights, execution timelines, loss progression plots (`loss_plot.png`), and structural circuit diagrams (`vqe_ansatz.png`) into a single queryable database dashboard interface.
