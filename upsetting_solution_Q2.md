# Upsetting Process — Solution (Problem 2)
**Topic:** Metal Forming · Plasticity · Stress-Strain Rate Analysis

---

## QUESTION (Full Statement)

A workpiece of dimensions **8 × 4 × 2 units** (Length × Width × Height, i.e., 2L = 8, 2b = 4, h = 2) is compressed using an upsetting process. The tool applies a uniaxial compressive stress:

$$\sigma_{zz} = -5 \text{ units}$$

Friction between the platen and workpiece produces a shear stress:

$$\tau_{yz} = \tau_{zy} = 2 \text{ units}$$

The tool (ram) velocity:

$$V_z = -1 \text{ unit/s (compressive)}$$

**Coordinate system:** Z = compression direction; X, Y = lateral directions.  
**Limits:** z from –h to +h (i.e., –1 to +1); y from –b to +b (i.e., –2 to +2); x from –L/2 to +L/2.

> Note: Both ends compress (symmetric about mid-plane) → Z limits: **–1 to +1**, giving 2h = 2.

**Find:**
1. Applied stress tensor and invariants (I, J)
2. Principal stresses and principal directions
3. Mohr's circle
4. Flow condition — k_f via Von Mises and Tresca
5. Strain rate tensor and velocity field (V_x, V_y, V_z)
6. Velocity at key coordinates
7. Power due to external normal stress
8. Power due to shear stress (by integration)
9. Power per unit volume (total)
10. Power due to internal stresses
11. Effective strain rate
12. Principal strain rates
13. Upper bound power check

---

## PROBLEM SETUP

| Quantity | Value |
|----------|-------|
| Dimensions | 2L = 8, 2b = 4, h = 2 → L=4, b=2, h=1 (half-height) |
| σ_zz | –5 units |
| τ_yz = τ_zy | 2 units |
| Tool velocity | V_z = –1 at z = +h = +1 |
| Z limits | –h to +h → **–1 to +1** (free both ends) |
| Y limits | –b to +b → **–2 to +2** |
| X limits | –L to +L → **–4 to +4** |
| Volume | 8 × 4 × 2 = **64 units³** |

---

## STRESS TENSOR

$$[\sigma_{ij}] = \begin{bmatrix} 0 & 0 & 0 \\ 0 & 0 & 2 \\ 0 & 2 & -5 \end{bmatrix}$$

---

## (1) STRESS INVARIANTS

### Invariants of σ_ij — denoted I₁, I₂, I₃

**I₁ = tr(σ):**
$$I_1 = 0 + 0 + (-5) = \boxed{-5}$$

**I₂ = ½[I₁² – tr(σ²)]:**
$$I_2 = \sigma_{xx}\sigma_{yy} + \sigma_{yy}\sigma_{zz} + \sigma_{zz}\sigma_{xx} - \tau_{xy}^2 - \tau_{yz}^2 - \tau_{zx}^2$$
$$= 0 + 0(−5) + 0 - 0 - 4 - 0 = \boxed{-4}$$

**I₃ = det(σ):**
$$I_3 = 0(0 \cdot (-5) - 2 \cdot 2) - 0 + 0 = \boxed{0}$$

### Hydrostatic (Mean) Stress

$$\sigma_m = \frac{I_1}{3} = \frac{-5}{3} = -1.67 \text{ units}$$

### Deviatoric Tensor S_ij = σ_ij – σ_m·δ_ij

$$[S_{ij}] = \begin{bmatrix} 0-(-5/3) & 0 & 0 \\ 0 & 0-(-5/3) & 2 \\ 0 & 2 & -5-(-5/3) \end{bmatrix} = \begin{bmatrix} 5/3 & 0 & 0 \\ 0 & 5/3 & 2 \\ 0 & 2 & -10/3 \end{bmatrix}$$

### Invariants of S_ij — denoted J₁, J₂, J₃

**J₁ = tr(S) = 0** always (by definition of deviatoric tensor) ✓

**J₂ (second deviatoric invariant):**
$$J_2 = -\frac{1}{2}S_{ij}S_{ij} = -\left[\frac{1}{2}\left(S_{xx}^2 + S_{yy}^2 + S_{zz}^2\right) + S_{yz}^2\right]$$
$$= -\left[\frac{1}{2}\left(\frac{25}{9} + \frac{25}{9} + \frac{100}{9}\right) + 4\right] = -\left[\frac{150}{18} + 4\right] = -[8.33 + 4]$$
$$\boxed{J_2 = -3.31} \approx -\frac{10}{3}$$

**J₃ = det(S):**
$$J_3 = \frac{5}{3}\left[\frac{5}{3}\cdot\frac{-10}{3} - 4\right] = \frac{5}{3}\left[\frac{-50}{9} - 4\right] = \frac{5}{3} \times \frac{-86}{9} = \frac{-430}{27} \approx \boxed{-15.9}$$

---

## (2) PRINCIPAL STRESSES

**Characteristic equation:**
$$\lambda^3 - I_1\lambda^2 + I_2\lambda - I_3 = 0$$
$$\lambda^3 + 5\lambda^2 - 4\lambda = 0$$
$$\lambda(\lambda^2 + 5\lambda - 4) = 0$$

**Root 1:** λ = 0 → **σ₃ = 0**

**Roots 2 & 3:**
$$\lambda = \frac{-5 \pm \sqrt{25 + 16}}{2} = \frac{-5 \pm \sqrt{41}}{2} = \frac{-5 \pm 6.40}{2}$$

$$\sigma_1 = \frac{-5 + 6.40}{2} = \frac{1.40}{2} = \boxed{+0.7}$$

$$\sigma_2 = \frac{-5 - 6.40}{2} = \frac{-11.40}{2} = \boxed{-5.7}$$

**Ordered:** σ₁ = +0.7, σ₂ = 0, σ₃ = –5.7

### Principal Directions

**For λ = 0:**
$$(\sigma_{ij} - 0\cdot I)\mathbf{n} = 0 \implies \begin{bmatrix}0&0&0\\0&0&2\\0&2&-5\end{bmatrix}\begin{bmatrix}n_x\\n_y\\n_z\end{bmatrix} = 0$$

From row 2: 2n_z = 0 → n_z = 0; from row 3: 2n_y = 0 → n_y = 0; n_x free.

$$\mathbf{n}^{(0)} = [1, 0, 0]$$

**For λ = +0.7:**
$$\begin{bmatrix}-0.7&0&0\\0&-0.7&2\\0&2&-5.7\end{bmatrix}\begin{bmatrix}n_x\\n_y\\n_z\end{bmatrix} = 0$$

Row 1: n_x = 0. Rows 2&3: –0.7n_y + 2n_z = 0 → n_y = (2/0.7)n_z = 2.857n_z

Set n_z = 0.35 → n_y = 1.0. Normalize: magnitude = √(1² + 0.35²) = 1.06

$$\mathbf{n}^{(0.7)} = [0,\ 0.943,\ 0.331]$$

**For λ = –5.7:**
$$\begin{bmatrix}5.7&0&0\\0&5.7&2\\0&2&0.7\end{bmatrix}\begin{bmatrix}n_x\\n_y\\n_z\end{bmatrix} = 0$$

Row 1: n_x = 0. From rows 2&3: 5.7n_y + 2n_z = 0 → n_z = –2.85n_y

Set n_y = 1 → n_z = –2.85. Normalize: magnitude = √(1 + 8.12) = 3.02

$$\mathbf{n}^{(-5.7)} = [0,\ 0.331,\ -0.944]$$

### Principal Direction Matrix

$$[Q] = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 0.943 & 0.331 \\ 0 & 0.331 & -0.944 \end{bmatrix}$$

---

## (3) MOHR'S CIRCLE

For the Y–Z plane (σ_yy = 0, σ_zz = –5, τ_yz = 2):

| Quantity | Formula | Value |
|----------|---------|-------|
| Centre C | (σ_yy + σ_zz)/2 | (0 – 5)/2 = **–2.5** |
| Radius R | √[(σ_yy–σ_zz)²/4 + τ²] | √[(2.5)² + 4] = √10.25 = **3.2** |
| σ₁ (Mohr) | C + R | –2.5 + 3.2 = **+0.7** ✓ |
| σ₂ (Mohr) | C – R | –2.5 – 3.2 = **–5.7** ✓ |
| τ_max | R | **3.2** |
| 2θ | tan⁻¹(2τ/(σ_A–σ_B)) | tan⁻¹(4/5) = 38.7° → θ = **19.3°** |

```
         τ
         |
    3.2  +       * (0, +2)
         |      /
         +----+--------+------ σ
       -5.7  -2.5    +0.7
         |      \
   -3.2  +       * (-5, -2)

         C = -2.5,  R = 3.2
```

---

## (4) FLOW CONDITION — k_f

### Von Mises

$$k_f^{VM} = \sqrt{\frac{1}{2}\left[(\sigma_1-\sigma_2)^2 + (\sigma_2-\sigma_3)^2 + (\sigma_3-\sigma_1)^2\right]}$$

$$= \sqrt{\frac{1}{2}\left[(0.7-0)^2 + (0-(-5.7))^2 + (-5.7-0.7)^2\right]}$$

$$= \sqrt{\frac{1}{2}\left[0.49 + 32.49 + 40.96\right]} = \sqrt{\frac{73.94}{2}} = \sqrt{36.97}$$

$$\boxed{k_f^{VM} = 6.08 \text{ units}}$$

### Tresca

$$k_f^{Tr} = \sigma_1 - \sigma_3 = 0.7 - (-5.7) = \boxed{6.4 \text{ units}}$$

### Error Check

$$\text{Error} = \frac{6.4 - 6.08}{6.4} \times 100 = \frac{0.32}{6.4} \times 100 = \mathbf{5\%} < 15\% \checkmark$$

> Von Mises is always lower than Tresca; 5% error is acceptable and within the standard engineering tolerance of 15%.

---

## (5) STRAIN RATE TENSOR AND VELOCITY FIELD

### Normal Strain Rates

From kinematics (symmetric compression, 2h = 2, V_z = –1 at z = h = 1):

$$\dot{\varepsilon}_{zz} = \frac{V_z}{h} = \frac{-1}{1} = -1 \text{ s}^{-1}$$

Wait — more precisely: $\dot{\varepsilon}_{zz} = \partial V_z/\partial z$. With V_z = –z at h=1, V_z = –1, giving **∂V_z/∂z = –1**.

Volume constancy: $\dot{\varepsilon}_{xx} + \dot{\varepsilon}_{yy} + \dot{\varepsilon}_{zz} = 0$

By symmetry (equal lateral dimensions in this problem's context):
$$\dot{\varepsilon}_{xx} = \dot{\varepsilon}_{yy} = +0.5 \text{ s}^{-1}$$

### Shear Strain Rate (Lévy-Mises)

$$\dot{\varepsilon}_{ij} = \lambda S_{ij}$$

Using z-component: $\lambda = \dot{\varepsilon}_{zz}/S_{zz} = -1/(-10/3) = 3/10 = 0.3$

$$\dot{\varepsilon}_{yz} = \lambda \cdot S_{yz} = 0.3 \times 2 = \mathbf{0.6}$$

### Strain Rate Tensor

$$[\dot{\varepsilon}_{ij}] = \begin{bmatrix} 0.5 & 0 & 0 \\ 0 & 0.5 & 0.6 \\ 0 & 0.6 & -1 \end{bmatrix}$$

**Check:** 0.5 + 0.5 – 1.0 = 0 ✓

### Velocity Field Derivation

**V_z:** Symmetric compression about z = 0. At z = h = +1, V_z = –1.

$$V_z = \dot{\varepsilon}_{zz} \cdot z = -z \implies V_z = -z$$

At z = +1: V_z = –1 ✓ ; at z = –1: V_z = +1 (upward from bottom platen) ✓

**V_x:** No shear in XZ, pure lateral spread:

$$V_x = \dot{\varepsilon}_{xx} \cdot x = 0.5x$$

At centre (x = 0): V_x = 0 ✓

**V_y:** Normal + shear contribution. Since τ_yz ≠ 0, V_y depends on **both y and z**:

$$\dot{\varepsilon}_{yy} = \frac{\partial V_y}{\partial y} = 0.5 \implies V_y \text{ contains } 0.5y$$

$$\dot{\varepsilon}_{yz} = \frac{1}{2}\left(\frac{\partial V_y}{\partial z} + \frac{\partial V_z}{\partial y}\right) = 0.6$$

Since $\partial V_z/\partial y = 0$: $\partial V_y/\partial z = 1.2$

Integrating: $f'(z) = 1.2 \implies f(z) = 1.2z$

$$V_y = 0.5y + 1.2z + C$$

At y = z = 0 (centre), V_y = 0 → **C = 0**

### Summary of Velocity Field

$$\boxed{V_x = 0.5x}$$
$$\boxed{V_y = 0.5y + 1.2z}$$
$$\boxed{V_z = -z}$$

---

## (6) VELOCITY AT KEY COORDINATES

| Point (x, y, z) | V_x | V_y | V_z |
|-----------------|-----|-----|-----|
| (0, 0, 0) | 0 | 0 | 0 |
| (0, 2, 0) | 0 | 1.0 | 0 |
| (0, 2, 1) | 0 | 2.2 | –1 |
| (4, 0, 0) | 2.0 | 0 | 0 |
| (4, 2, 1) | 2.0 | 2.2 | –1 |

> At the centre (0,0,0): zero velocity — symmetric free-compression ✓  
> At top face z = +1: V_z = –1 = tool velocity ✓

---

## (7) POWER DUE TO EXTERNAL NORMAL STRESS

The normal compressive force acts on both top and bottom faces (free compression, both ends move):

$$P_{comp} = 2 \times |\sigma_{zz}| \times A_{face} \times |V_{tool}|$$

Area of loaded face: A = 2L × 2b = 8 × 4 = 32 units²

$$P_{comp} = 2 \times 5 \times 32 \times 1 = \mathbf{320 \text{ units}}$$

**Power per unit volume (normal only):**
$$\dot{w}_{comp} = \frac{320}{64} = \mathbf{5 \text{ units/vol}}$$

---

## (8) POWER DUE TO SHEAR STRESS — BY INTEGRATION

Shear stress τ_zy = 2 acts on the top face (z = +h = +1) and bottom face (z = –h = –1). Both contribute by symmetry.

**At top face (z = +1):** $V_y = 0.5y + 1.2(1) = 0.5y + 1.2$

$$P_{shear,top} = \int_{-4}^{+4}\int_{-2}^{+2} \tau_{zy} \cdot V_y \, dy \, dx$$

$$= \int_{-4}^{+4}\int_{-2}^{+2} 2(0.5y + 1.2) \, dy \, dx$$

**Inner integral (over y, –2 to +2):**

$$\int_{-2}^{+2} 2(0.5y + 1.2) \, dy = 2\left[0.25y^2 + 1.2y\right]_{-2}^{+2}$$

At y = +2: $0.25(4) + 1.2(2) = 1 + 2.4 = 3.4$

At y = –2: $0.25(4) + 1.2(-2) = 1 - 2.4 = -1.4$

$$= 2 \times (3.4 - (-1.4)) = 2 \times 4.8 = 9.6$$

**Outer integral (over x, –4 to +4):**

$$P_{shear,top} = \int_{-4}^{+4} 9.6 \, dx = 9.6 \times 8 = 76.8$$

**Bottom face (z = –1):** V_y = 0.5y + 1.2(–1) = 0.5y – 1.2. But shear on bottom face acts in opposite direction (τ_zy = –2 by traction continuity on –Z face):

$$P_{shear,bot} = \int_{-4}^{+4}\int_{-2}^{+2} (-2)(0.5y - 1.2) \, dy \, dx$$

Inner integral:
$$\int_{-2}^{+2}(-2)(0.5y - 1.2)\,dy = -2\left[0.25y^2 - 1.2y\right]_{-2}^{+2}$$

At y=+2: 1 – 2.4 = –1.4; At y=–2: 1 + 2.4 = 3.4

$$= -2(-1.4 - 3.4) = -2(-4.8) = 9.6$$

$$P_{shear,bot} = 9.6 \times 8 = 76.8$$

$$P_{shear,total} = 76.8 + 76.8 = \mathbf{153.6 \text{ units}}$$

**Power per unit volume (shear):**
$$\dot{w}_{shear} = \frac{153.6}{64} = \mathbf{2.4 \text{ units/vol}}$$

---

## (9) TOTAL EXTERNAL POWER PER UNIT VOLUME

$$\boxed{\dot{w}_{total} = \dot{w}_{comp} + \dot{w}_{shear} = 5 + 2.4 = 7.4 \text{ units/vol}}$$

**Total power = 7.4 × 64 = 473.6 units** *(or equivalently 320 + 153.6 = 473.6)*

---

## (10) POWER DUE TO INTERNAL STRESSES

Internal power per unit volume = $\sigma_{ij}\dot{\varepsilon}_{ij}$ (double contraction):

$$\dot{w}_{int} = \sigma_{zz}\dot{\varepsilon}_{zz} + 2\tau_{yz}\dot{\varepsilon}_{yz}$$

> (Factor of 2 because τ_yz = τ_zy and ε̇_yz = ε̇_zy — each counted once for symmetric pair)

$$= (-5)(-1) + 2(2)(0.6) = 5 + 2.4$$

$$\boxed{\dot{w}_{int} = 7.4 \text{ units/vol}}$$

$$P_{int} = 7.4 \times 64 = \mathbf{473.6 \text{ units}}$$

**Consistency check:** P_ext = P_int = 473.6 ✓

---

## (11) EFFECTIVE STRAIN RATE

$$\dot{\bar{\varepsilon}} = \sqrt{\frac{2}{3}\dot{\varepsilon}_{ij}\dot{\varepsilon}_{ij}}$$

$$= \sqrt{\frac{2}{3}\left[\dot{\varepsilon}_{xx}^2 + \dot{\varepsilon}_{yy}^2 + \dot{\varepsilon}_{zz}^2 + 2\dot{\varepsilon}_{yz}^2\right]}$$

$$= \sqrt{\frac{2}{3}\left[0.25 + 0.25 + 1 + 2(0.36)\right]}$$

$$= \sqrt{\frac{2}{3}\left[0.25 + 0.25 + 1 + 0.72\right]} = \sqrt{\frac{2}{3} \times 2.22} = \sqrt{1.48}$$

$$\boxed{\dot{\bar{\varepsilon}} = 1.22 \text{ s}^{-1}}$$

---

## (12) PRINCIPAL STRAIN RATES

The X-direction is already principal (no X-row/column off-diagonals):

$$\dot{\varepsilon}_x^p = 0.5$$

For the Y–Z sub-block:

$$\det\begin{bmatrix}0.5-\lambda & 0.6 \\ 0.6 & -1-\lambda\end{bmatrix} = 0$$

$$(0.5-\lambda)(-1-\lambda) - 0.36 = 0$$

$$-0.5 - 0.5\lambda + \lambda + \lambda^2 - 0.36 = 0$$

$$\lambda^2 + 0.5\lambda - 0.86 = 0$$

$$\lambda = \frac{-0.5 \pm \sqrt{0.25 + 3.44}}{2} = \frac{-0.5 \pm 1.92}{2}$$

$$\dot{\varepsilon}_1^p = \frac{-0.5 + 1.92}{2} = \boxed{+0.71}$$

$$\dot{\varepsilon}_3^p = \frac{-0.5 - 1.92}{2} = \boxed{-1.21}$$

### All Three Principal Strain Rates (ordered)

$$\dot{\varepsilon}_1^p = 0.71, \quad \dot{\varepsilon}_2^p = 0.50, \quad \dot{\varepsilon}_3^p = -1.21$$

**Check:** 0.71 + 0.50 – 1.21 = 0 ✓

---

## (13) UPPER BOUND POWER

### Via Principal Stress × Principal Strain Rate

$$P_{principal} = V_{ol} \times (\sigma_1\dot{\varepsilon}_1^p + \sigma_2\dot{\varepsilon}_2^p + \sigma_3\dot{\varepsilon}_3^p)$$

$$= 64 \times (0.7 \times 0.71 + 0 \times 0.50 + (-5.7)(-1.21))$$

$$= 64 \times (0.497 + 0 + 6.897) = 64 \times 7.394$$

$$\approx \mathbf{473.2 \text{ units}} \approx 473.6 \checkmark$$

### Via Von Mises Upper Bound

$$\dot{W}_{UB} = k_f^{VM} \times \dot{\bar{\varepsilon}} = 6.08 \times 1.22 = 7.42 \text{ units/vol}$$

$$P_{UB} = 7.42 \times 64 = \mathbf{474.9 \text{ units}} \approx 473.6 \checkmark$$

> **Note:** Cannot use the "frictionless" severity formula here because friction is present (τ_yz = 2 ≠ 0). The upper bound must include the shear work term.

---

## SUMMARY TABLE

| Quantity | Result |
|----------|--------|
| σ_m | –5/3 = –1.67 |
| I₁, I₂, I₃ | –5, –4, 0 |
| J₁, J₂, J₃ | 0, –3.31, –15.9 |
| σ₁, σ₂, σ₃ | +0.7, 0, –5.7 |
| Mohr's C, R | –2.5, 3.2 |
| τ_max | 3.2 |
| k_f (VM) | **6.08** |
| k_f (Tresca) | **6.4** (error = 5%) |
| ε̇_zz, ε̇_yy, ε̇_xx | –1, +0.5, +0.5 |
| ε̇_yz | 0.6 |
| V_x, V_y, V_z | 0.5x, 0.5y+1.2z, –z |
| P_comp | 320 (= 5/vol) |
| P_shear | 153.6 (= 2.4/vol) |
| **P_total/vol** | **7.4** |
| P_internal/vol | **7.4** ✓ |
| ε̄̇ (effective) | **1.22** |
| ε̇₁ᵖ, ε̇₂ᵖ, ε̇₃ᵖ | +0.71, +0.50, –1.21 |
| P_UB/vol | **7.42** ✓ |

---

*All power terms consistent. Incompressibility satisfied throughout.*
