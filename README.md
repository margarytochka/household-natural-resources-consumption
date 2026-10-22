# Impact of Weather and Socioeconomic Factors on Natural Gas Consumption

Analysis of how outdoor temperature (degree days) and median income relate to household natural gas consumption in five Dutch municipalities, 2012-2021. Course project for *Foundations of Data Analytics* at TU/e.

## Research question

Does household gas consumption depend on weather and income? Specifically:

1. Does relative gas consumption increase with degree days?
2. Is consumption higher when the outdoor temperature is below 5°C?
3. Is there a relationship between consumption and median income?

## Data

| Dataset | Content |
|---|---|
| Gas consumption | Consumption per municipality and household type, 2012-2021 | 
| Weather | Degree days and temperature per municipality |
| Income | Median income per municipality | 

**Municipalities:** Asten, Wageningen, Leidschendam-Voorburg, Enschede, Leudal.
**Household types:** Apartment, Detached house.

The raw data is included in `data/`.

## Methods

- **Exploratory data analysis:** trends in consumption and degree days over time, and relationships between consumption, degree days and income.
- **Linear regression:** relative gas consumption against degree days and median income.
- **One-sided two-sample t-test:** H0: mean consumption is the same below and above 5°C; H1: consumption is higher on colder days. Run separately for apartments and detached houses.
- **Evaluation:** mean absolute error (MAE) of the regression predictions.

## Results

- Relative gas consumption increases with degree days.
- Median income alone shows no visible relationship with relative consumption.
- The t-tests reject H0 for both apartments and detached houses (p < 0.001), supporting higher consumption below 5°C.
- Regression MAE: 7.5 [unit].

<img width="896" height="477" alt="image" src="https://github.com/user-attachments/assets/5c667651-0f3c-4bc5-9e1c-9c658b1697b1" />


## Limitations

- The p-values are extremely small because the samples are large. Consecutive observations are also correlated (cold days cluster), which violates the independence assumption of the t-test, so the p-values overstate the strength of the evidence.
- Only five municipalities, so the results may not generalise to the rest of the Netherlands.
- Income is a municipality-level median and says little about individual households.
- No separate train/test evaluation or baseline model was used to assess the regression.

## Repository structure

```
.
├── data/          # input data (or instructions to download it)
├── notebooks/     # analysis notebook(s)
├── figures/       # plots used in this README
└── README.md
```

## How to run

```bash
git clone https://github.com/[username]/[repo-name].git
cd [repo-name]
pip install -r requirements.txt
jupyter notebook notebooks/[notebook-name].ipynb
```

## Author

Marharyta Nikulina, BSc Computer Science and Engineering, TU/e.
