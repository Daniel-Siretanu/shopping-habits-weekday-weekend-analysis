# Weekend vs. Weekday Shopping: A Real-Data Study

Two-sample hypothesis testing, from theory to a real 541,909-transaction dataset.

-  [Read the writeup](shopping-habits-writeup.pdf) — full proofs of the two-sample $t$-test / linear regression equivalence and Welch's test.
-  [Explore the notebook](shopping-habits-analysis.ipynb) — the empirical analysis on real UK retail transaction data.

## The Question

Is there a significant difference between weekend and weekday shopper spending? This question is
shown to be a special case of simple linear regression on a single binary indicator variable, with
the regression $t$-statistic proven to coincide exactly with the classical pooled two-sample
$t$-statistic under variance homogeneity. When that assumption fails, the Behrens–Fisher problem and
Welch's approximate solution are derived in full.

## Key Findings

- **The equivalence holds exactly.** Under variance homogeneity, the regression $t$-statistic and the classical pooled two-sample $t$-statistic are proven to coincide exactly.
- **A realistic sample can miss a real effect.** A $500$-shopper sample gives $p\approx0.31$ on a real, small population-level spending gap (~\$10) — nowhere near significant — while the same trimming procedure applied to the full population of over 18,000 real orders gives $p<0.05$: the effect is genuinely there, the sample just lacked the power to detect it.
- **Pooled and Welch diverge.** In a balanced design the two tests' $t$-statistics coincide exactly, yet their $p$-values still differ whenever the two groups' variances differ. At the population level, the gap between the two tests widens for two reasons: group sizes are far from equal, and the possibility that the assumption of homogeneity of variance fails between weekend and weekday spending.

## Data

UCI "Online Retail" dataset (Chen, D., 2015, CC BY 4.0) — 541,909 real, timestamped transactions
from a UK-based online retailer, Dec 2010–Dec 2011.
