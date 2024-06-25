# data-sourcing-challenge
Module 6 Challenge

Movie Recommendation System Data Preparation

1. Overview:
This project involves preparing data for a movie recommendation system by extracting and merging data from two APIs: The New York Times (NYT) and The Movie Database (TMDB). The goal is to gather movie reviews and related details for analysis using natural language processing techniques.

2.Setup:
1. Clone the Repository:
    1. Clone or download the repository to your local machine.
2. Install Dependencies:
    1. Open a terminal or command prompt.
    2. Navigate to the project directory.
3. Run the following command to install required dependencies:
    1. pip install requests pandas python-dotenv

4. Add API Keys:
    1. Create a file named example.env in the root directory.
    2. Add your API keys in the format:
        1. NYT_API_KEY=your_nyt_api_key_here
        2. TMDB_API_KEY=your_tmdb_api_key_here
    3. Rename example.env to .env and save it.

5. Part 1: Access the New York Times API
    Steps:
        1.The Python script accesses the NYT API to fetch movie reviews with specific criteria (e.g., containing "love" in the headline).
        2. It retrieves data such as headline, web URL, snippet, source, keywords, publication date, byline, and word count.
        3. Reviews are fetched from multiple pages (up to 200 results) with a 12-second delay between requests to comply with API limits.
        4. Data is formatted into a Pandas DataFrame, and the movie title is extracted using string manipulation.

6. Part 2: Access The Movie Database API
    Steps:
        1. The script uses the TMDB API to search for movie details based on titles extracted from NYT reviews.
        2. It queries the API to retrieve movie IDs and then fetches full movie details.
        3. Data extracted includes title, original title, budget, language, homepage, overview, popularity, runtime, revenue, release date, vote average, vote count, genres, spoken languages, and production countries.
        4. Results are stored in a Pandas DataFrame for further processing.

7. Part 3: Merge and Clean the Data for Export
    Steps:
        1. Data from NYT reviews and TMDB are merged on the movie title column.
        2. Columns with lists (genres, spoken languages, production countries) are processed to remove list characters ([, ], ') and convert to string format.
        3. Duplicate rows are removed, and the index is reset.
        4. Finally, the cleaned data is exported to a CSV file named merged_data.csv without the index column.

8. Usage
    1. Run the Script:
        1. Open your Python environment.
        2. Execute the script movie_recommendation.py.

    2. Output:
        1. After execution, check the console for status messages.
        2. The cleaned and merged data will be available in merged_data.csv.

9. Troubleshooting
        1. Ensure Python and required libraries are installed correctly.
        2. Verify API keys in the .env file are accurate and properly formatted.

10. Conclusion
    This project demonstrates how to fetch, process, merge, clean, and export data from multiple APIs using Python and Pandas. It provides a foundational understanding for building more complex data pipelines and analysis tools in Python.

Make sure to replace placeholders (like your_nyt_api_key_here and your_tmdb_api_key_here) with your actual API keys and adjust paths and repository names as needed. This README provides a structured guide for someone new to Python and data processing with APIs. If you have any further questions or need more details, feel free to ask!

For any questions reach out to sandokan.stage@du.edu