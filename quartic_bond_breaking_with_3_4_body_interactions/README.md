
# Fix for LAMMPS Error: "Bond style quartic cannot be used with 3,4-body interactions"

If you encountered one of the following LAMMPS errors:

```
Bond style quartic cannot be used with 3,4-body interactions
```
```
No angle, dihedral, or improper styles can be defined when using bond style quartic.
```

you are in the right place. By default, LAMMPS's `bond_style quartic` forbids the simultaneous use of angle, dihedral, or improper interactions. The modified source files in this directory remove that restriction, allowing you to use quartic bonds together with angle (and other 3/4-body) styles in your simulation.

See the modification summary below for details on what was changed and why.

---

# Summary of Modifications to `bond_quartic`

## 1. Removed Internal Bond Breaking
- Deleted the code that automatically removed bonds when `r > rc`.
- Bonds no longer self-delete.
- **Purpose:** Delegate all topology changes to `fix bond/break`.

---

## 2. Allowed Angle Interactions
- Removed restriction preventing use with angle styles.
- Angles can now coexist with quartic bonds.
- **Purpose:** Enable polymer models with angular stiffness.

---

## 3. Kept Quartic Nonlinear Force Law

Quartic bond energy:

E(r) = K (r - r0)^2 (r - rc)^2

- Nonlinear elastic behavior preserved.
- Energy goes to zero at `r = rc`.
- **Purpose:** Maintain nonlinear elasticity prior to fracture.

---

## 4. Replaced Internal Constant
- Replaced predefined `MY_CUBEROOT2` with explicit computation `pow(2.0, 1.0/3.0)`.
- **Purpose:** Simplify dependency (cosmetic change).

---

## 5. Removed `partial_flag = 1`
- Bond style no longer marked as partially contributing energy.
- **Purpose:** Simplification (may affect energy bookkeeping).

---

# Overall Design Intent

- Quartic bond → provides nonlinear elastic force only  
- `fix bond/break` → handles bond deletion and topology updates  
- Angles remain valid until explicit bond removal  

**Clean separation of:**
- Force calculation  
- Topology modification
