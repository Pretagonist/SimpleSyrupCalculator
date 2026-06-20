# SimpleSyrupCalculator

A simple, single-file web app for accurately calculating simple syrup ingredients.

Open [`index.html`](index.html) in any browser — no build step, no dependencies.

## Features

- **Metric or Imperial** — grams / mL, or weight-ounces / fluid-ounces.
- **Ratios** — 1:1 (standard) or 1:2 (thin), sugar : water by weight.
- **Solve from any direction** — specify the sugar you have, the water you have,
  the final syrup *volume* you want, or the final syrup *weight* you want.

## The accurate part

Dissolving sugar in water is **not** volume-additive:
`100 g sugar + 100 mL water ≠ 200 mL`. It weighs 200 g but measures only
~163 mL, because sugar molecules pack into the spaces between water molecules.

The calculator works in **mass** (the ratio is by weight) and converts the
total mass to volume using the measured **density of a sucrose solution** at
20 °C, interpolated from standard NBS/ICUMSA reference tables. Density depends
on concentration (°Brix = sugar % by weight):

| Ratio (sugar:water) | °Brix | Density (g/mL) |
| ------------------- | ----- | -------------- |
| 1:1                 | 50.0  | 1.230          |
| 1:2                 | 33.3  | 1.143          |
