# Applied Data Science Capstone: SpaceX Falcon 9 Landing Prediction

Predicts whether SpaceX's Falcon 9 first stage will land successfully, using historical launch data. A successful landing means the booster can be reused, which is the main reason SpaceX can offer launches at a fraction of the cost of competitors — so predicting landing success is effectively a proxy for predicting launch cost.

## Project Structure

| Notebook / File | What it does |
|---|---|
| `Data Collection API.ipynb` | Pulls historical launch data from the SpaceX REST API |
| `Data Collection with Web Scraping.ipynb` | Scrapes supplementary Falcon 9 launch records from Wikipedia with BeautifulSoup |
| `Data Wrangling.ipynb` | Cleans and prepares the combined dataset, engineers the binary landing-outcome label |
| `EDA with Data Visualization.ipynb` | Explores relationships between flight number, payload mass, launch site, and landing outcome using Seaborn |
| `EDA with SQL.ipynb` | SQL queries against the launch dataset to answer specific questions (e.g. success rate by site) |
| `Interactive Visual Analytics with Folium.ipynb` | Interactive map of launch sites and their proximity to coastlines, highways, and railways |
| `Machine Learning Prediction.ipynb` | Trains and tunes 4 classification models to predict landing outcome |
| `dash_app.py` | Interactive Plotly Dash dashboard — dropdown site selector, payload range slider, live-updating pie and scatter charts |
| `Capstone_Presentation.pdf` | Final summary presentation of methodology and results |

## Machine Learning Results

Four classification models were tuned via `GridSearchCV` (10-fold cross-validation) on an 80/20 train/test split:

| Model | Best CV Accuracy | Test Accuracy |
|---|---|---|
| Logistic Regression | 84.6% | 83.3% |
| SVM (sigmoid kernel) | 84.8% | 83.3% |
| **Decision Tree** | **88.9%** | 83.3% |
| KNN | 84.8% | 83.3% |

All four models scored identically on the held-out test set (83.3% accuracy, F1 = 0.889) — expected given the small test set size (18 samples). To break the tie, all models were also evaluated on the full dataset, where the **Decision Tree classifier performed best** (91.1% accuracy, 0.938 F1, 0.882 Jaccard score), making it the selected final model.

## Interactive Dashboard

`dash_app.py` is a Plotly Dash app with:
- A launch-site dropdown (All Sites, CCAFS LC-40, VAFB SLC-4E, KSC LC-39A, CCAFS SLC-40)
- A live-updating pie chart of success rate by site
- A payload-mass range slider
- A scatter plot correlating payload mass with landing outcome, colored by booster version

## Tools & Libraries

Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, SQL, BeautifulSoup, Folium, Plotly Dash

## Key Takeaway

Booster reuse (successful landing) is central to SpaceX's cost advantage — Falcon 9 launches are priced at $62M versus $165M+ for comparable competitor launches, largely because SpaceX can recover and refly the first stage. This project frames landing prediction as a proxy for that cost advantage.
