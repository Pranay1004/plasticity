# Upsetting Process — Master Formula Sheet
**Manufacturing Technology · Metal Forming · Plasticity**

---

## 1. STRESS TENSOR

### Applied Stress (General 3D)
$$[\sigma_{ij}] = \begin{bmatrix} \sigma_{xx} & \tau_{xy} & \tau_{xz} \\ \tau_{yx} & \sigma_{yy} & \tau_{yz} \\ \tau_{zx} & \tau_{zy} & \sigma_{zz} \end{bmatrix}$$

**Symmetry condition:** τ_ij = τ_ji (6 independent components)

---

## 2. STRESS INVARIANTS (of σ_ij)

$$I_1 = \sigma_{xx} + \sigma_{yy} + \sigma_{zz} = \text{tr}(\sigma)$$

$$I_2 = \sigma_{xx}\sigma_{yy} + \sigma_{yy}\sigma_{zz} + \sigma_{zz}\sigma_{xx} - \tau_{xy}^2 - \tau_{yz}^2 - \tau_{zx}^2$$

$$I_3 = \det(\sigma_{ij})$$

**Characteristic equation:**
$$\lambda^3 - I_1\lambda^2 + I_2\lambda - I_3 = 0$$

---

## 3. HYDROSTATIC & DEVIATORIC TENSORS

### Mean (Hydrostatic) Stress
$$\sigma_m = \frac{I_1}{3} = \frac{\sigma_{xx}+\sigma_{yy}+\sigma_{zz}}{3}$$

### Deviatoric Stress Tensor
$$S_{ij} = \sigma_{ij} - \sigma_m\delta_{ij}$$

$$[S_{ij}] = \begin{bmatrix} \sigma_{xx}-\sigma_m & \tau_{xy} & \tau_{xz} \\ \tau_{yx} & \sigma_{yy}-\sigma_m & \tau_{yz} \\ \tau_{zx} & \tau_{zy} & \sigma_{zz}-\sigma_m \end{bmatrix}$$

**Property:** tr(S) = S_xx + S_yy + S_zz = 0 always

---

## 4. DEVIATORIC INVARIANTS (of S_ij)

$$J_1 = \text{tr}(S) = 0 \quad \text{(always)}$$

$$J_2 = -\frac{1}{2}S_{ij}S_{ij} = -\frac{1}{2}\left(S_{xx}^2 + S_{yy}^2 + S_{zz}^2 + 2S_{yz}^2 + 2S_{xz}^2 + 2S_{xy}^2\right)$$

$$J_3 = \det(S_{ij})$$

---

## 5. PRINCIPAL STRESSES

Eigenvalues of σ_ij. Solve:
$$\det(\sigma_{ij} - \lambda I) = 0 \implies \lambda^3 - I_1\lambda^2 + I_2\lambda - I_3 = 0$$

Ordered convention: **σ₁ ≥ σ₂ ≥ σ₃**

### Principal Directions (Eigenvectors)
For each eigenvalue λ_k, solve $(\sigma_{ij} - \lambda_k\delta_{ij})n_j = 0$ and normalize.

---

## 6. MOHR'S CIRCLE (2D, for any plane i–j)

$$C = \frac{\sigma_i + \sigma_j}{2}, \qquad R = \sqrt{\left(\frac{\sigma_i - \sigma_j}{2}\right)^2 + \tau_{ij}^2}$$

$$\sigma_{1,2} = C \pm R$$

$$\tau_{max} = R$$

$$2\theta = \tan^{-1}\left(\frac{2\tau_{ij}}{\sigma_i - \sigma_j}\right)$$

---

## 7. FLOW CONDITION (Yield Criteria)

### Von Mises
$$k_f^{VM} = \sqrt{\frac{1}{2}\left[(\sigma_1-\sigma_2)^2 + (\sigma_2-\sigma_3)^2 + (\sigma_3-\sigma_1)^2\right]}$$

Equivalent form using stress components:
$$k_f^{VM} = \sqrt{\frac{1}{2}\left[(\sigma_{xx}-\sigma_{yy})^2 + (\sigma_{yy}-\sigma_{zz})^2 + (\sigma_{zz}-\sigma_{xx})^2 + 6(\tau_{xy}^2+\tau_{yz}^2+\tau_{zx}^2)\right]}$$

Using deviatoric invariant:
$$k_f^{VM} = \sqrt{-3J_2} = \sqrt{\frac{3}{2}S_{ij}S_{ij}}$$

Flow condition: $J_2 = -\frac{k_f^2}{3}$ or $S_{ij}S_{ij} = \frac{2}{3}k_f^2$

### Tresca
$$k_f^{Tr} = \sigma_1 - \sigma_3 \quad \text{(max principal stress difference)}$$

### Error Between Criteria
$$\text{error} = \frac{k_f^{Tr} - k_f^{VM}}{k_f^{Tr}} \times 100\% \quad \text{(must be < 15%)}$$

---

## 8. STRAIN RATE TENSOR

$$\dot{\varepsilon}_{ij} = \frac{1}{2}\left(\frac{\partial V_i}{\partial x_j} + \frac{\partial V_j}{\partial x_i}\right)$$

$$[\dot{\varepsilon}_{ij}] = \begin{bmatrix} \partial V_x/\partial x & \frac{1}{2}(\partial V_x/\partial y + \partial V_y/\partial x) & \frac{1}{2}(\partial V_x/\partial z + \partial V_z/\partial x) \\ \cdot & \partial V_y/\partial y & \frac{1}{2}(\partial V_y/\partial z + \partial V_z/\partial y) \\ \cdot & \cdot & \partial V_z/\partial z \end{bmatrix}$$

### Incompressibility (Volume Constancy)
$$\dot{\varepsilon}_{xx} + \dot{\varepsilon}_{yy} + \dot{\varepsilon}_{zz} = 0 \iff \frac{\partial V_x}{\partial x} + \frac{\partial V_y}{\partial y} + \frac{\partial V_z}{\partial z} = 0$$

### Normal Strain Rate from Ram
$$\dot{\varepsilon}_{zz} = -\frac{V_0}{H} \quad \text{(fixed bottom, height H)}$$
$$\dot{\varepsilon}_{zz} = -\frac{V_0}{h} \quad \text{(free both ends, half-height h)}$$

---

## 9. LÉVY-MISES FLOW RULE

$$\dot{\varepsilon}_{ij} = \lambda S_{ij}$$

where λ is the plastic multiplier:
$$\lambda = \frac{\dot{\varepsilon}_{ii}^{normal}}{S_{ii}^{corresponding}} = \frac{\dot{\bar{\varepsilon}}}{\sqrt{\frac{2}{3}S_{ij}S_{ij}}}$$

Shear strain rate from shear stress:
$$\dot{\varepsilon}_{yz} = \lambda S_{yz}$$

---

## 10. VELOCITY FIELD (Linear, Homogeneous)

General structure for upsetting along Z with τ_zy friction:

$$V_z = \dot{\varepsilon}_{zz} \cdot z$$

$$V_x = \dot{\varepsilon}_{xx} \cdot x$$

$$V_y = \dot{\varepsilon}_{yy} \cdot y + 2\dot{\varepsilon}_{yz} \cdot z$$

> The factor 2ε̇_yz·z arises because $\partial V_y/\partial z = 2\dot{\varepsilon}_{yz}$ (the full shear velocity gradient is assigned to V_y).

**Boundary conditions:**
- Fixed bottom: V_z(z=0) = 0 ✓; V_z(z=H) = –V₀
- Free both ends: V_z(z=±h) = ∓V₀; V_y(0,0,0) = 0

---

## 11. PRINCIPAL STRAIN RATES

Eigenvalues of $[\dot{\varepsilon}_{ij}]$. If X is decoupled:
$$\dot{\varepsilon}_x^p = \dot{\varepsilon}_{xx}$$

For Y–Z sub-block:
$$\dot{\varepsilon}_{1,3}^p = \frac{\dot{\varepsilon}_{yy} + \dot{\varepsilon}_{zz}}{2} \pm \sqrt{\left(\frac{\dot{\varepsilon}_{yy}-\dot{\varepsilon}_{zz}}{2}\right)^2 + \dot{\varepsilon}_{yz}^2}$$

**Check:** $\dot{\varepsilon}_1^p + \dot{\varepsilon}_2^p + \dot{\varepsilon}_3^p = 0$

---

## 12. EFFECTIVE (EQUIVALENT) STRAIN RATE

$$\dot{\bar{\varepsilon}} = \sqrt{\frac{2}{3}\dot{\varepsilon}_{ij}\dot{\varepsilon}_{ij}}$$

Expanded (using principal strain rates):
$$\dot{\bar{\varepsilon}} = \sqrt{\frac{2}{3}\left[(\dot{\varepsilon}_1^p)^2 + (\dot{\varepsilon}_2^p)^2 + (\dot{\varepsilon}_3^p)^2\right]}$$

Using tensor components directly:
$$\dot{\bar{\varepsilon}} = \sqrt{\frac{2}{3}\left[\dot{\varepsilon}_{xx}^2 + \dot{\varepsilon}_{yy}^2 + \dot{\varepsilon}_{zz}^2 + 2\dot{\varepsilon}_{yz}^2 + 2\dot{\varepsilon}_{xz}^2 + 2\dot{\varepsilon}_{xy}^2\right]}$$

---

## 13. POWER — EXTERNAL (COMPRESSION)

### Fixed bottom (one-sided):
$$P_{comp} = |\sigma_{load}| \times A_{face} \times V_0$$

### Free both ends (two-sided, symmetric):
$$P_{comp} = 2 \times |\sigma_{load}| \times A_{face} \times V_0$$

### Per unit volume:
$$\dot{w}_{comp} = \frac{P_{comp}}{V_{ol}}$$

---

## 14. POWER — EXTERNAL (SHEAR, by Integration)

For shear τ_zy on the loaded top face (z = H or z = h):

$$P_{shear} = \iint_{A_{face}} \tau_{zy} \cdot V_y(x, y, z_{face}) \, dx \, dy$$

Since $V_y = \dot{\varepsilon}_{yy}\cdot y + 2\dot{\varepsilon}_{yz}\cdot z_{face}$, and the integral of y over symmetric limits is zero:

$$P_{shear} = \tau_{zy} \cdot (2\dot{\varepsilon}_{yz}\cdot z_{face}) \cdot A_{face}$$

Fully symmetric (two faces contribute):
$$P_{shear,total} = 2 \times P_{shear,top}$$

**General integration formula:**
$$\int_{-b}^{+b} \tau \cdot (\alpha y + \beta) \, dy = \tau\left[\frac{\alpha y^2}{2} + \beta y\right]_{-b}^{+b} = \tau \cdot 2\beta b \quad (\text{odd } y\text{-term vanishes})$$

---

## 15. POWER — INTERNAL (Volume Integral)

$$\dot{w}_{int} = \sigma_{ij}\dot{\varepsilon}_{ij} \quad \text{(per unit volume)}$$

Expanded for upsetting with one shear:
$$\dot{w}_{int} = \sigma_{zz}\dot{\varepsilon}_{zz} + 2\tau_{yz}\dot{\varepsilon}_{yz}$$

For full tensor:
$$\dot{w}_{int} = \sigma_{xx}\dot{\varepsilon}_{xx} + \sigma_{yy}\dot{\varepsilon}_{yy} + \sigma_{zz}\dot{\varepsilon}_{zz} + 2\tau_{xy}\dot{\varepsilon}_{xy} + 2\tau_{yz}\dot{\varepsilon}_{yz} + 2\tau_{zx}\dot{\varepsilon}_{zx}$$

$$P_{int} = \dot{w}_{int} \times V_{ol}$$

**Consistency check:** P_ext = P_int (must hold for compatible velocity field)

---

## 16. POWER — PRINCIPAL STRESS × PRINCIPAL STRAIN RATE

$$P = V_{ol}\left(\sigma_1\dot{\varepsilon}_1^p + \sigma_2\dot{\varepsilon}_2^p + \sigma_3\dot{\varepsilon}_3^p\right)$$

This is the diagonal form of the double contraction — valid only in the principal frame.

---

## 17. EQUIVALENT (VON MISES) STRESS

$$\bar{\sigma} = k_f^{VM} = \sqrt{\frac{1}{2}\left[(\sigma_1-\sigma_2)^2+(\sigma_2-\sigma_3)^2+(\sigma_3-\sigma_1)^2\right]}$$

**Consistency check:**
$$\bar{\sigma} \cdot \dot{\bar{\varepsilon}} = \dot{w}_{int} \text{ (power density)}$$

---

## 18. UPPER BOUND THEOREM

$$\dot{W}_{UB} = \bar{\sigma} \cdot \dot{\bar{\varepsilon}} \quad \text{(per unit volume)}$$

$$P_{UB} = \dot{W}_{UB} \times V_{ol}$$

**Conditions for valid upper bound:**
1. Velocity field is kinematically admissible (satisfies BCs)
2. Incompressibility satisfied (∇·V = 0)
3. No velocity discontinuities (or their contribution is added separately)

> Upper bound ≥ actual power. Equality holds when the assumed field is the exact solution.

**Cannot use frictionless formula** when shear/friction is present — must include shear power explicitly.

---

## 19. QUICK REFERENCE — SIGN CONVENTIONS

| Convention | Rule |
|-----------|------|
| Compressive stress | Negative (σ = –|σ|) |
| Tensile stress | Positive |
| Shear τ_ij | On face with outward normal i, acts in direction j |
| Conjugate pair | τ_ij = τ_ji (stress symmetry) |
| Strain rate | ε̇_zz < 0 = compression; ε̇_xx, ε̇_yy > 0 = lateral spread |
| Velocity | V_z < 0 at top face (ram going down); V_z > 0 at bottom (free) |

---

## 20. DIMENSIONAL CHECK TABLE

| Quantity | Units (consistent system) |
|----------|--------------------------|
| Stress σ, τ | force/area |
| Strain rate ε̇ | 1/time (s⁻¹) |
| Velocity V | length/time |
| Power/volume | stress × strain rate = force/(area·time) |
| Total power | force × velocity |

---

*Formula sheet covers both Q1 (20×20×50, τ_zy=5) and Q2 (8×4×2, τ_yz=2) problems completely.*
