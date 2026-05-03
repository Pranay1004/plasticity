# Upsetting Process — Complete Solution
**Course:** Manufacturing Technology | **Topic:** Metal Forming, Plasticity

---

## QUESTION (Full Statement)

Fastener heads are manufactured using an **upsetting process** in which a block of **20 × 20 × 50 units** (Length × Width × Height) is compressed using a bolt header machine. The ram compresses the workpiece at a velocity of **2 units** in the **Z-direction** (uniaxial compressive stress = **10 units**). Friction between the platen and workpiece develops a shear stress of **5 units** in the Z-plane along the Y-direction (τ_zy = 5).

**Draw the free body diagram and determine:**

| Part | Task | Marks |
|------|------|-------|
| (a) | Applied stress tensor | 1 |
| (b) | Stress invariants (I₁, I₂, I₃) | 2 |
| (c) | Principal stresses, hydrostatic stress, stress deviator tensor | 5 |
| (d) | Mohr's circle | 4 |
| (e) | Flow condition — k_f via Von Mises and Tresca | 3 |
| (f) | Strain rate tensor and principal strain rate tensor | 4 |
| (g) | Equations for velocity fields | 4 |
| (h) | Velocity at coordinates (0,0,0), (0,0,5), (10,10,20) | 3 |
| (i) | Power due to external stresses (compression + shear) | 4 |
| (j) | Power due to internal stresses | 4 |
| (k) | Power via product of principal stress × principal strain rate | 2 |
| (l) | Equivalent stress and effective strain | 2 |
| (m) | Power per unit volume — upper bound solution method | 2 |

**Total: 40 marks**

---

## PROBLEM SETUP

### Given Data

| Quantity | Value |
|----------|-------|
| Dimensions (L × W × H) | 20 × 20 × 50 |
| Half-dimensions | ±10 in X, ±10 in Y, 0 to 50 in Z |
| Ram velocity | V₀ = 2 units (downward, –Z) |
| Compressive stress | σ_z = –10 units |
| Friction shear stress | τ_zy = τ_yz = 5 units |
| Boundary condition | Bottom face **fixed** → Z limits: 0 to H |

### Coordinate System
- X: length direction (–10 to +10)
- Y: width direction (–10 to +10)
- Z: compression direction (0 to 50); ram acts from top

### Free Body Diagram Description
- Top face (Z = 50): σ_z = –10 (compressive, downward), τ_zy = 5 (shear along Y)
- Bottom face (Z = 0): **fixed** (platen reaction)
- Lateral faces: free surfaces (zero traction, assuming no lateral friction)

---

## (a) Applied Stress Tensor — [1 Mark]

Only σ_z and τ_zy = τ_yz = 5 are non-zero. By symmetry of the stress tensor, τ_zy = τ_yz.

$$[\sigma] = \begin{bmatrix} \sigma_{xx} & \tau_{xy} & \tau_{xz} \\ \tau_{yx} & \sigma_{yy} & \tau_{yz} \\ \tau_{zx} & \tau_{zy} & \sigma_{zz} \end{bmatrix} = \begin{bmatrix} 0 & 0 & 0 \\ 0 & 0 & 5 \\ 0 & 5 & -10 \end{bmatrix}$$

> **Note:** Compressive stress is negative by sign convention. All other components are zero since no lateral loads or X-direction friction are applied.

---

## (b) Stress Invariants — [2 Marks]

The three principal invariants are derived from the characteristic equation:
$$\sigma^3 - I_1\sigma^2 + I_2\sigma - I_3 = 0$$

### First Invariant — I₁ (Trace)
$$I_1 = \sigma_{xx} + \sigma_{yy} + \sigma_{zz} = 0 + 0 + (-10)$$
$$\boxed{I_1 = -10}$$

### Second Invariant — I₂
$$I_2 = (\sigma_{xx}\sigma_{yy} + \sigma_{yy}\sigma_{zz} + \sigma_{zz}\sigma_{xx}) - (\tau_{xy}^2 + \tau_{yz}^2 + \tau_{zx}^2)$$
$$= (0 \cdot 0) + (0 \cdot (-10)) + ((-10) \cdot 0) - (0 + 25 + 0)$$
$$\boxed{I_2 = -25}$$

### Third Invariant — I₃ (Determinant)
$$I_3 = \det[\sigma] = 0(0 \cdot (-10) - 5 \cdot 5) - 0 + 0$$
$$\boxed{I_3 = 0}$$

> **Physical meaning:** I₁ represents volumetric stress; I₂ relates to shear energy; I₃ = 0 confirms one principal stress is zero.

---

## (c) Principal Stresses, Hydrostatic Stress, Deviatoric Tensor — [5 Marks]

### Principal Stresses

Using the characteristic equation with I₁ = –10, I₂ = –25, I₃ = 0:
$$\sigma^3 + 10\sigma^2 - 25\sigma = 0$$
$$\sigma(\sigma^2 + 10\sigma - 25) = 0$$

**Root 1:** σ₃ = 0

**Roots 2 & 3** (quadratic formula):
$$\sigma = \frac{-10 \pm \sqrt{100 + 100}}{2} = \frac{-10 \pm 10\sqrt{2}}{2} = -5 \pm 5\sqrt{2}$$

$$\boxed{\sigma_1 = -5 + 5\sqrt{2} \approx +2.07}$$
$$\boxed{\sigma_2 = -5 - 5\sqrt{2} \approx -12.07}$$
$$\boxed{\sigma_3 = 0}$$

> Ordered as σ₁ > σ₂ > σ₃ → **+2.07 > 0 > –12.07** ... wait, reordering correctly:
> σ₁ = +2.07, σ₂ = 0, σ₃ = –12.07 *(largest to smallest)*

### Hydrostatic (Mean) Stress
$$\sigma_m = \frac{I_1}{3} = \frac{-10}{3} = -3.33 \text{ units}$$

**Hydrostatic tensor:**
$$[\sigma_H] = \begin{bmatrix} -3.33 & 0 & 0 \\ 0 & -3.33 & 0 \\ 0 & 0 & -3.33 \end{bmatrix}$$

### Stress Deviator Tensor

$$[S] = [\sigma] - [\sigma_H]$$

$$[S] = \begin{bmatrix} 0-(-3.33) & 0 & 0 \\ 0 & 0-(-3.33) & 5 \\ 0 & 5 & -10-(-3.33) \end{bmatrix} = \begin{bmatrix} 3.33 & 0 & 0 \\ 0 & 3.33 & 5 \\ 0 & 5 & -6.67 \end{bmatrix}$$

> **Verification:** trace[S] = 3.33 + 3.33 – 6.67 = 0 ✓ (deviatoric tensor is always traceless)

---

## (d) Mohr's Circle — [4 Marks]

Mohr's circle is drawn for the **Y–Z plane** (the plane containing the active shear τ_zy = 5):

| Quantity | Formula | Value |
|----------|---------|-------|
| σ_A (on Y-face) | σ_yy | 0 |
| σ_B (on Z-face) | σ_zz | –10 |
| τ_AB | τ_yz | 5 |

### Centre of Circle
$$C = \frac{\sigma_A + \sigma_B}{2} = \frac{0 + (-10)}{2} = -5$$

### Radius
$$R = \sqrt{\left(\frac{\sigma_A - \sigma_B}{2}\right)^2 + \tau_{AB}^2} = \sqrt{(-5)^2 + 5^2} = \sqrt{50} = 5\sqrt{2} \approx 7.07$$

### Principal Stresses (from Mohr's Circle)
$$\sigma_{1,2} = C \pm R = -5 \pm 7.07$$
$$\sigma_1 = +2.07, \quad \sigma_2 = -12.07$$

### Maximum Shear Stress
$$\tau_{max} = R = 5\sqrt{2} \approx 7.07 \text{ units}$$

### Angle of Principal Plane
$$2\theta = \tan^{-1}\left(\frac{2\tau_{AB}}{\sigma_A - \sigma_B}\right) = \tan^{-1}\left(\frac{2 \times 5}{0 - (-10)}\right) = \tan^{-1}(1) = 45°$$
$$\theta = 22.5°$$

### Mohr's Circle (ASCII Sketch)

```
        τ
        |
   7.07 +       * A(0, +5)
        |      /|
        |    /  |
        |  /    |
--------+--------+--------+------ σ
      -12.07   -5        +2.07
        |  \    |
        |    \  |
        |      \|
  -7.07 +       * B(-10, -5)
        |
        
        C = -5, R = 7.07
```

---

## (e) Flow Condition — k_f via Von Mises and Tresca — [3 Marks]

Using principal stresses: σ₁ = +2.07, σ₂ = 0, σ₃ = –12.07

### Von Mises Criterion
$$k_f^{VM} = \sqrt{\frac{1}{2}\left[(\sigma_1 - \sigma_2)^2 + (\sigma_2 - \sigma_3)^2 + (\sigma_3 - \sigma_1)^2\right]}$$

$$= \sqrt{\frac{1}{2}\left[(2.07 - 0)^2 + (0 - (-12.07))^2 + (-12.07 - 2.07)^2\right]}$$

$$= \sqrt{\frac{1}{2}\left[4.28 + 145.68 + 199.96\right]} = \sqrt{\frac{349.92}{2}} = \sqrt{174.96}$$

$$\boxed{k_f^{VM} \approx 13.23 \text{ units}}$$

### Tresca Criterion
$$k_f^{Tr} = \sigma_{max} - \sigma_{min} = \sigma_1 - \sigma_3 = 2.07 - (-12.07)$$

$$\boxed{k_f^{Tr} = 14.14 = 10\sqrt{2} \text{ units}}$$

> **Note:** k_f^{VM} / k_f^{Tr} = 13.23/14.14 = 0.935. Von Mises is always ≤ Tresca; the ratio approaches 1 for pure shear and 0.866 for uniaxial tension. Tresca is more conservative (always predicts earlier yield).

---

## (f) Strain Rate Tensor and Principal Strain Rates — [4 Marks]

### Normal Strain Rates

From kinematics of upsetting (ram velocity V₀ = 2, height H = 50):

$$\dot{\varepsilon}_{zz} = -\frac{V_0}{H} = -\frac{2}{50} = -0.04 \text{ s}^{-1}$$

**Volume constancy** (incompressibility condition):
$$\dot{\varepsilon}_{xx} + \dot{\varepsilon}_{yy} + \dot{\varepsilon}_{zz} = 0$$

By symmetry (square cross-section, 20 × 20):
$$\dot{\varepsilon}_{xx} = \dot{\varepsilon}_{yy} = +\frac{0.04}{2} = +0.02 \text{ s}^{-1}$$

### Shear Strain Rates (via Lévy-Mises Flow Rule)

The Lévy-Mises rule: $\dot{\varepsilon}_{ij} = \lambda S_{ij}$

Finding λ from the normal component:
$$\lambda = \frac{\dot{\varepsilon}_{zz}}{S_{zz}} = \frac{-0.04}{-6.67} = 0.006$$

$$\dot{\varepsilon}_{yz} = \lambda \cdot S_{yz} = 0.006 \times 5 = 0.03 \text{ s}^{-1}$$

All other shear strain rates = 0 (since S_xy = S_xz = 0).

### Strain Rate Tensor
$$[\dot{\varepsilon}] = \begin{bmatrix} 0.02 & 0 & 0 \\ 0 & 0.02 & 0.03 \\ 0 & 0.03 & -0.04 \end{bmatrix}$$

**Verification:** trace = 0.02 + 0.02 – 0.04 = 0 ✓

### Principal Strain Rates

The X-direction is already principal (no off-diagonal terms in X-row/column):
$$\dot{\varepsilon}_{x}^{p} = 0.02$$

For the Y–Z sub-block:
$$\dot{\varepsilon}_{1,2}^{YZ} = \frac{(0.02 + (-0.04))}{2} \pm \sqrt{\left(\frac{0.02 - (-0.04)}{2}\right)^2 + 0.03^2}$$

$$= -0.01 \pm \sqrt{0.03^2 + 0.03^2} = -0.01 \pm \sqrt{0.0018} = -0.01 \pm 0.0424$$

$$\boxed{\dot{\varepsilon}_1^p = +0.0324, \quad \dot{\varepsilon}_2^p = +0.02, \quad \dot{\varepsilon}_3^p = -0.0524}$$

**Check:** 0.0324 + 0.02 – 0.0524 = 0 ✓

---

## (g) Velocity Field Equations — [4 Marks]

For a linear (homogeneous) velocity field, $V_i = \dot{\varepsilon}_{ij} \cdot x_j$ where the shear gradient is assigned to one velocity component:

$$\frac{\partial V_z}{\partial z} = \dot{\varepsilon}_{zz} = -0.04 \implies V_z = -0.04z$$

$$\frac{\partial V_x}{\partial x} = \dot{\varepsilon}_{xx} = +0.02 \implies V_x = +0.02x$$

For V_y: normal + shear contribution (shear gradient $\partial V_y / \partial z = 2\dot{\varepsilon}_{yz} = 0.06$):
$$\frac{\partial V_y}{\partial y} = +0.02, \quad \frac{\partial V_y}{\partial z} = 2\dot{\varepsilon}_{yz} = 0.06$$

$$\implies V_y = +0.02y + 0.06z$$

### Summary of Velocity Field

$$\boxed{V_x = 0.02x}$$
$$\boxed{V_y = 0.02y + 0.06z}$$
$$\boxed{V_z = -0.04z}$$

**Physical interpretation:**
- V_z: workpiece compresses; velocity proportional to Z-position (zero at fixed base, max at top)
- V_x: lateral spread in X — purely from volume conservation
- V_y: lateral spread in Y **plus** shear-driven flow from platen friction (0.06z term)

---

## (h) Velocity at Specified Coordinates — [3 Marks]

Substituting into the velocity field equations:

### Point 1: (x, y, z) = (0, 0, 0)

$$V_x = 0.02(0) = 0$$
$$V_y = 0.02(0) + 0.06(0) = 0$$
$$V_z = -0.04(0) = 0$$

> At the fixed base, all velocities = 0 ✓ (consistent with fixed BC)

### Point 2: (x, y, z) = (0, 0, 5)

$$V_x = 0.02(0) = 0$$
$$V_y = 0.02(0) + 0.06(5) = 0.3$$
$$V_z = -0.04(5) = -0.2$$

> At height z = 5: vertical compression begins; shear-driven lateral flow in Y = 0.3 units/s

### Point 3: (x, y, z) = (10, 10, 20)

$$V_x = 0.02(10) = 0.2$$
$$V_y = 0.02(10) + 0.06(20) = 0.2 + 1.2 = 1.4$$
$$V_z = -0.04(20) = -0.8$$

### Summary Table

| Point | V_x | V_y | V_z |
|-------|-----|-----|-----|
| (0, 0, 0) | 0 | 0 | 0 |
| (0, 0, 5) | 0 | **0.3** | –0.2 |
| (10, 10, 20) | 0.2 | **1.4** | –0.8 |

---

## (i) Power Due to External Stresses — [4 Marks]

External power = work done by surface tractions on the boundary.

### Power Due to Compressive Stress

$$P_{compression} = |\sigma_z| \times A_{top} \times V_0$$

Area of loaded face: $A_{top} = L \times W = 20 \times 20 = 400$ units²

$$P_{comp} = 10 \times 400 \times 2 = \mathbf{8000 \text{ units}}$$

### Power Due to Shear Stress — Integration on Top Face

The shear power must be computed by integration because the velocity V_y is **not constant** — it varies with position on the face.

**At top face (z = H = 50):** $V_y = 0.02y + 0.06(50) = 0.02y + 3$

$$P_{shear} = \int_{-10}^{+10}\int_{-10}^{+10} \tau_{zy} \cdot V_y \, dx \, dy = \int_{-10}^{+10}\int_{-10}^{+10} 5(0.02y + 3) \, dx \, dy$$

**Inner integral (over y, –10 to +10):**

$$\int_{-10}^{+10} 5(0.02y + 3) \, dy = 5\left[0.01y^2 + 3y\right]_{-10}^{+10}$$

At y = +10: $0.01(100) + 3(10) = 1 + 30 = 31$

At y = –10: $0.01(100) + 3(–10) = 1 – 30 = –29$

$$= 5 \times (31 – (–29)) = 5 \times 60 = 300$$

**Outer integral (over x, –10 to +10):**

$$P_{shear} = \int_{-10}^{+10} 300 \, dx = 300 \times 20 = \mathbf{6000 \text{ units}}$$

### Cross-Check: Lateral Face (ZY plane at y = +10)

At y = +10: $V_y = 0.02(10) + 0.06z = 0.2 + 0.06z$

$$P_{zy,lat} = \int_{0}^{50}\int_{-10}^{+10} \tau_{yz} \cdot V_y \, dx \, dz = \int_0^{50} 5(0.2 + 0.06z) \times 20 \, dz$$

$$= 100 \int_0^{50}(0.2 + 0.06z) \, dz = 100\left[0.2z + 0.03z^2\right]_0^{50}$$

$$= 100[10 + 75] = \mathbf{8500 \text{ units}}$$

> **Why are these different?**
> - **Top face (P = 6000):** This is the direct **friction input power** from the platen. Use this for **external power balance**.
> - **Lateral face (P = 8500):** This captures the cumulative shear work across the full height — it includes both the friction-driven component AND the velocity gradient built up over z. This is an **internal traction** work term.
> - For **external power**, always integrate over the **loaded face** (where the external agent applies traction).
> - For **internal power**, use the volume integral σᵢⱼ·ε̇ᵢⱼ (which implicitly accounts for all faces).

### Total External Power

$$\boxed{P_{external} = P_{comp} + P_{shear} = 8000 + 6000 = 14000 \text{ units}}$$

---

## (j) Power Due to Internal Stresses — [4 Marks]

Internal power per unit volume = double contraction of stress and strain rate tensors:

$$\dot{w} = \sigma_{ij} \dot{\varepsilon}_{ij} = \sigma_{zz}\dot{\varepsilon}_{zz} + 2\tau_{yz}\dot{\varepsilon}_{yz}$$

> Factor of 2 because τ_yz = τ_zy (symmetric) and ε̇_yz = ε̇_zy:

$$\dot{w} = (-10)(-0.04) + 2(5)(0.03) = 0.40 + 0.30 = 0.70 \text{ units/vol}$$

**Total volume:**
$$V_{ol} = 20 \times 20 \times 50 = 20{,}000 \text{ units}^3$$

$$\boxed{P_{internal} = 0.70 \times 20{,}000 = 14{,}000 \text{ units}}$$

**Consistency check:** P_external = P_internal = 14,000 ✓

> This confirms that the assumed linear velocity field is **kinematically admissible** and energetically consistent.

---

## (k) Power via Principal Stress × Principal Strain Rate — [2 Marks]

Using principal values: σ₁ = +2.07, σ₂ = 0, σ₃ = –12.07 and ε̇₁ = +0.0324, ε̇₂ = +0.02, ε̇₃ = –0.0524

$$P_{principal} = V_{ol} \times (\sigma_1\dot{\varepsilon}_1 + \sigma_2\dot{\varepsilon}_2 + \sigma_3\dot{\varepsilon}_3)$$

$$= 20{,}000 \times \left[(2.07)(0.0324) + (0)(0.02) + (-12.07)(-0.0524)\right]$$

$$= 20{,}000 \times [0.0671 + 0 + 0.6325]$$

$$= 20{,}000 \times 0.6996 \approx \mathbf{13{,}992 \text{ units}}$$

> ≈ 14,000 ✓ (small discrepancy from rounding of principal values)

---

## (l) Equivalent Stress and Effective Strain — [2 Marks]

### Equivalent (Von Mises) Stress

Already computed in (e):
$$\boxed{\bar{\sigma} = k_f^{VM} = 13.23 \text{ units}}$$

### Effective Strain Rate

$$\dot{\bar{\varepsilon}} = \sqrt{\frac{2}{3}\left(\dot{\varepsilon}_1^{p2} + \dot{\varepsilon}_2^{p2} + \dot{\varepsilon}_3^{p2}\right)}$$

$$= \sqrt{\frac{2}{3}\left[(0.0324)^2 + (0.02)^2 + (-0.0524)^2\right]}$$

$$= \sqrt{\frac{2}{3}\left[0.001050 + 0.000400 + 0.002746\right]}$$

$$= \sqrt{\frac{2}{3} \times 0.004196} = \sqrt{0.002797} = 0.0529 \text{ s}^{-1}$$

$$\boxed{\dot{\bar{\varepsilon}} \approx 0.053 \text{ s}^{-1}}$$

**Consistency check:**
$$\bar{\sigma} \cdot \dot{\bar{\varepsilon}} = 13.23 \times 0.053 = 0.701 \approx 0.70 \text{ (internal power density)} \checkmark$$

---

## (m) Power per Unit Volume — Upper Bound Method — [2 Marks]

In the **upper bound theorem**, power per unit volume is:

$$\dot{W}_{UB} = \bar{\sigma} \cdot \dot{\bar{\varepsilon}}$$

$$\dot{W}_{UB} = 13.23 \times 0.053 = \mathbf{0.701 \text{ units/vol}}$$

**Total upper bound power:**

$$\boxed{P_{UB} = \dot{W}_{UB} \times V_{ol} = 0.701 \times 20{,}000 \approx 14{,}020 \text{ units}}$$

> **Why is this an upper bound?**
> The assumed velocity field (linear, homogeneous) is **kinematically admissible** — it satisfies:
> 1. Velocity boundary conditions (V_z = 0 at z = 0 for fixed BC)
> 2. Incompressibility (∇·V = 0)
> 3. No velocity discontinuities
>
> The upper bound theorem states: *any kinematically admissible velocity field gives a power ≥ actual required power.* Here the UB equals internal power exactly because the assumed field is the true solution for this homogeneous deformation case.

---

## SUMMARY TABLE

| Part | Result |
|------|--------|
| (a) Stress tensor | σ_zz = –10, τ_yz = τ_zy = 5, rest = 0 |
| (b) Invariants | I₁ = –10, I₂ = –25, I₃ = 0 |
| (c) Principal σ | +2.07, 0, –12.07 ; σ_m = –3.33 |
| (d) Mohr's Circle | C = –5, R = 7.07, τ_max = 7.07, θ = 22.5° |
| (e) Flow condition | k_f^VM = 13.23, k_f^Tr = 14.14 |
| (f) Strain rates | ε̇_zz = –0.04, ε̇_xx = ε̇_yy = +0.02, ε̇_yz = 0.03 |
| (g) Velocity field | Vx = 0.02x, Vy = 0.02y + 0.06z, Vz = –0.04z |
| (h) Velocities | (0,0,0)→zero; (0,0,5)→(0, 0.3, –0.2); (10,10,20)→(0.2, 1.4, –0.8) |
| (i) External power | P_comp = 8000, P_shear = 6000, **P_ext = 14,000** |
| (j) Internal power | **P_int = 14,000** ✓ |
| (k) P_principal | ≈ 13,992 ✓ |
| (l) Equiv. quantities | σ̄ = 13.23, ε̄̇ = 0.053 |
| (m) Upper bound | Ẇ_UB = 0.701/vol, P_UB ≈ 14,020 |

---

*Solution complete — all energy terms consistent, incompressibility satisfied throughout.*
