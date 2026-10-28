# Archer-Daniels-Midland (ADM) DCF Valuation

Excel valuation of ADM (NYSE: ADM) built from SEC filings. Contents:
- linked three-statement projection
- DCF using perpetuity-growth and exit-multiple terminal values
- trading comps and football field
- two-page research note

Rohitpreet Singh, 28-Oct-2026. Educational project, not investment advice.

## Why ADM
In Punjab I sold maize to starch, beer and ethanol plants and ran a grain-procurement agency. ADM runs the same chain at global scale through three segments:
- Ag Services & Oilseeds: origination and crushing
- Carbohydrate Solutions: starches, sweeteners, ethanol
- Nutrition

## Results
| Output | Value | Cell |
|---|---|---|
| Price, 27-Oct-2026 close | $78.20 | `Inputs & Sources!B6` |
| DCF, perpetuity growth (2.5%) | $68.81 | `DCF!B51` |
| DCF, exit multiple (10.72x EV/EBITDA) | $74.50 | `DCF!C51` |
| **Blended (50/50)** | **$71.65 (-8.4%)** | `DCF!B59`, `DCF!B60` |
| WACC | 7.61% | `WACC!B25` |
| Blended value, raw beta 0.63 | $75.45 | `Sensitivity!G30` |
| Comps, EV/EBITDA, peer 25th-75th pct | $50.26-$65.43 | `Comps!E22:G22` |
| Analyst average target (11 analysts) | $80.30 | `Inputs & Sources!B12` |

The blended value is within a +/-15% band of the price, so I rate ADM fairly valued. The market already prices in the 2026 earnings recovery.

## Files
| File | Contents |
|---|---|
| `ADM_DCF_Valuation.xlsx` | Cover, Inputs & Sources, Historical, Projections, WACC, DCF, Sensitivity, Comps, Football Field |
| `ADM_Equity_Research_Note.pdf` | Two-page note |
| `football_field.png` | Valuation range chart |
| `data/*.csv` | Extracted financials and market inputs, with source URLs |

## Sources
**ADM filings on SEC EDGAR:**
- 10-K FY2025
- 10-Q Q2 2026: balance sheet, 485mm diluted shares, $1,331mm lease liabilities
- 8-K earnings releases for Q4 2022, Q4 2024, Q4 2025 and Q2 2026
- 8-K of 27-Jan-2026 (SEC settlement)

**Market inputs:**

| Input | Value | Source |
|---|---|---|
| 10-year Treasury | 5.00% (26-Oct-2026) | FRED DGS10 |
| Implied equity risk premium | 4.20% (1-Oct-2026) | Damodaran |
| Price, beta, analyst target, 52-week range, peer multiples | various | StockAnalysis.com, retrieved 28-Oct-2026 |

## Method
1. **Historical (FY2021-FY2025, 1H2025, 1H2026).**
   - EBIT excludes equity-method earnings (Wilmar and others). This matches StockAnalysis's EBITDA basis: rebuilt ADM TTM EBITDA is $2.984bn vs. their $3.00bn.
   - FY2021-22 segment figures are as originally reported, before the 2024 recast.
2. **Projections (FY2026E-FY2030E).**
   - Revenue: +4.4% in FY2026 (1H run-rate), then 3.0%, 3.0%, 2.5%, 2.5%.
   - EBIT margin: 3.00% rising to 3.09%, the FY2021-25 average.
   - D&A: 10.8% of beginning PP&E.
   - Capex: $1.4bn guidance midpoint in FY2026, then 1.53% of revenue.
   - Working capital: 9.8% rising to 11.0% of revenue.
   - Debt is flat; cash balances the statements, and the balance sheet ties every year.
3. **WACC.**
   - Cost of equity 8.16%: 5.00% + 0.75 Blume-adjusted beta (0.67 x 0.63 + 0.33) x 4.20%.
   - Pre-tax cost of debt 6.59%, with a 17.8% tax rate.
   - Weights: 80.1% equity, 19.9% debt including leases.
4. **DCF.**
   - Valuation date: 30-Jun-2026, mid-period discounting.
   - Gordon terminal value: steady-state working-capital reinvestment at g, discounted mid-year.
   - Exit-multiple terminal value: 10.72x, the peer median of BG, INGR, DAR and ANDE, discounted from year-end.
   - Bridge: deducts debt, leases, temporary equity and NCI; adds cash and affiliates at book. Pensions are not deducted.
   - Value per diluted share is rolled forward to 28-Oct-2026 at the cost of equity, less the $0.52 dividend paid since the valuation date.
5. **Sensitivity.** Two 5x5 grids (WACC x g, WACC x multiple) that recompute the full DCF, plus a raw-beta case.
6. **Comps.** Four peers from one provider; the sheet shows n per statistic. EV/Sales is shown but not used.

## Use
- Blue cells are inputs, black are formulas, green are cross-sheet links, yellow are key assumptions and outputs.
- Change inputs on `Inputs & Sources`. Every sheet updates.
- `Cover!C19` is the balance-sheet check; it reads 0.

## Limitations
- Beta is third-party (StockAnalysis 5Y), not my own regression.
- Affiliates are valued at book, not market.
- Pension obligations are not deducted.
- Debt and share count are held flat.
- The price is the 27-Oct close implied by StockAnalysis's 28-Oct quote. Their history table ends at the 26-Oct close of $79.01.
