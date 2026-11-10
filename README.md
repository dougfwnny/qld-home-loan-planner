# QLD Home Loan Planner

A free, open-source home loan planner for Queensland, Australia. Work out your repayment, the deposit you need, what you can afford and the income a bank will want to see, with stamp duty, LMI and buying costs included.

**Use it here:** https://dougfwnny.github.io/qld-home-loan-planner/

![QLD Home Loan Planner](docs/screenshot.png)

It is a single HTML file with no build step, no sign-up and no tracking. Your inputs stay in your browser.

## What it does

**Three ways to start**

- **I have a deposit:** enter the price and deposit to see the monthly, fortnightly and weekly repayment.
- **Target repayment:** enter the repayment you want and see the deposit you need.
- **What can I afford:** enter your savings and maximum repayment to see the highest price that works.

**Cash you need to buy**

- Queensland transfer (stamp) duty, including the first home concession for established homes, the full exemption for new first homes, and the home concession rate.
- 8% AFAD for temporary residents and foreign buyers.
- Estimated lenders mortgage insurance (LMI) when the deposit is under 20%.
- The federal 5% Deposit Scheme, which waives LMI up to the A$ 1M cap for Brisbane, the Gold Coast and the Sunshine Coast.
- Other costs such as conveyancing, building and pest inspection, and registration.

**Bank approval**

- Minimum gross income to get approved and a comfortable income where the repayment is 30% of gross income or less.
- A step-by-step view of how a lender assesses you: net income, living expenses (HEM benchmark), other debts and credit cards, the repayment tested at your rate plus 3%, and your debt-to-income ratio.
- A table of minimum income by property price and deposit (5%, 10%, 20%).
- Settings for a single borrower or couple, children, your own income, expenses, other loans and card limits.

**What if rates change?**

- Repayments at your rate −0.5%, +0.5%, +1% and +3% (the bank's stress test).

## Assumptions

The figures were checked on 9 November 2026. They change over time, so treat every result as an estimate.

| Item | Value used | Source |
|---|---|---|
| Default interest rate | 6.75% p.a. variable, owner-occupier, P&I | Canstar estimate after the RBA raised the cash rate to 4.85% on 3 Nov 2026 |
| Stamp duty | QRO general, home concession and first home concession rates for contracts from 1 Aug 2026 | Queensland Revenue Office |
| AFAD | 8% of the price | Queensland Revenue Office |
| LMI | Average Helia/QBE rate by LVR, plus 9% QLD duty on the premium | Published premium tables |
| 5% Deposit Scheme cap | A$ 1,000,000 (Brisbane, Gold Coast, Sunshine Coast) | Housing Australia |
| Serviceability buffer | Rate + 3 percentage points | APRA |
| Debt-to-income | 6 times gross income or less | APRA DTI limit |
| Income tax | 2026-27 resident rates plus 2% Medicare levy, no offsets | ATO rates |
| Living expenses | Higher of your figure and an approximate HEM benchmark | Published HEM estimates |
| Credit cards | 3.8% of the total limit per month | Lender guidelines |

Every lender has its own formula, so the approval figures are a range rather than a promise. First Home Owner Grant, FIRB fees, insurance, council rates and body corporate fees are not included.

## Updating the numbers

Everything lives in `index.html`. The values most likely to need updates are:

- `DEFAULTS` — default price, deposit, rate and term
- `dutyGeneral`, `dutyHome`, `firstHomeConcession` — Queensland stamp duty scales
- `LMI_PTS` — LMI premium by LVR
- `SCHEME_CAP` — 5% Deposit Scheme price cap
- `incomeTax` — income tax brackets and Medicare levy
- `HEM_T`, `HEM_KID3` — living expense benchmarks
- `testRate` — the serviceability buffer (rate + 3)
- the `0.038` card factor in `commitments` and the DTI limit of `6` in `minIncome` and `maxLoan`
- the rate hint and the "Rates as of" line in the page header

## Run it locally

Download `index.html` and open it in a browser. There is nothing to install. The page loads two fonts from Google Fonts and falls back to system fonts when offline.

## Privacy

All calculations run in your browser. Your inputs are saved only in that browser's local storage so they are still there next time. Nothing is sent to a server.

## Contributing

Issues and pull requests are welcome, especially rate and rule updates, corrections, and support for other states.

## Disclaimer

This tool gives general estimates for planning. It is not financial, tax or legal advice. Check your figures with the Queensland Revenue Office, your lender or a mortgage broker before you make a decision.

## License

[MIT](LICENSE)
