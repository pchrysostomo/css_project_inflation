# css_project_inflation
Fall 2022 Project for CSS program

## Description

This work aims to use methods presented in both courses to understand the recent inflation surge in the United States and to predict the dynamics for the next following months. The project was divided into three parts. In the first one, several surveys and macroeconomic data were imported, cleaned, and visualized. As the process was long and required many lines of code, the first part was kept only in the auxiliary files. The second part of the work describes, with text and graphics, relevant macroeconomic events that have occurred since the beginning of the pandemic and that are directly related to the recent inflation surge, to then forecast possible future paths, based on the indicators presented throughout the narrative. Finally, the third and last part uses a quantitative approach, where the forecast is carried out from traditional univariate models, Random Walk and ARIMA, but also by a LASSO, which allows including the collected data in a predictive model. Both approaches point in the direction that US inflation will decelerate over the coming months.

## Project structure and Data files

Because there are many different datasets, the project has 3 sub-directories:  

**Project**  
- \\update: jupyter notebooks to update the data.
- \\data: sub directories to store the parquet files.
- \\notebooks: jupyter notebook with plots.

Below, I have listed the name of the surveys/data, how they were imported, a reference link, and where to find the codes to import the data. 

To see the charts, take a look at the `notebooks` folder. I made some charts for Inflation (here I went step-by-step on how I built the functions that are saved in the `functions.py` file), Activity, Employment, Fiscal/Trade, Monetary policy, Financial Markets and Business surveys.

**1. Economic Activity**

- GDP | API | [BEA](https://www.bea.gov/news/2022/gross-domestic-product-third-quarter-2022-advance-estimate)| `update\\bea_nipa.ipynb`
- Real Personal Consumption Expenditure | API | [BEA](https://www.bea.gov/news/2022/personal-income-and-outlays-september-2022) | `update\\bea_nipa.ipynb`
- Real Personal Income | API | [BEA](https://www.bea.gov/news/2022/personal-income-and-outlays-september-2022)| `update\\bea_nipa.ipynb`
- Real Personal Savings | API | [BEA](https://www.bea.gov/news/2022/personal-income-and-outlays-september-2022)| `update\\bea_nipa.ipynb`
- Advanced Retail Sales | API | [Census](https://www.census.gov/retail/index.html#marts)| `update\\census.ipynb`
- Industrial Production | .csv files | [FED](https://www.federalreserve.gov/datadownload/Choose.aspx?rel=G17)| `update\\fed.ipynb`
- Capital Goods Expenditure | API | [Census](https://www.census.gov/manufacturing/m3/index.html)| `update\\census.ipynb`

**2. Inflation**

- CPI | .txt | [BLS](https://www.bls.gov/cpi/)|`update\\bls_cpi.ipynb` and `update\\bls_cpi_weights.ipynb`
- PPI | .txt | [BLS](https://www.bls.gov/ppi/)|`update\\bls_ppi.ipynb`
- PCE Inflation | API | [BEA](https://www.bea.gov/news/2022/personal-income-and-outlays-september-2022)| `update\\census.ipynb`
- Gasoline Prices | API | [FRED](https://fred.stlouisfed.org/series/GASREGW)| `update\\fred.ipynb`
- Manheim Price Index | PDF/.csv_file | [Manheim](https://publish.manheim.com/en/services/consulting/used-vehicle-value-index.html) and csv from [Moody's](https://www.economy.com/united-states/manheim-used-vehicle-value-index) | `\\data\\inflation\\manheim.csv`

**3. Labor Market**

- Current Employment Statistics | .txt | [BLS](https://www.bls.gov/ces/) | `update\\bls_ces.ipynb`
- Current Population Survey | .txt | [BLS](https://www.bls.gov/cps/) | `update\\bls_cps.ipynb`
- JOLTS | .txt | [BLS](https://www.bls.gov/jlt/) | `update\\bls_jolts.ipynb`
- Jobless Claims | PDF/API | [DOL](https://www.dol.gov/agencies/eta/feature-numbers) and [Fred](https://fred.stlouisfed.org/series/ICSA#:~:text=An%20initial%20claim%20is%20a,for%20the%20Unemployment%20Insurance%20program.) | `update\\fred.ipynb`
- Atlanta Fed Wage Tracker | .csv file | [Atlanta Fed](https://www.atlantafed.org/chcs/wage-growth-tracker) | `update\\atlanta_fed.ipynb`

**4. Housing**

- New Home Sales | API | [Census](https://www.census.gov/construction/nrs/index.html) | `update\\census.ipynb`
- Existing Home Sales | PDF/BBG | [NAR](https://www.nar.realtor/research-and-statistics/housing-statistics/existing-home-sales) and [FRED](https://fred.stlouisfed.org/series/EXHOSLUSM495S) (only last 12M observations) | `update\\bloomberg.ipynb`
- Housing Starts | API | [Census](https://www.federalreserve.gov/datadownload/Choose.aspx?rel=H6) | `update\\census.ipynb`
- Building Permits | API | [Census](https://www.census.gov/construction/bps/) | `update\\census.ipynb`
- Mortagage Rate | API | [FRED](https://fred.stlouisfed.org/series/MORTGAGE30US) | `update\\fred.ipynb`
- Case-Shiller Home Price Index | API | [FRED](https://fred.stlouisfed.org/categories/32261) | `update\\fred.ipynb`

**5. Business Surveys**

- ISM Manufacturing | PDF/BBG | [ISM](https://www.ismworld.org/supply-management-news-and-reports/reports/ism-report-on-business/) | `update\\bloomberg.ipynb`
- ISM non-Manufacturing | PDF/BBG | [ISM](https://www.ismworld.org/supply-management-news-and-reports/reports/ism-report-on-business/) | `update\\bloomberg.ipynb`
- Philly Fed M-PMI | .csv file | [Phily Fed](https://www.philadelphiafed.org/surveys-and-data/mbos-historical-data) | `update\\bloomberg.ipynb`
- Philly Fed S-PMI | .csv file | [Phily Fed](https://www.philadelphiafed.org/surveys-and-data/regional-economic-analysis/nonmanufacturing-business-outlook-survey) | `update\\philly_fed.ipynb`
- Empire M-PMI | .csv file | [NY Fed](https://www.newyorkfed.org/survey/empire/empiresurvey_overview) | `update\\ny_fed.ipynb`
- Richmond Fed M-PMI | .xls file | [Richmond Fed](https://www.richmondfed.org/research/regional_economy/surveys_of_business_conditions/manufacturing/about) | `update\\richmond_fed.ipynb`
- NFIB | BBG/API | [NFIB](http://www.nfib-sbet.org/) | `update\\bloomberg.ipynb` and `update\\nfib.ipynb`

**6. Consumer Confidence**

- Michigan Consumer Confidence | .csv files | [Michigan](https://data.sca.isr.umich.edu/tables.php) | `update\\michigan.ipynb`
- Conference Board Consumer Confidence | BBG | [Conf. Board](https://www.conference-board.org/topics/consumer-confidence) | `update\\bloomberg.ipynb`
- Survey of Consumer Expectations | .csv file | [NY Fed](https://www.newyorkfed.org/microeconomics/sce#/) | `update\\ny_fed.ipynb`

**7. Monetary Policy and Financial Market**

- Fed Funds Rate | API | [FRED](https://fred.stlouisfed.org/series/FEDFUNDS) | `update\\fred.ipynb`
- Money Supply | API | [FRED](https://fred.stlouisfed.org/series/M2SL) | `update\\fred.ipynb`
- Market Interest Rates (1, 2, 5, 10 and 30 years) | API | [FRED](https://fred.stlouisfed.org/categories/115) | `update\\fred.ipynb`
- Breakeven Inflation (1, 2, 5, 10 and 30 years) | API | [FRED](https://fred.stlouisfed.org/categories/33446) | `update\\fred.ipynb`
- Fed's 5y5y forward breakeven | API | [FRED](https://fred.stlouisfed.org/series/T5YIFR) | `update\\fred.ipynb`
- S&P 500 | API | [Yahoo Finance](https://finance.yahoo.com/quote/%5EGSPC/) | `update\\yahoo_finance.ipynb`
- Fed Balance Sheet | API | [FRED](https://fred.stlouisfed.org/series/WALCL) | `update\\fred.ipynb`
- Total Households Networth | API | [FRED](https://fred.stlouisfed.org/series/BOGZ1FL192090005Q) | `update\\fred.ipynb`

**8. Fiscal Accounts and Trade**

- Government Revenues and Expenditures | API | [FRED](https://fred.stlouisfed.org/graph/?id=MTSO133FMS,MTSR133FMS,) | `update\\fred.ipynb`
- Imports and Exports | API | [Census](https://www.census.gov/foreign-trade/Press-Release/current_press_release/index.html) | `update\\census.ipynb`
- Trade Defficit | API | [Census](https://www.census.gov/foreign-trade/Press-Release/current_press_release/index.html) | `update\\census.ipynb`
- Dollar Index | API | [FRED](https://fred.stlouisfed.org/series/DTWEXBGS) | `update\\fred.ipynb`
