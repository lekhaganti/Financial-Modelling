# FMCF — Core Mental Models & Principles
> *Maya's Quest: Financing Atherium Legends*

---

## THE ONE MASTER PRINCIPLE

**Money has a time address.** A dollar today ≠ a dollar tomorrow. Every calculation in this entire project is a consequence of that single fact. All 14 scenarios are just different forms of the same question: *what is this cash flow worth at a different point in time?*

---

## PART I — TIME VALUE OF MONEY & PROJECT VALUATION (Scenarios 1–6)

### The Two Fundamental Operations

| Direction | Formula | What It Does |
|---|---|---|
| **Discounting** (future → present) | `PV = FV / (1+r)^n` | Shrinks a future number back to today |
| **Compounding** (present → future) | `FV = PV × (1+r)^n` | Grows a today number forward |

> **Mental model:** Discounting is asking *"what would I pay today?"* Compounding is asking *"what will I have later?"* — they are mathematical inverses.

---

### Lump Sum vs. Annuity — The Critical Distinction

A **lump sum** is one cash flow. An **annuity** is the same cash flow repeated.

| Type | PV Formula | FV Formula |
|---|---|---|
| Lump Sum | `PV = FV / (1+r)^n` | `FV = PV × (1+r)^n` |
| Annuity (PV) | `PMT × [1 – (1+r)^-n] / r` | — |
| Annuity (FV) | — | `PMT × [((1+r)^n – 1) / r] × (1+r)` |

**Key numbers from the case:**
- Scenario 1: $2,500 in 5 quarters @ 6.5% → PV = **$1,824.70**
- Scenario 2: $1,200 growing @ 4.2% for 6 periods → FV = **$1,535.98**
- Scenario 3: $185.50/period × 8 periods @ 5.1% → PV = **$1,194.09**
- Scenario 4: $75/period × 5 periods @ 8.5% → FV at period 6 = **$482.18**

---

### NPV — The Decision Rule That Matters Most

> **NPV = Sum of all discounted cash inflows − Initial Investment**
> `NPV = Σ [CFt / (1+r)^t] – C₀`

- **NPV > 0** → Accept the project (creates value)
- **NPV < 0** → Reject (destroys value)
- **NPV = 0** → Indifferent

**Scenario 5 (DLC project):** $220k investment, 5 years of inflows → NPV = **$1,14,006.53** ✅

**Scenario 6 (Inflation adjustment):** Real rate 9%, Inflation 3.1%
- Nominal rate used for discounting = `(1 + real) × (1 + inflation) – 1`
- NPV = **$99,270.86** — still positive, project survives inflation

> **Principle:** Always discount at the *nominal* rate when cash flows are in *nominal* (inflated) terms. Using real rate on nominal flows understates NPV; mixing them is the #1 student error.

---

## PART II — MORTGAGES & LOAN AMORTIZATION (Scenarios 7–9)

### The Mortgage Formula — One Formula, Three Decisions

```
PMT = PV × [r(1+r)^n / ((1+r)^n – 1)]
```

This is just annuity PV rearranged to solve for payment instead of price.

**Key insight — Amortization structure:**
- Early periods: payment is mostly **interest**
- Late periods: payment is mostly **principal**
- This is not arbitrary — it's a mathematical consequence of the declining balance

**Scenario 7:** $250k, 25 years, 8.5% → annual PMT calculated via formula above

**Scenario 9 — Rate drop impact (the most practical insight):**
| | @ 9.5% | @ 8.2% |
|---|---|---|
| Total payment (30 yr) | $50,840/yr | $45,254/yr |
| Total interest paid | $15,25,209 | $13,57,634 |
| **Savings from 1.3% rate drop** | — | **~$1,67,575** |

> **Mental model:** A 1.3% rate reduction on a $500k mortgage saves ~$167k over 30 years. Interest rate differences compound dramatically over time. The earlier you refinance, the more you save (because early payments are interest-heavy).

---

## PART III — BOND PRICING (Scenarios 10–14)

### The Core Bond Equation

A bond's price = PV of all coupons + PV of face value

```
Price = Σ [Coupon / (1+r)^t] + [Face Value / (1+r)^n]
```

### The Inverse Relationship — The Most Important Bond Principle

| If market yield... | Bond price... | Why |
|---|---|---|
| **Rises** | **Falls** | Future coupons now discounted at higher rate |
| **Falls** | **Rises** | Same coupons, lower discount = higher PV |

**From Scenario 12 sensitivity table:**
- YTM 0.5% → price $1,081 | YTM 10% → price $573
- Same bond, same coupons — price moves 47% purely from yield change

### Premium vs. Discount Bond

| Condition | Bond Type | Price |
|---|---|---|
| Coupon Rate > YTM | Premium | > $1,000 |
| Coupon Rate = YTM | Par | = $1,000 |
| Coupon Rate < YTM | Discount | < $1,000 |

**Scenario 11:** Coupon 5.8%, YTM 4.0% → Price = **$1,080.84** (APR) / **$1,082.69** (EAR) — premium bond ✅

### APR vs. EAR — Why It Matters for Bonds

- **APR** (Annual Percentage Rate): divide annual yield by periods → 4% ÷ 2 = 2% per half-year
- **EAR** (Effective Annual Rate): convert properly → (1.04)^0.5 – 1 = 1.98% per half-year
- EAR gives a **slightly higher price** because the per-period discount rate is marginally lower
- Difference is small but conceptually important: EAR reflects true compounding

---

### Duration & Convexity — Risk Measurement (Scenario 14)

| Metric | Value | What It Tells You |
|---|---|---|
| **Duration** | 4.54 years | Average time to receive cash flows (weighted by PV) |
| **Modified Duration** | 4.46–4.47 | % price drop per 1% rise in yield |
| **Convexity** | 25.51–25.52 | Curvature correction for large yield moves |

> **Mental model — Modified Duration as a speedometer:**
> If Modified Duration = 4.46 and yields rise 1%, bond falls ~4.46%.
> Duration is the *linear* estimate; convexity corrects for the curve.
> **Longer duration = more interest rate risk. Lower coupon + longer maturity = highest duration.**

**Price change approximation:**
```
ΔP/P ≈ –(Modified Duration × Δy) + ½ × Convexity × (Δy)²
```

---

## THE 5 UNIVERSAL PRINCIPLES ACROSS ALL 14 SCENARIOS

1. **Time has a price** — that price is the discount/interest rate. Higher risk → higher rate → lower present value.

2. **Cash flow timing matters as much as amount** — $1,000 in year 1 is worth more than $1,000 in year 10. Never compare raw cash flows across time.

3. **NPV = value creation** — the only decision rule that directly measures whether a project adds wealth. IRR and payback period are shortcuts; NPV is the truth.

4. **Rate changes have outsized long-run impact** — small rate differences compound into large dollar differences over 20–30 year horizons (mortgage and bond both demonstrate this).

5. **Coupon rate vs. yield determines bond character** — premium/discount/par status is fully determined by this comparison. It never changes as long as the coupon is fixed.

---

## FORMULA CHEAT SHEET

```
PV lump sum       : PV = FV / (1+r)^n
FV lump sum       : FV = PV × (1+r)^n
PV annuity        : PV = PMT × [1 – (1+r)^-n] / r
FV annuity (due)  : FV = PMT × [((1+r)^n – 1) / r] × (1+r)
Mortgage PMT      : PMT = PV × [r(1+r)^n / ((1+r)^n – 1)]
NPV               : NPV = Σ CFt/(1+r)^t – C₀
Nominal rate      : (1 + real) × (1 + inflation) – 1
Bond price        : Σ [C/(1+r)^t] + [FV/(1+r)^n]
Modified Duration : Macaulay Duration / (1 + r/m)
```

---

*Source: FMCF Presentation | Maya's Quest: Financing Atherium Legends*
