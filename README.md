#### Black-Box Attribute Inference (Discrete & Continuous)

Technical reports, experimental results, and reproducible PyTorch implementation investigating **attribute inference attacks under strict zero-leakage constraints** (no access to ground-truth population priors, target distribution moments, or victim internal gradients). 

#### Repository Contents

* **[TU_Wien_Attribute_Inference_Report.pdf](./TU_Wien_Attribute_Inference_Report.pdf)** | Original research coursework report (*TU WIEN, E192 / 184.702, Winter Semester 2025*, co-authored with Fausto Morando) covering confidence-based discrete MAP estimation, Riemannian/JSD centroid evaluation and categorical pseudo-regression limits.
* **[Continuous_Attribute_Inference_Report.pdf](./Continuous_Attribute_Inference_Report.pdf)** | Independent follow-up extending attribute inference to continuous black-box regressors via Owen-scrambled Sobol' QMC surrogates, Conditional WGAN-GP priors and Jacobian-regularized gradient inversion.
* **[continuous_attribute_inference.ipynb](./continuous_attribute_inference.ipynb)** | Clean, self-contained PyTorch notebook reproducing Stage 0 surrogate alignment, Stage 1 auto-balanced WGAN-GP manifold learning, Stage 2 test-time gradient inversion and the ε-uncertainty resilience sweep.

#### Key Highlights & Findings

#### 1. Discrete Manifold Mapping *(TU WIEN Coursework Extension)*

* Replaced unrealistic population-prior assumptions with query-efficient **Owen-scrambled Sobol' Quasi-Monte Carlo (QMC)** probing and dynamic intra-batch **Jensen-Shannon Divergence** centroid evaluation.

#### 2. Continuous Manifold Mapping *(Independent Extension)*

* **Topological Surrogacy & Prior Learning:** Trained a differentiable surrogate via first-order Jacobian matching over ε-perturbed QMC bounds alongside a **1-Lipschitz Conditional WGAN-GP** with latent feature matching and homoscedastic loss balancing.
* **Test-Time Gradient Inversion:** Achieved strong variance capture on causal attributes (**R² = 0.53 ID / 0.47 OOD**), while characterizing why non-injective mappings cause low-signal behavioral channels to saturate despite global Earth Mover's Distance convergence.
* **Stochastic Smoothing & Open Direction:** Observed that mild boundary perturbations (**ε ∈ (0,0.25]**) act as implicit adversarial regularization, spiking recovery up to **R² = 0.84 OOD**. Currently investigating unsupervised, validation-free geometric discriminants to isolate well-conditioned surrogates without ground-truth leakage.

#### Kaggle Dataset AI Impact on Students [https://www.kaggle.com/datasets/laveshjadon/ai-impact-on-students]
Preliminary Benchmark (dataset selected for its cleanly separable causal vs non injective behavioral features)
After finalizing pipeline will test it on standard tabular privacy benchmarks (z.B. UCI Adult, ACS Folktables)

#### Key Preliminary Figures

#### Stage 1: Conditional WGAN-GP Manifold Topology vs. Population
<img width="1722" height="472" alt="WGAN" src="https://github.com/user-attachments/assets/d9cc052c-2e3f-4b89-86a5-6d52b41780b0" />

#### Appendix: Reconstruction Resilience Under Target-Bound Uncertainty (ε)
<img width="1277" height="470" alt="epsillon" src="https://github.com/user-attachments/assets/898991ba-85b9-4c88-8e32-9ab2dc2e5c11" />
 

#### Author & Contact

**Stefanos (Stephan) Drepenteris** | School of Electrical and Computer Engineering, National Technical University of Athens (NTUA)
Email: el22123@mail.ntua.gr | stephandrepenteris@gmail.com
