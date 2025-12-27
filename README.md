# Book Genre Analysis by Age Group

## Overview
This project investigates whether readers’ genre preferences are influenced by their age. The analysis is conducted in R using SQL Server as the data source. It includes data cleaning, exploratory data analysis, statistical summaries, and visualization.

## Objective
- Explore the relationship between age groups and book genre preferences.
- Compare average ratings for different genres by age group.
- Visualize engagement through ratings and review counts.

## Dataset
The dataset was compiled from Goodreads and includes:
- `books.csv`: Book metadata (authors, title, average rating, genre, etc.)
- `ratings.csv`: User ratings (1–5 stars)
- `book_tags.csv` & `tags.csv`: Optional genre tags
- Cleaned dataset saved as `cleaned_books.csv`

### Columns
| Column | Description |
|--------|-------------|
| id | Internal row index |
| book_id | Unique book identifier |
| work_id | Work identifier (aggregated across editions) |
| books_count | Number of editions |
| isbn / isbn13 | International Standard Book Numbers |
| authors | Author(s) name |
| original_publication_year | Year of first publication |
| original_title | Main book title |
| language_code | Language code |
| average_rating | Average rating (1–5) |
| ratings_count | Total ratings submitted |
| work_ratings_count | Ratings across all editions |
| work_text_reviews_count | Number of text reviews |
| ratings_1–ratings_5 | Counts of 1–5 star ratings |
| category | Genre: Fantasy/Adventure or Real-World Fiction |
| age_group | Reader age group: young or adult |

## Project Workflow
1. **Connection**: Establish SQL Server connection using `DBI` and `odbc`.
2. **Data Cleaning**: Remove duplicates, handle missing values, add new columns (`work_rating`), remove unnecessary fields.
3. **Exploratory Data Analysis (EDA)**: 
   - Ratings distribution
   - Book count by genre
   - Age group vs genre heatmaps and mosaic plots
4. **Data Analysis**: 
   - Compare engagement and average ratings between age groups
   - Evaluate thesis and antithesis
5. **Visualizations**: 
   - Scatter plots, bar charts, radial charts, interactive Plotly charts

## Key Findings
- Adults engage more with Real-World Fiction and give higher 5-star ratings.
- Young readers enjoy Fantasy/Adventure Fiction but show less overall engagement.
- Real-World Fiction has the highest number of reviews and ratings, especially from adults.

## Tools and Libraries
- **R Packages**: `dplyr`, `tidyr`, `ggplot2`, `ggmosaic`, `reshape2`, `scales`, `plotly`
- **Database**: SQL Server (via ODBC)

## How to Run
1. Clone the repository:
```bash
git clone https://github.com/yourusername/book-genre-analysis.git
