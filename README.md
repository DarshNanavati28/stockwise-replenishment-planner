# Stockwise — Replenishment Planner

A standalone, browser-based inventory planning demo. Open index.html directly or publish it with GitHub Pages. It uses sample product and daily demand history; edit a product's stock, costs, lead-time assumptions, and demand series in the planner.

## What it does

- Calculates reorder points and safety stock using demand and supplier lead-time variation.
- Shows the selected target service level and z factor on each recommendation.
- Keeps unusual demand visible; users can classify events as promotion, data error, or unknown.
- Compares a robust recent forecast with a simple training-period average on a later holdout period.
- Simulates demand surges and supplier delays, with updated quantities, annual cost estimates, and stockout risk.
- Exports recommendations to CSV.

## Formulas and assumptions

ROP = mean daily demand × mean lead time + z × sqrt(mean lead time × demand variance + mean daily demand² × lead-time variance). Safety stock is the z-scaled variability term. The forecast uses recent seven-day demand; classified one-off events are winsorized to the historical 90th percentile and data errors are excluded. EOQ = sqrt(2 × annual demand × order cost / annual holding cost per unit). Assumptions: independent demand and lead time, approximately normal lead-time demand, stable forecast during lead time, and no minimum-order or pack-size constraints.

## GitHub Pages

The included workflow publishes the repository root on pushes to main and supports manual deployment. In repository settings, choose GitHub Actions as the Pages build and deployment source if prompted.
