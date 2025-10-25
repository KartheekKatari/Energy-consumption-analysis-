# Energy-consumption-analysis-


# World Wide Energy Consumption

This data was taken from an aia organization that tracks energy consumption, emissions, production, population etc for different countries.

I hope you enjoy the observations you make as they will reflect reality and help you understand the correlation between economical power, consumption and emission.

---

## Understanding  Data Files:

### 🌍 Database Context

Working with a structured energy dataset comprising 6 CSV files that have been imported into a MySQL database named `energy`. These tables include Dataset:

- country (central table)
- consumption
- production
- emission
- gdp_ppp
- population

Each of the tables (except country) has a foreign key referencing the country table's country column.

---

- SQL query to create tables

```
CREATE DATABASE ENERGYDB2;
USE ENERGYDB2;

-- 1. country table
CREATE TABLE country (
  CID VARCHAR(10) PRIMARY KEY,
  Country VARCHAR(100) UNIQUE
);

SELECT * FROM COUNTRY;

-- 2. emission_3 table
CREATE TABLE emission_3 (
  country VARCHAR(100),
  energy VARCHAR(100),
  year INT,
  emission INT,
  per_capita_emission DOUBLE,
  FOREIGN KEY (country) REFERENCES country(Country)
);

SELECT * FROM EMISSION_3;

-- 3. population table
CREATE TABLE population (
  countries VARCHAR(100),
  year INT,
  Value DOUBLE,
  FOREIGN KEY (countries) REFERENCES country(Country)
);

SELECT * FROM POPULATION;

-- 4. production table
CREATE TABLE production (
  country VARCHAR(100),
  energy VARCHAR(50),
  year INT,
  production INT,
  FOREIGN KEY (country) REFERENCES country(Country)
);

SELECT * FROM PRODUCTION;

-- 5. gdp_3 table
CREATE TABLE gdp_3 (
  Country VARCHAR(100),
  year INT,
  Value DOUBLE,
  FOREIGN KEY (Country) REFERENCES country(Country)
);

SELECT * FROM GDP_3;

-- 6. consumption table
CREATE TABLE consumption (
  country VARCHAR(100),
  energy VARCHAR(50),
  year INT,
  consumption INT,
  FOREIGN KEY (country) REFERENCES country(Country)
);

SELECT * FROM CONSUMPTION;
```

---

### Procedure to work with the files

1. Create a database
2. In the navigator section select the created database and right click on it
3. Select “Table Data Import Wizard” and get the csv file one by one from the dataset provided (kindly first download the csv file in your systems from the drive link provided).
4. Once data is imported, use alter to create relationships between the tables
   Note: check the er-diagram to create relationships between the tables

---

## Data Analysis Questions

- General & Comparative Analysis
  - What is the total emission per country for the most recent year available?
  - What are the top 5 countries by GDP in the most recent year?
  - Compare energy production and consumption by country and year.

---

### Specific Questions

- Which energy types contribute most to emissions across all countries?
- Trend Analysis Over Time
  - How have global emissions changed year over year?
- What is the trend in GDP for each country over the given years?
- How has population growth affected total emissions in each country?
- Has energy consumption increased or decreased over the years for major economies?
- What is the average yearly change in emissions per capita for each country?
- Ratio & Per Capita Analysis
  - What is the emission-to-GDP ratio for each country by year?
- What is the energy consumption per capita for each country over the last decade?
- How does energy production per capita vary across countries?
- Which countries have the highest energy consumption relative to GDP?
- What is the correlation between GDP growth and energy production growth?
- Global Comparisons
  - What are the top 10 countries by population and how do their emissions compare?
  - Which countries have improved (reduced) their per capita emissions the most over the last decade?
  - What is the global share (%) of emissions by country?
  - What is the global average GDP, emission, and population by year?

---


---
