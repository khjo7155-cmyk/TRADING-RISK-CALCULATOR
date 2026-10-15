# Trading Risk Lab

A lightweight browser-based calculator for exploring trading risk management: compounded drawdown, losing-streak probability, expectancy, break-even win rate, and recovery returns.

## Who it is for
- Retail traders testing risk assumptions
- Students learning probability and drawdown concepts
- Developers building transparent trading tools
- Trading communities discussing risk management

## Features
- Cash risk based on starting balance and risk percentage
- Compounded drawdown after consecutive losses
- Dynamic-programming estimate of at least one losing streak in a sample
- Consecutive losses needed to reach a drawdown limit
- Simple expectancy in R and break-even win rate
- Recovery return after drawdown
- Client-side calculations; no data is sent to a server

## Run
Open `index.html` in a modern browser. No dependencies or build step are required.

## Formulas and assumptions
For risk fraction r and k consecutive losses, assuming each loss risks a fixed fraction of current equity:

`DD = 1 - (1-r)^k`

For win rate w, loss rate q = 1-w, and average winning reward R measured in risk units:

`Expectancy (R) = w × R - q`

Break-even win rate under this simplified model is `1/(R+1)`. Recovery return after drawdown d is `d/(1-d)`.

The streak probability assumes independent trades and a stable win rate. The probability of one preselected sequence of k losses (`q^k`) differs from the probability of at least one such streak anywhere in N trades; the app estimates the latter using dynamic programming.

## Limitations
This is an educational model, not a forecast or financial advice. It does not model fees, spread, slippage, partial exits, correlated trades, changing win rates, static-cash risk, or instrument-specific contract sizing. Expectancy assumes full wins or full losses.

## Contributing
Formula reviews, reproducible bug reports, documentation improvements, and tested feature suggestions are welcome. Please document assumptions in proposed changes.

## License
MIT. See [LICENSE](LICENSE).
