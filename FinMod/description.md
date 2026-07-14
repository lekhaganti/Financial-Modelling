# Financial Modelling — Core Insights
> **Source:** FinMod.xlsx — Sheet 9.1–9.7 | Firm & Project Valuation: Five Equivalent Methods
> Distilled to the 20% that explains 80%

---

## THE ONE MASTER PRINCIPLE

**Five roads, one destination.** The model proves — using real numbers — that APV, FCFE, FCFF, DDM, and Residual Income all produce the *exact same firm value* ($2,234.92) and the *exact same value added* ($1,434.92). The method you choose is a matter of convenience, not correctness. Understanding why they converge is the entire subject.

---

## THE MODEL AT A GLANCE

| Key Input | Value |
|---|---|
| Initial Firm Capital (Date 0) | $800 |
| Tax Rate | 40% |
| Unlevered Cost of Equity (r_u) | 10% |
| Risk-free Rate / Cost of Debt | 3% |
| Infinite Horizon Growth Rate | 5% |
| Initial Debt (D) | $250 |
| Initial Book Equity | $550 |

**Cash flow structure:** 5-year explicit forecast (Dates 1–5) + infinite horizon from Date 6 onward, with revenues growing from $650 → $840, EBIT from $180 → $305.

---

## LAYER 1 — THE CASH FLOW WATERFALL (Most Important Architecture)

Understanding *which* cash flows go to *whom* is the foundation of all five methods:

```
Revenue
  – Expenses
  = Gross Earnings
  – Depreciation
  = EBIT
  – Interest Expense
  = EBT
  – Taxes (40%)
  = Earnings (Net Income)
  + Depreciation          ← non-cash add-back
  = Cash Flow from Operations
  – CapEx
  – ΔWorking Capital
  = FREE CASH FLOW TO EQUITY (FCFE)  ← what equity holders receive
  + After-tax Interest
  = FREE CASH FLOW TO FIRM (FCFF)    ← what ALL capital providers receive
```

> **Mental model:** FCFE is the cash left for shareholders *after* debt is serviced. FCFF is the cash before any financing decisions — as if the firm were 100% equity-financed. FCFF + debt cash flows = FCFE.

**Actual numbers (Year 1):**
| Line | Value |
|---|---|
| EBIT | 180 |
| NOPAT (EBIT × (1 – tax)) | 108 |
| + Depreciation | 60 |
| – CapEx & ΔWC | –70 |
| **FCFF** | **98** |
| + New Borrowing – Interest paid | +0.5 |
| **FCFE (= Dividends)** | **98.5** |

---

## LAYER 2 — THE FIVE VALUATION METHODS

All five use the same cash flows, different lenses. **The key to understanding each is knowing what it discounts and at what rate.**

### Method 1: APV (Adjusted Present Value)
> *"Value the unlevered firm, then add the tax shield separately."*

```
Firm Value (APV) = Value of Unlevered Firm + PV of Tax Shield
                 = $2,182.16            + $52.76
                 = $2,234.92
```

- Unlevered firm discounted at **r_u = 10%** (no debt effect)
- Tax shield discounted at **r_f = 3%** (risk-free, because debt is risk-free here)
- Tax Shield = Interest × Tax Rate = $7.5 × 40% = **$3.00/year**, growing

> **Why APV is the most transparent method:** it isolates *exactly* how much value debt adds via the tax shield. Here: **$52.76 of value from leverage** on $250 of debt. That's the benefit of the interest tax deduction made explicit.

---

### Method 2: FCFE (Free Cash Flow to Equity)
> *"Discount equity cash flows at the levered cost of equity."*

```
Value of Equity = PV of FCFE discounted at r_e (levered)
r_e (levered)  ≈ 10.88% (Year 1), declining slightly as D/E falls
Value of Equity = $1,984.92
Value of Firm   = Equity + Debt = $1,984.92 + $250 = $2,234.92 ✓
```

> **Key insight:** The levered cost of equity (~10.88%) is *higher* than the unlevered rate (10%) because equity holders now bear financial risk on top of business risk. As debt grows (D rises from 250 → 288.75), r_e adjusts dynamically. This is Modigliani-Miller in action.

---

### Method 3: FCFF / WACC
> *"Discount firm-level cash flows at the blended cost of capital."*

```
WACC = (E/V) × r_e  +  (D/V) × r_d × (1 – tax)
     ≈ 9.87% (Year 1)   [vs. r_u = 10% — WACC < r_u because of tax shield]

Value of Firm = PV of FCFF at WACC = $2,234.92 ✓
```

**Weights (Year 1):**
- Equity weight: 88.8%
- Debt weight: 11.2%

> **Critical insight — WACC is a moving target:** Because the debt/equity ratio changes each year as the firm grows and borrows more, WACC is recalculated period by period (~9.866% → 9.885%). A textbook with a fixed WACC is simplifying. This model shows the correct approach.

> **Why WACC < r_u:** The tax shield on debt lowers the effective cost of capital. WACC embeds the tax benefit *in the discount rate* rather than in the cash flows (unlike APV which separates them).

---

### Method 4: DDM (Dividend Discount Model)
> *"Dividends = FCFE when the firm pays out all free cash flow."*

```
Dividends = FCFE (since all free cash flow is distributed)
Value of Equity = PV of Dividends at r_e = $1,984.92
Value of Firm   = $2,234.92 ✓
```

> **When DDM = FCFE:** Only when the firm pays out 100% of free cash flow as dividends — which this model assumes. In practice, retained earnings break this equivalence. DDM is a special case of FCFE.

---

### Method 5: Residual Income (RI) / Economic Profit
> *"Start with book value, add the PV of all future economic profits."*

```
Economic Profit = NOPAT – Capital Charge
Capital Charge  = WACC × Book Value of Total Capital

Year 1: EP = 108 – 78.93 = 29.07
Year 5: EP = 147 – 83.01 = 63.99  ← growing because NOPAT grows faster than capital charge

Value Added     = PV of all Economic Profits = $1,434.92
Firm Value (RI) = Book Value + Value Added   = $800 + $1,434.92 = $2,234.92 ✓
```

> **Why RI is the most intuitive for performance analysts:** Economic Profit tells you *period by period* whether the firm is earning above or below its cost of capital. NOPAT > Capital Charge = value creation. A firm can be profitable (positive earnings) yet destroy value (EP < 0) if it doesn't earn its WACC.

---

## THE CONVERGENCE — WHY ALL FIVE GIVE $2,234.92

| Method | Discounts | At Rate | Firm Value |
|---|---|---|---|
| APV | FCFF (unlevered) + Tax Shield | r_u / r_f | $2,234.92 |
| FCFE | FCFE (equity CFs) | r_e (levered) | $2,234.92 |
| FCFF/WACC | FCFF | WACC | $2,234.92 |
| DDM | Dividends | r_e (levered) | $2,234.92 |
| RI | Book Value + Economic Profits | WACC / r_e | $2,234.92 |

**The algebra behind convergence:** All methods account for the same three things — (1) the firm's operating cash flows, (2) the tax shield on debt, and (3) the risk borne by each capital provider. They just package these three elements differently. If they don't converge, there's a modelling error.

---

## THE 4 UNIVERSAL PRINCIPLES FROM THIS MODEL

**1. NOPAT is the cleanest measure of operating performance.**
`NOPAT = EBIT × (1 – tax rate)` — strips out financing decisions entirely. Two firms with identical operations but different capital structures have the same NOPAT. It's the common currency across all valuation methods.

**2. The tax shield has real economic value.**
$52.76 of the firm's $2,234.92 value comes purely from the government's subsidy on debt interest. Leverage isn't just about ROE — it creates value through tax savings. The model quantifies this precisely.

**3. Value created = Firm Value − Capital Invested.**
`Value Added = $2,234.92 – $800 = $1,434.92`
This is the single most important number in corporate finance. A firm worth less than its invested capital is destroying wealth, regardless of profitability.

**4. Economic Profit ≠ Accounting Profit.**
Year 1: Earnings = $103.5 (positive). Economic Profit = $29.07 (also positive, but much smaller).
A firm can show healthy accounting earnings and still be a weak economic performer if its capital charge is high. The capital charge is the *opportunity cost* of the capital deployed — the return investors could get elsewhere at equivalent risk.

---

## KEY FORMULAS

```
FCFF    = NOPAT + Depreciation – CapEx – ΔWorking Capital
FCFE    = FCFF – After-tax Interest + Net New Borrowing
NOPAT   = EBIT × (1 – Tax Rate)
WACC    = (E/V)×r_e + (D/V)×r_d×(1–T)
APV     = V_unlevered + PV(Tax Shield)
EP      = NOPAT – (WACC × Invested Capital)
RI Firm Value = Book Value + PV(Economic Profits)
Terminal Value (Gordon Growth) = CF_{t+1} / (r – g)
```

---

## WHAT THIS MODEL IS REALLY TEACHING

The five methods exist because different situations make different methods practical:

| Situation | Best Method |
|---|---|
| Changing capital structure | APV (cleanest separation) |
| Stable leverage ratio | WACC/FCFF (simplest) |
| Dividend-paying mature firm | DDM |
| Private equity / leveraged buyout | FCFE |
| Performance measurement / incentive design | Residual Income / Economic Profit |

The model proves they're all correct. Practice choosing the right tool for the context.

---

*Source: FinMod.xlsx — Sheet 9.1–9.7 | Firm & Project Valuation: Five Equivalent Methods*
