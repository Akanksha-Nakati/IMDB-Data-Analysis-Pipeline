# 🎬 IMDB Data Analysis Pipeline

> Turning decades of movie data into insights that actually matter

## What's This About?

Let's be honest—IMDB has a goldmine of data, but it's messy, massive, and not exactly analysis-ready. This project takes those raw datasets (we're talking millions of records about movies, ratings, directors, and more) and transforms them into something you can actually query and learn from.

Think of it as building the foundation for answering questions like: "What makes a 9+ rated movie?" or "Which genres dominated the 2010s?" or "Do bigger budgets really mean better ratings?"

## The Pipeline

### 1. **Ingest & Parse**
Started with IMDB's public datasets—compressed TSV files with cryptic column names and inconsistent formatting. Used PySpark to load these massive files into DataFrames without breaking a sweat.

Key files processed:
- `title.basics.tsv.gz` → Movie metadata
- `title.ratings.tsv.gz` → User ratings
- `title.crew.tsv.gz` → Directors and writers

### 2. **Clean & Filter**
Raw data is never pretty. Filtered out TV episodes, shorts, and incomplete records to focus on full-length films with valid release years and ratings. Because nobody wants null values ruining their analysis.

### 3. **Transform & Enrich**
This is where the magic happens. Joined multiple datasets to create a comprehensive view of each film—combining ratings with crew info, genres with release years, all in a normalized schema that makes downstream queries fast and painless.

### 4. **Store in Delta Lake**
Leveraged Delta Lake for versioned, reliable storage. This means the data stays consistent, queries run faster, and you can time-travel through data versions if needed (yes, that's actually a thing).

## Tech Stack

- **Databricks**: The command center for everything
- **PySpark**: Because processing millions of rows needs distributed computing
- **Delta Lake**: For storage that doesn't break when your data scientist runs wild queries
- **Python**: Gluing it all together

## Why This Matters

Data engineering isn't just about moving data from A to B. It's about making data usable, trustworthy, and ready to answer questions that matter. This pipeline does exactly that—it takes chaotic raw files and turns them into a structured foundation for real analysis.

Whether you're building a recommendation engine, studying film trends, or just curious about what makes movies tick, this pipeline gives you a head start.

## What I Learned

- **Scale matters**: What works on 1,000 rows doesn't work on 10 million
- **Data quality is everything**: Garbage in, garbage out is real
- **Design with the end in mind**: Every transformation should serve a clear analytical purpose
- **Databricks is powerful**: But you need to understand Spark to use it right

## Future Enhancements

- Add box office revenue data for financial analysis
- Implement automated data refresh pipelines
- Build predictive models on top of this cleaned dataset
- Create visualization dashboards to surface insights


