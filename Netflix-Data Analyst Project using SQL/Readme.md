# Netflix Data Analysis Project Using SQL

![Netflix](https://upload.wikimedia.org/wikipedia/commons/0/08/Netflix_2015_logo.svg)

## Overview

This project performs an in-depth analysis of Netflix's content catalog using **PostgreSQL**. It covers 15 real-world business problems, providing actionable insights about the types of content available on Netflix, trends over time, content by country, genre distributions, and more.

---

## Dataset

The dataset (`netflix_titles.csv`) contains information about all Movies and TV Shows available on Netflix. It includes the following columns:

| Column         | Data Type     | Description                                      |
|----------------|---------------|--------------------------------------------------|
| `show_id`      | VARCHAR(5)    | Unique identifier for each title                 |
| `type`         | VARCHAR(10)   | Content type – `Movie` or `TV Show`              |
| `title`        | VARCHAR(250)  | Title of the content                             |
| `director`     | VARCHAR(550)  | Director(s) of the content                       |
| `casts`        | VARCHAR(1050) | Cast members                                     |
| `country`      | VARCHAR(550)  | Country/countries of production                  |
| `date_added`   | VARCHAR(55)   | Date the content was added to Netflix            |
| `release_year` | INT           | Year the content was originally released         |
| `rating`       | VARCHAR(15)   | Content rating (e.g., PG-13, TV-MA)              |
| `duration`     | VARCHAR(15)   | Duration in minutes (Movies) or seasons (TV Shows)|
| `listed_in`    | VARCHAR(250)  | Genre(s) / categories                            |
| `description`  | VARCHAR(550)  | Brief description of the content                 |

---

## Database Schema

```sql
DROP TABLE IF EXISTS netflix;
CREATE TABLE netflix (
    show_id      VARCHAR(5),
    type         VARCHAR(10),
    title        VARCHAR(250),
    director     VARCHAR(550),
    casts        VARCHAR(1050),
    country      VARCHAR(550),
    date_added   VARCHAR(55),
    release_year INT,
    rating       VARCHAR(15),
    duration     VARCHAR(15),
    listed_in    VARCHAR(250),
    description  VARCHAR(550)
);
```

---

## Business Problems & Solutions

The project solves the following 15 business problems:

| # | Problem Statement |
|---|-------------------|
| 1 | Count the number of Movies vs TV Shows |
| 2 | Find the most common rating for movies and TV shows |
| 3 | List all movies released in a specific year (e.g., 2020) |
| 4 | Find the top 5 countries with the most content on Netflix |
| 5 | Identify the longest movie |
| 6 | Find content added in the last 5 years |
| 7 | Find all movies/TV shows by director **Rajiv Chilaka** |
| 8 | List all TV shows with more than 5 seasons |
| 9 | Count the number of content items in each genre |
| 10 | Find the top 5 years with the highest average content releases from India |
| 11 | List all movies that are documentaries |
| 12 | Find all content without a director |
| 13 | Find how many movies actor **Salman Khan** appeared in during the last 10 years |
| 14 | Find the top 10 actors with the most appearances in Indian-produced movies |
| 15 | Categorize content as **'Bad'** (contains 'kill' or 'violence') or **'Good'** and count each |

All SQL solutions are available in [`Solutions of 15 business problems.sql`](./Solutions%20of%2015%20business%20problems.sql).

---

## Project Files

```
├── netflix_titles.csv                      # Raw dataset
├── Schemas.sql                             # Table creation script
├── Business Problems Netflix.sql           # List of 15 business problems
├── Solutions of 15 business problems.sql  # SQL queries solving each problem
└── README.md                               # Project documentation
```

---

## Technologies Used

- **PostgreSQL** – relational database and SQL engine
- **SQL** – data querying and analysis
  - Window functions (`RANK() OVER`)
  - CTEs (`WITH` clause)
  - String functions (`UNNEST`, `STRING_TO_ARRAY`, `SPLIT_PART`, `ILIKE`)
  - Date functions (`TO_DATE`, `EXTRACT`, `CURRENT_DATE`, `INTERVAL`)

---

## How to Run

1. **Set up PostgreSQL** on your local machine or use any cloud-hosted PostgreSQL instance.
2. **Create the table** by running `Schemas.sql`.
3. **Import the dataset** – load `netflix_titles.csv` into the `netflix` table:
   ```sql
   COPY netflix FROM '/path/to/netflix_titles.csv' DELIMITER ',' CSV HEADER;
   ```
4. **Run the queries** in `Solutions of 15 business problems.sql` to explore the analysis results.

---

## Key Insights

- **Movies dominate** the Netflix catalog compared to TV Shows.
- **TV-MA** is the most common rating across both content types.
- The **United States, India, and the United Kingdom** are among the top content-producing countries.
- A significant portion of Netflix content **lacks director information**.
- Content flagged as **'Bad'** (containing keywords like 'kill' or 'violence') forms a notable subset of the catalog.

---

## Author

**Abinesh** – [GitHub Profile](https://github.com/pavithra-576)

---

## License

This project is open-source and available under the [MIT License](LICENSE).
