# student-invoice-price-calculator

## Overview

This project is a simple educational Treasury futures invoice price calculator built in Excel.

The goal of the project is to demonstrate the core mechanics behind Treasury futures delivery and how futures prices connect to cash Treasury pricing through conversion factors and accrued interest.

Rather than focusing on overengineered systems or unnecessary complexity, this project isolates the fundamental delivery math used in Treasury futures markets.

The calculator models:

* Coupon payments
* Accrued interest
* Futures implied cash pricing
* Invoice pricing
* Net basis

This project is intended for educational purposes and serves as a student-level introduction to Treasury futures delivery mechanics and fixed income settlement logic.

---

# Inputs

| Input                  | Description                                |
| ---------------------- | ------------------------------------------ |
| Par Value              | Face value of the Treasury security        |
| Coupon Rate            | Annual coupon rate of the bond             |
| Coupon Frequency       | Number of coupon payments per year         |
| Clean Market Price     | Current clean cash Treasury market price   |
| Days Since Last Coupon | Days accrued since previous coupon payment |
| Days In Coupon Period  | Total days in current coupon period        |
| Futures Price          | Treasury futures market price              |
| Conversion Factor      | CME conversion factor of the CTD bond      |

---

# Formulas

## 1. Coupon Payment

Calculates the periodic coupon payment of the Treasury security.

```text
Coupon Payment = (Coupon Rate × Par Value) / Coupon Frequency
```

Example:

```text
(0.045 × 100) / 2 = 2.25
```

---

## 2. Accrued Interest

Calculates the coupon interest earned since the previous coupon payment date.

```text
Accrued Interest =
Coupon Payment ×
(Days Since Last Coupon / Days In Coupon Period)
```

Example:

```text
2.25 × (73 / 182) = 0.9025
```

---

## 3. Futures Implied Cash Price

Calculates the futures-adjusted implied cash Treasury price using the conversion factor.

```text
Implied Cash Price =
Futures Price × Conversion Factor
```

Example:

```text
111.50 × 0.9025 = 100.62875
```

---

## 4. Invoice Price

Calculates the final Treasury futures delivery invoice price.

```text
Invoice Price =
Implied Cash Price + Accrued Interest
```

Example:

```text
100.62875 + 0.9025 = 101.53125
```

---

## 5. Net Basis

Calculates the difference between the current clean cash Treasury market price and the futures implied cash price.

```text
Net Basis =
Clean Market Price − Implied Cash Price
```

Example:

```text
109.25 − 100.62875 = 8.62125
```

---

# Educational Concepts

This project demonstrates several important fixed income and Treasury futures concepts:

* Treasury coupon mechanics
* Accrued interest calculations
* Clean vs dirty pricing
* Treasury futures conversion factors
* Futures implied cash pricing
* Invoice settlement mechanics
* Treasury futures basis relationships

---

# Purpose

The purpose of this project is to make Treasury futures delivery mechanics easier to understand through a transparent and modular calculator structure.

The project intentionally prioritizes:

* Simple structure
* Readable formulas
* Educational transparency
* Practical intuition

instead of unnecessary complexity.

---

# Notes

This project is an educational proof-of-concept and does not include:

* Delivery options
* Implied repo calculations
* Cheapest-to-deliver optimization
* Carry modeling
* Advanced Treasury futures delivery optionality
* Institutional settlement conventions

The focus is purely on the foundational invoice pricing engine behind Treasury futures delivery.
