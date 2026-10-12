# 🎬 Movie Recommender System

A content-based movie recommendation web application built using **Python, Streamlit, FastAPI, and The Movie Database (TMDB) API**. The application allows users to discover movies, search by title, explore movie details, and find similar movies using TF-IDF and genre-based recommendation techniques.

## 🚀 Features

- **Movie Discovery:** Browse trending, popular, top-rated, now-playing, and upcoming movies.
- **Movie Search:** Search movies by title with dropdown suggestions and matching results.
- **Movie Details:** View movie posters, release dates, genres, overviews, and backdrops.
- **TF-IDF Recommendations:** Discover movies with similar textual content using TF-IDF-based similarity.
- **Genre-Based Recommendations:** Explore movies sharing similar genres.
- **Interactive UI:** Navigate between the home page and individual movie detail pages.
- **TMDB Integration:** Retrieve movie information and poster images from TMDB.
- **REST API Backend:** Communicate with a FastAPI backend to fetch movie data and recommendations.

## 🛠️ Tech Stack

| Technology   | Purpose                                          |
| ------------ | ------------------------------------------------ |
| Python       | Core programming language                        |
| Streamlit    | Interactive web application frontend             |
| FastAPI      | Backend REST API                                 |
| Scikit-learn | TF-IDF vectorization and similarity calculations |
| TMDB API     | Movie information and poster images              |
| Requests     | HTTP communication with the backend              |

## 🏗️ System Architecture

1. **User Interface:** Streamlit provides the movie search, home feed, and details pages.
2. **Backend API:** FastAPI processes requests for movie search, details, and recommendations.
3. **Movie Data:** TMDB supplies movie metadata, posters, and related information.
4. **Recommendation Engine:** TF-IDF and genre-based techniques identify similar movies.
5. **Results:** Recommended movies are displayed in an interactive poster grid.

## 📂 Project Structure

```text
movie-recommender/
│
├── app.py                 # Streamlit frontend
├── requirements.txt       # Python dependencies
├── README.md              # Project documentation
└── .gitignore             # Files excluded from Git
```

The FastAPI backend may be maintained in a separate repository or folder, depending on your deployment setup.

## ⚙️ Installation and Setup

### 1. Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd movie-recommender
```

Replace `YOUR_GITHUB_REPOSITORY_URL` with your actual GitHub repository URL.

### 2. Create a Virtual Environment

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

If you do not have a `requirements.txt` file yet, you can create one containing:

```text
streamlit
requests
```

Add any additional dependencies required by your backend or recommendation engine to the appropriate requirements file.

### 4. Configure the Backend URL

In `app.py`, configure the FastAPI backend URL:

```python
API_BASE = "https://movie-rec-466x.onrender.com"
TMDB_IMG = "https://image.tmdb.org/t/p/w500"
```

For local development, use:

```python
API_BASE = "http://127.0.0.1:8000"
```

Make sure the backend is running and its endpoints are accessible before using the application.

### 5. Run the Application

```bash
streamlit run app.py
```

Streamlit will provide a local URL, usually:

```text
http://localhost:8501
```

Open this URL in your browser.

## 🎯 Recommendation Techniques

### 1. TF-IDF-Based Recommendation

TF-IDF (Term Frequency–Inverse Document Frequency) converts textual information into numerical feature vectors. The system can compare movie descriptions or other textual features and identify movies with similar content.

### 2. Genre-Based Recommendation

The genre-based approach recommends movies that share genres with the selected movie. This provides an additional way to discover related films.

**Note:** The quality of recommendations depends on the data and implementation used by the backend.

## 🔌 API Endpoints

The frontend uses the following backend endpoints:

| Endpoint              | Purpose                                            |
| --------------------- | -------------------------------------------------- |
| `/home`               | Retrieve movies for the selected home category     |
| `/tmdb/search`        | Search movies using a title or keyword             |
| `/movie/id/{tmdb_id}` | Retrieve details for a movie                       |
| `/movie/search`       | Retrieve TF-IDF and genre-based recommendations    |
| `/recommend/genre`    | Retrieve genre-based recommendations as a fallback |

The exact response formats depend on your FastAPI backend implementation.

## 🌐 Deployment

The application can be deployed using Streamlit Community Cloud or another platform that supports Streamlit.

For deployment:

1. Push your frontend code to GitHub.
2. Deploy the Streamlit frontend.
3. Ensure the FastAPI backend is deployed and publicly accessible.
4. Configure `API_BASE` with the deployed backend URL.
5. Test movie search, details, and recommendation endpoints.

## 🔮 Future Enhancements

- Add user accounts and personalized recommendations.
- Implement collaborative filtering using user ratings.
- Introduce watchlists and favorite movies.
- Add advanced filters for release year, rating, and genre.
- Improve recommendation quality with hybrid recommendation techniques.
- Add movie ratings and reviews where supported by the data source.
- Optimize API requests and caching for improved performance.

## 📚 Data Source and Attribution

Movie metadata and images are accessed through [The Movie Database (TMDB)](https://www.themoviedb.org/).

This product uses the TMDB API but is not endorsed or certified by TMDB. Follow TMDB's applicable API terms, attribution requirements, and usage policies.

## 👨‍💻 Author

Developed as a Python-based movie discovery and recommendation project to explore web application development, REST APIs, and content-based recommendation techniques.
