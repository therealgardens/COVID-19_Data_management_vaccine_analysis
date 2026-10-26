# COVID-19 Data Management & Analysis

### SQL Database Design, Data Exploration and Visualization with Python

A university project developed for the **Data Management (ET4015)** course, June 2022.

The project focuses on designing and implementing a relational database to analyze the evolution of the COVID-19 pandemic across different countries, exploring confirmed cases, deaths, vaccination campaigns, and vaccine manufacturers.

The analysis combines **SQL for data management and querying** with **Python for data visualization**.

## Project Overview

The main objectives of this project are to:

- Design and implement a relational database using SQLite.
- Integrate multiple datasets containing COVID-19, vaccination, geographical, and demographic information.
- Perform SQL queries to investigate patterns in infections, mortality, and vaccination coverage.
- Compare the evolution of the pandemic across different countries.
- Visualize historical trends using Python, Matplotlib, and Seaborn.

The project follows a complete data management workflow, from importing raw CSV files to relational database construction, SQL analysis, and graphical visualization.

## Technologies Used

- **Python** — Data processing and visualization
- **SQLite / SQL** — Relational database creation, management, and querying
- **Pandas** — CSV import and SQL query results
- **Matplotlib** — Data visualization
- **Seaborn** — Statistical plots and time-series visualization
- **Jupyter Notebook** — Interactive development and analysis

## Datasets

The analysis uses six CSV datasets.

| Dataset | Description |
|---|---|
| `COVID_stati_tutti.csv` | Historical COVID-19 confirmed cases, recovered cases, and deaths by country and date |
| `vaccini.csv` | Vaccination records, including total vaccinations and vaccinated individuals |
| `manifacturer.csv` | Vaccination data categorized by vaccine manufacturer, country, and date |
| `Geography_data.csv` | Country identifiers, names, latitude, and longitude |
| `Population_area.csv` | Population, land area, and demographic information |
| `pollution.csv` | Air quality and water pollution indicators for different cities |

The pollution dataset is imported into the SQLite environment but is not used in the main analytical queries and visualizations.

## Database Design

A relational database was designed to organize the different datasets and connect epidemiological, demographic, and vaccination information.

The database contains five main tables:

| Table | Description |
|---|---|
| `Countries` | Country identifiers, population, area, and geographical coordinates |
| `Covidrecord` | Daily records of confirmed cases, recoveries, and deaths |
| `Vaccinationsrecord` | Vaccination records by country and date |
| `Vaccine_manifacturers` | List of vaccine manufacturers |
| `Vaccinecountries` | Vaccinations administered by country, manufacturer, and date |

Foreign-key relationships connect the records to their corresponding countries and vaccine manufacturers.

### Database Implementation

The implementation follows four main steps:

1. Import the CSV datasets into Pandas DataFrames.
2. Load the DataFrames into temporary SQLite tables.
3. Create the relational database tables using SQL.
4. Populate the tables through SQL `INSERT INTO ... SELECT` statements and relational joins.

All database operations are performed directly within the Jupyter Notebook.

## SQL Analysis

The project includes several SQL queries designed to investigate different aspects of the pandemic.

### 1. Vaccination Coverage by Country

Calculate the proportion of vaccinated individuals relative to each country's total population.

**Vaccination Coverage = Vaccinated Population / Total Population**

This indicator supports comparisons of vaccination coverage between countries.

### 2. Confirmed Cases Relative to Land Area

Compare the number of confirmed COVID-19 cases relative to the geographical area of different countries.

The analysis uses population and geographical information to investigate differences in the territorial distribution of reported infections.

### 3. Relative Mortality by Hemisphere

Investigate COVID-19 mortality relative to population size, distinguishing between countries in the Northern and Southern Hemispheres.

The queries focus on historical observations from **October 2020** and use geographical coordinates to identify each hemisphere.

## Data Visualization

SQL query results are converted into Pandas DataFrames and visualized using Seaborn.

### COVID-19 Evolution in the United Kingdom

Time-series visualizations comparing:

- Confirmed COVID-19 cases
- Reported deaths
- Number of vaccinated individuals

An additional graph focuses exclusively on deaths to improve readability.

### COVID-19 Evolution in Israel

A similar analysis is conducted for Israel, comparing infections, deaths, and vaccination trends.

### Vaccinations by Manufacturer

Visualization of cumulative vaccination totals grouped by vaccine manufacturer.

The analysis includes manufacturers such as Pfizer/BioNTech, Moderna, Oxford/AstraZeneca, and others represented in the dataset.

### Vaccination Coverage Across Countries

Comparison of vaccination coverage over time for eight countries:

- Italy
- France
- Germany
- Brazil
- Switzerland
- Canada
- Australia
- Sri Lanka

The analysis focuses on the period starting in September 2021.

These visualizations provide a comparative view of how vaccination campaigns evolved across countries.

## Repository Structure

The repository contains the following files:

- `Progetto_Covid_DM.ipynb` — Main Jupyter Notebook containing SQL queries, database implementation, and visualizations
- `COVID_stati_tutti.csv` — COVID-19 cases and deaths
- `vaccini.csv` — Vaccination records
- `manifacturer.csv` — Vaccine manufacturer data
- `Geography_data.csv` — Geographical information
- `Population_area.csv` — Population and area data
- `pollution.csv` — Pollution indicators

## How to Run the Project

**1. Clone the repository**

Clone the GitHub repository or download the project files.

**2. Install the required Python libraries**

`pip install pandas numpy matplotlib seaborn notebook`

**3. Open the Jupyter Notebook**

`jupyter notebook Progetto_Covid_DM.ipynb`

**4. Execute the notebook**

Run the cells sequentially to:

- Import the datasets.
- Create the SQLite database.
- Populate the relational tables.
- Execute the analytical SQL queries.
- Generate the visualizations.

All CSV files should remain in the same directory as the notebook.

The SQLite database (`database.db`) is automatically created when the notebook is executed. An existing database with that name in the working directory is removed at the beginning of execution.

## Limitations

The analysis is based on historical COVID-19 datasets and should not be interpreted as representing the current epidemiological situation.

Some vaccination records contain missing observations, zero values, or irregular reporting intervals. These limitations may affect time-series visualizations and aggregated vaccination totals.

Additionally, observed relationships between vaccination trends and COVID-19 outcomes should be interpreted descriptively rather than as evidence of causality.

## Conclusion

This project demonstrates how relational database design, SQL queries, and Python visualizations can be combined to explore complex real-world datasets.

The analysis provides insights into historical COVID-19 trends, differences in vaccination coverage across countries, and the evolution of vaccination campaigns by manufacturer.

Beyond the epidemiological application, the project highlights practical skills in:

- Relational database design
- Data integration and management
- SQL querying and aggregation
- Data analysis
- Data visualization
- Working with real-world datasets

## Authors

**Davide Giardini**  
**Irene Buso**

*Data Management (ET4015) — University Project, June 2022*
