# Robust Nonlinear Predictive Control of Biological Cellular Dynamics via Latent Neural ODEs

## 🔬 Overview
This repository contains the implementation of a robust control framework designed to model complex biological cellular dynamics[cite: 1]. By leveraging Latent Ordinary Differential Equation Networks (Neural ODEs), high-dimensional transcriptomic data is mapped into a tractable continuous-time latent space[cite: 1]. The resulting model acts as a robust dynamic attractor, successfully rejecting initial condition perturbations while perfectly reconstructing the geometric manifold of cell differentiation.

## ✨ Key Features & Control Strategies
* **Latent Neural ODE Architecture:** Utilizes an Encoder-ODE-Decoder structure to bypass noise, extreme low-pass filtering behavior, and the "MSE Trap" inherent in high-dimensional biological data.
* **Advanced Data Engineering:** Employs Principal Component Analysis (PCA) for noise filtration and the Leiden algorithm for topological manifold surgery. A continuous temporal axis is extracted using Diffusion Pseudotime (DPT).
* **Two-Point Boundary Value Problem (BVP):** The control architecture is formulated as a BVP to prevent trajectory attenuation, enforcing precise initial and terminal state tracking through anchored geometric constraints.
* **Lyapunov-Based Robust Stabilization:** Implements eigenvalue regularization using second-order gradients derived from the mathematically extracted Jacobian matrix. This forces dominant poles into the left-half of the complex plane ($Re(\lambda) < 0$), ensuring strict asymptotic stability.

## 📊 Empirical Results & Robustness
The model successfully bridges classical nonlinear control theory with modern deep learning. Robustness stress tests—conducted by injecting artificial Gaussian noise into the initial biological state—empirically validate the existence of a stable basin of attraction. The dynamic vector field autocorrects the perturbed trajectory, demonstrating absolute resilience against initial condition uncertainty and stochastic sequencer dropout noise.

### Phase Portrait Demonstrations
*(Note: You can view the generated phase portraits in the repository showcasing the system's dynamic tracking and robustness.)*
- `Phase Portrait - Neural ODE with Two-Point Boundary Constraints.png`
- `Phase Portrait-Robustness Test & Basin of Attraction.png`

## 📖 Comprehensive Report
For an in-depth mathematical breakdown of the Jacobian linearization, Taylor Series Expansion, and the closed-loop optimization dynamics, please refer to the complete engineering report included in this repository: [`Report.pdf`](./Report.pdf).

## 👨‍💻 Author
**Amirali OliaeiMehr**  
Department of Electrical Engineering, Control Systems Specialization  
Amirkabir University of Technology
