# SQL_Music_Store_Analysis 

Music Store Data Analysis (PostgreSQL + pgAdmin 4)

## Short description
A complete SQL analysis project on the Chinook digital music store dataset using PostgreSQL and pgAdmin 4, answering business questions about invoices, revenue by city, best customers, rock listeners, top artists, long tracks, and per-country preferences through optimized queries and clear output sets.

## Tech stack
- PostgreSQL: primary RDBMS for running and tuning queries on normalized music store tables such as employees, customers, invoices, invoice_items, artists, albums, tracks, genres, and playlists.

- pgAdmin 4: GUI client used for schema inspection, query execution, and result exports for reporting and documentation.

- SQL: ANSI-compliant SQL with PostgreSQL-specific syntax and CTEs, window functions, and joins for analytics over sales and catalog data.

## Data source
- Chinook sample database, a well-known digital media store schema with 11 core tables: employees, customers, invoices, invoice_items, artists, albums, media_types, genres, tracks, playlists, playlist_track; ideal for realistic SQL analytics on sales and catalog relationships.

- The repository assumes the Chinook schema is loaded into PostgreSQL; the project is database-agnostic in logic but uses PostgreSQL dialect and pgAdmin for execution and results.

## Features and highlights
### Easy set

- Senior-most employee by job title using ordering and tie-safe selection. 

- Countries with most invoices via aggregation over invoices and customers for geographic demand insight.

- Top 3 invoice totals using ORDER BY + LIMIT for high-value sales identification.

- Best revenue city for a promotional event by summing invoice totals grouped by city, returning top city and amount.

- Best customer by total spend across invoice_items and invoices, returning customer details and total purchase value.

### Moderate set

- Rock music listeners: email, first name, last name filtered by tracks linked to Genre = ‘Rock’, ordered alphabetically by email.

- Top 10 rock artists by total track count from tracks joined to albums and artists, filtered by Genre = ‘Rock’.

- Tracks longer than average length: list of Name and Milliseconds above global average with descending order by duration.

### Advanced set

- Spend by each customer on artists: join invoice_items → invoices → customers and tracks → albums → artists, sum per customer-artist pair.

- Most popular genre per country: for each country, return genre(s) with highest purchase count; handles ties using window functions or max-per-group logic.

- Top-spending customer per country: for each country, return customer(s) with maximum spend and the amount, including ties.

### Project structure 

- data/: DDL and seed for Chinook or link to source scripts; environment notes for PostgreSQL import.

- queries/: SQL files organized by Easy, Moderate, Advanced with comments and execution notes.

- reports/: PDF/CSV outputs for key answers, screenshots from pgAdmin 4, and reasoning per query.

### Getting started

- Load Chinook schema into PostgreSQL (DDL/scripts available in the Chinook repository or vendor-specific ports) and connect via pgAdmin 4.

- Run queries in the queries/ folder in order; each file includes assumptions, joins diagram notes, and expected output columns.

### Why Chinook?

- The schema is realistic for digital media stores, with many-to-one and many-to-many relationships that exercise joins, grouping, and window functions, making it excellent for SQL practice and business analytics.

## References
- Chinook schema overview and table relationships for employees, customers, invoices, invoice_items, artists, albums, media_types, genres, tracks, playlists, and playlist_track.

- Setup guidance and cross-database availability of Chinook schema/scripts and ecosystem tooling.

- Typical business questions and deliverables for a “Digital Music Store Data Analysis” project using PostgreSQL and pgAdmin 4.

## Schema- Music Store Database 
![MusicDatabaseScema](https://github.com/tejas2024-d/SQL_Music_Store_Analysis/blob/main/schema_diagram.png)
