# Formula 1 Race Intelligence Dashboard (2010–2026)

## About the Project
https://public.tableau.com/authoring/F1RaceIntelligenceDashboardAnalysis2010-2026_17935450827200/Dashboard1#1
This project explores Formula 1 race data from 2010 to 2026 using Tableau Public. The goal was to analyze race results, driver performance, constructor standings, tyre strategies, and mechanical failures through interactive dashboards.

The project uses an Excel dataset containing five related tables and more than 6,400 race result records. I organized the data in Tableau using relationships between the tables and created dashboards to explore different aspects of Formula 1.

The analysis is divided into three main sections:

* **Constructor Strategy:** Comparing constructor performance over different seasons and studying tyre compound performance across circuit types.
* **Driver and Race Analysis:** Exploring driver points, career performance, and the geographical distribution of Grand Prix circuits.
* **Reliability Analysis:** Examining DNF records, identifying common mechanical failures, and comparing reliability across constructors.

## Dataset and Data Model

The project uses `F1 Racing Project Dataset.xlsx`, which contains five sheets covering different parts of Formula 1 race data.

| Table                    | Records | Main Information                                                 |
| ------------------------ | ------: | ---------------------------------------------------------------- |
| `race_results`           |   6,464 | Race results, points, finishing positions, teams and DNF details |
| `circuits`               |     382 | Circuit names, countries, circuit types and track lengths        |
| `championship_standings` |   1,240 | Driver rankings and cumulative championship points               |
| `qualifying_results`     |   6,464 | Starting grid positions and qualifying times                     |
| `lap_intelligence`       | 18,400+ | Fastest laps, tyre compounds and pit-stop information            |

### Table Relationships

The tables are connected using common fields so that information from different parts of the dataset can be analyzed together.

* `race_results` is connected to `circuits` using `Circuit Id`.
* `race_results` is connected to `championship_standings` using `Driver` and `Season`.
* `race_results` is connected to `qualifying_results` using `Race Id` and `Driver`.

These relationships allow the dashboards to combine race, driver, circuit, and qualifying information without treating every sheet as a separate dataset.

## Analysis and Findings

### 1. Constructor Performance and Tyre Strategy

This section focuses on constructor performance across seasons and the relationship between tyre compounds and circuit types.

Some of the questions explored include:

* How have Red Bull Racing and Mercedes performed across different seasons?
* Which constructors have maintained consistent championship performance?
* How does tyre compound selection relate to average points?
* Does tyre performance vary between street, permanent, and hybrid circuits?

The analysis provides a way to compare constructor performance and explore how tyre choices relate to race outcomes.

### 2. Driver Performance and Grand Prix Locations

This section looks at individual driver performance and the geographical distribution of Formula 1 circuits.

The dashboard includes:

* Driver points leaderboards.
* Comparisons of championship performance across seasons.
* A geographical map showing Grand Prix locations.
* Country-wise distribution of circuits.

The map uses distinct circuit counts to avoid counting the same circuit multiple times when displaying geographical information.

### 3. Constructor Reliability and DNF Analysis

This section examines race retirements and the reasons behind them.

The main areas of analysis include:

* DNF counts by constructor.
* Distribution of mechanical failure categories.
* Engine, gearbox, hydraulic, and electrical failures.
* Comparison of reliability issues across teams.

Non-retirement records are excluded from the DNF analysis so that the dashboard focuses on actual retirements rather than completed races.

## Dashboard Features

The Tableau dashboards include the following features:

* **Interactive Filters:** Filter results by constructor, driver, country, and other available fields.
* **Cross-Filtering:** Selecting a value in one chart updates related visualizations.
* **Dynamic Aggregation:** Uses `COUNTD(Race Id)` to count unique races and avoid duplicate counting.
* **DNF Filtering:** Excludes non-retirement records when analyzing retirement reasons.
* **Geographical Visualization:** Displays circuit locations and their distribution across countries.
* **Dashboard Layout:** Uses a 2 × 2 worksheet layout designed for desktop viewing.

## Tools and Technologies

| Tool                  | Purpose                                         |
| --------------------- | ----------------------------------------------- |
| Tableau Public        | Data visualization and dashboard development    |
| Microsoft Excel       | Dataset organization and preparation            |
| Tableau Relationships | Connecting the five data tables                 |
| Calculated Fields     | Aggregations, filtering, and analytical metrics |

## Repository Structure

```text
F1-Race-Intelligence-Dashboard/
│
├── F1 Racing Project Dataset.xlsx
│   └── Source dataset containing five sheets
│
└── README.md
    └── Project documentation
```

## What I Learned

While working on this project, I gained practical experience in:

* Working with relational datasets in Tableau.
* Connecting multiple tables using common keys.
* Creating calculated fields and aggregations.
* Building interactive dashboards with cross-filtering.
* Analyzing race performance and identifying patterns in historical data.
* Presenting analytical findings through visualizations.

The project helped me understand how raw sports data can be organized, analyzed, and presented in a way that makes comparisons and trends easier to explore.
