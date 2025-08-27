
# 📘 Learning Journal — SPY Stock Movement Classifier

> Use this to track *what you’re actually learning*.
> Fill out a new entry **every time you work on the project**, even if only for 15 minutes.

---

## ✏️ Entry Template

### 📅 **Date & Session Duration**
`YYYY-MM-DD — X minutes/hours`

### 🧠 **Main Learning Outcome for Today**
_What did I *intend* to understand or practice today?_

### ⚙️ **What I Did**
_Bullet list of activities, e.g., read docs, wrote code, debugged, researched_

### 🔍 **What I Learned / Realized**
_Even small realizations count — write them down. Be honest._

### ❓ **What Confused Me**
_Things that didn’t fully click yet or I felt shaky on_

### 📌 **Next Questions to Explore**
_What should I dig into or clarify next session?_

---

## 📈 Weekly Review (fill at end of each week)

### ✅ What I actually learned this week (in my own words):

### 🤯 Things that surprised me / I struggled with:

### 🔄 Adjustments for next week (process or learning approach):

---
### 📅 **Date & Session Duration**
`YYYY-MM-DD — X minutes/hours`

### 🧠 **Main Learning Outcome for Today**
Understand how to build and visualize past-looking return features (1-day, 5-day, 10-day, momentum) and interpret them in the context of predicting next-day SPY moves.

### ⚙️ **What I Did**
- Implemented columns for 5-day, 10-day and momentum
- Made sure to correctly include the Date column in the processed data
- Made line plot and histogram of 1 day returns
- Plotted and visualized multi-day returns on one plot
- Made a box plot of returns split by y (growth), which indicated tomorrow's up vs down

### 🔍 **What I Learned / Realized**
- How to better visualize data using mat plot lib
- The differences in the quality of data between 1 day, 5 day, and 10 day returns
- Boxplots hinted at weak signals, which are tiny differences between up vs down days. This matches the idea that markets are efficient.
- return_1d (future return) is the label, while ret_1d, ret_5d, etc. are features. Keeping that distinction is crucial.

### ❓ **What Confused Me**
- Handling indices in raw csv's can be tricky if not formatted properly beforehand
- Still a little fuzzy on when to use .pct_change() vs .shift() for returns.
- Interpreting boxplots: overlap was large, so I wasn’t sure how much signal really exists.

### 📌 **Next Questions to Explore**
- How strong are moving average signals compared to returns (Session 4)?
- Do price-to-SMA ratios show clearer mean-reversion tendencies?
- Should I standardize/scale features now or wait until model training?
- How to decide which features are redundant (e.g., ret_5d vs mom_5d).

---
### 📅 **Date & Session Duration**
2025-08-24 — 45 minutes  

### 🧠 **Main Learning Outcome for Today**  
Build a labeled SPY dataset for next-day movement and save it to `data/processed/spy_labeled.csv`.  

### ⚙️ **What I Did**  
- Created a column that shows the returns for the next day
- Classify whether the next day closer is higher or lower with binary output
- Organized rows by ascending order

### 🔍 **What I Learned / Realized**  
- I learned how to manipulate the pandas dataframe object using functions like shift, dropna, and how to perform comparisons

### ❓ **What Confused Me**  
- I had some difficulty with syntax as the dataframe doesn't work like a standard object
- I had to understand what the values represent with respect to the data

### 📌 **Next Questions to Explore**  
- How does this data help me classify and predict stocks based on the historical data?

---

### 📅 **Date & Session Duration**
`2025-08-23 — 45 minutes`

### 🧠 **Main Learning Outcome for Today**
Get a local, reproducible dataset of SPY daily prices into the project.  

### ⚙️ **What I Did**
- Set up the first notebook: `notebooks/01_get_data.ipynb`  
- Used `yfinance` to download SPY daily OHLCV data (2010–2025)  
- Debugged warnings about adjusted vs raw prices (`auto_adjust`)  
- Saved the dataset to `data/raw/spy.csv`  
- Reloaded the CSV and handled the header/index formatting quirks  

### 🔍 **What I Learned / Realized**
- Yahoo Finance data comes with multi-level headers when saved directly, which can cause confusion on reload.  
- Better practice is to reset the index before saving so the CSV is “flat.”  
- Adjusted vs raw prices matter — adjusted is usually better for modeling returns.  
- First milestone: having a raw dataset in `data/` feels like progress.  


### ❓ **What Confused Me**
- The warnings about `auto_adjust` defaults.  
- Why the CSV came back with multi-index headers and how to flatten them.  
- Difference between keeping `Date` as index vs column in saved CSVs.  


### 📌 **Next Questions to Explore**
- How to consistently label “next-day up/down” without introducing leakage.  
- Should I use adjusted or raw close prices for the target?  
- What happens to the dataset if I extend beyond SPY (e.g., add QQQ, DIA)? 
