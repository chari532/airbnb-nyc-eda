# Airbnb NYC Bookings — Exploratory Data Analysis

An end-to-end exploratory data analysis (EDA) of Airbnb listings across New York City, covering data cleaning, pricing patterns, host behavior, and guest engagement trends.

## 📌 Problem Statement

Airbnb hosts, guests, and market analysts need to understand pricing patterns, listing distribution, and host behavior across New York City's Airbnb market to make informed decisions — whether that's a host setting competitive prices, a guest choosing a neighbourhood, or an analyst studying market trends.

This project analyzes a raw Airbnb bookings dataset to answer key questions about the NYC short-term rental market through data cleaning and visual analytics.

## 🎯 Objectives

- Clean and preprocess a raw, inconsistent real-world dataset
- Explore listing distribution by room type and neighbourhood group
- Identify pricing patterns across NYC boroughs
- Investigate whether construction year influences price
- Identify high-volume hosts and market concentration
- Examine whether host verification correlates with guest engagement
- Assess the relationship between price and service fees
- Compare review ratings across neighbourhood groups and room types
- Explore how host listing count relates to calendar availability

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| Language | Python 3 |
| Data Handling | pandas, NumPy |
| Visualization | matplotlib, seaborn |
| Environment | Google Colab / Jupyter Notebook |
| Version Control | Git, GitHub |

## 📂 Dataset

`airbnb_bookings.csv` — listing-level data including:
- **Identifiers**: `id`, `host id`, `host name`
- **Location**: `neighbourhood group`, `neighbourhood`
- **Property details**: `room type`, `Construction year`
- **Pricing**: `price`, `service fee`
- **Availability & activity**: `availability 365`, `number of reviews`, `last review`, `review rate number`
- **Host metrics**: `calculated host listings count`, `host_identity_verified`

## 🧹 Data Cleaning Steps

1. Removed duplicate rows
2. Dropped irrelevant columns (`house_rules`, `license`)
3. Cleaned currency fields (`price`, `service fee`) by stripping `$` and `,` characters
4. Converted data types (floats for price/fee, strings for IDs, datetime for review dates, int for construction year)
5. Fixed data-entry typos in `neighbourhood group` (`"brookln"` → `"Brooklyn"`, `"manhatan"` → `"Manhattan"`)
6. Removed logically invalid rows where `availability 365` was negative or exceeded 365 days
7. Dropped rows with missing values

## 📊 Results

| # | Analysis | Key Finding |
|---|---|---|
| 1 | Room type distribution | **Entire home/apt** is most common (42,751), followed by Private room (36,441) |
| 2 | Neighbourhood distribution | **Brooklyn** and **Manhattan** dominate listings; Staten Island has the fewest |
| 3 | Avg price by neighbourhood group | Prices are fairly flat across boroughs (~$620–$631 range) |
| 4 | Construction year vs price | No strong trend — price fluctuates independent of build year |
| 5 | Top hosts by listings | Dominated by corporate hosts — **Sonder (NYC)** (295) and **Blueground** (286) |
| 6 | Reviews vs host verification | Verified and unconfirmed hosts show nearly identical review counts — verification has minimal impact |
| 7 | Price vs service fee | **Strong positive correlation (~1.0)** — service fee scales directly with price |
| 8 | Review rate by segment | Consistent ~3.2–3.8 average across all neighbourhood/room-type combinations |
| 9 | Host listings vs availability | **Weak positive correlation (~0.15)** — more listings per host only slightly increases availability |

*(Charts for each analysis are available in the `/charts` folder of this repo.)*

## 🚀 How to Run

1. Clone this repository
   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
   cd <repo-name>
   ```
2. Install dependencies
   ```bash
   pip install pandas numpy matplotlib seaborn
   ```
3. Open the notebook in Jupyter or upload it to Google Colab
4. Update the CSV file path to match your local/Colab environment
5. Run all cells

## 📁 Repository Structure

```
├── airbnb_analysis.ipynb      # Main analysis notebook
├── airbnb_bookings.csv        # Raw dataset (if included/permitted)
├── charts/                    # Exported chart images
├── README.md                  # Project documentation
└── .gitignore
```

## 🔮 Future Improvements

- Build a price prediction model (regression) using room type, location, and construction year
- Add geospatial mapping of listings using latitude/longitude
- Deploy an interactive dashboard (Streamlit/Dash) for live exploration
- Perform outlier detection using IQR or z-score methods
- Time-series analysis of review activity over time

## 👤 Author

RACHAKONDA SIVA NAGA BRAHMACHARI.

LinkedIn: linkedin.com/in/rsivachari | GitHub: https://github.com/chari532

## 📄 License

1776250134-P4-Airbnb Hotel Booking Analysis.xlsx.
