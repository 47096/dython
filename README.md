# Dython associations

**Demo — relate categorical variables without faking Pearson.**

A short recipe for association heatmaps on non-numeric data (Theil’s U / correlation ratio). Not a client case study — an EDA tool demo.

---

## The question

Pearson only works on numbers. In real tables you have colour, status, type, gender…  
**How do you see which categories move together?**

Dython fills that gap with an association matrix that *looks* like a correlation heatmap (0–1 for categorical pairs).

## What it shows

| Pairing | Method | Range |
|---------|--------|-------|
| Category ↔ category | Theil’s U | 0–1 |
| Category ↔ number | Correlation ratio | 0–1 |
| Number ↔ number | Pearson | −1–1 |

Demo data: `data/pokemon.csv` (vendored) — Pokémon stats — type, legendary flag, numeric attributes.

## When to use it

- Early EDA on survey / CRM / catalogue data  
- Feature shortlists before modelling  
- Teaching association ≠ Pearson  

## Run it

```bash
pip install dython pandas  # notebook uses data/pokemon.csv
git clone https://github.com/47096/dython.git
cd dython
jupyter notebook dython_demo.ipynb
```

```python
from dython.nominal import associations, identify_nominal_columns
cat = identify_nominal_columns(df)
associations(df, nominal_columns=cat)
```

**Stack:** [Dython](https://github.com/shakedzy/dython) · `pandas`

---

*Demo companion — see [datafying](https://datafying.co/) case studies on customer and marketing analytics.*
