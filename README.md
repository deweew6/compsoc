# Computational Social Science - Assignment 1

## **Overview**
This repository contains our solution to **Assignment 1** for the Computational Social Science course at DTU. The assignment consists of multiple exercises focusing on **web scraping, API data retrieval, data analysis, and network construction** using **BeautifulSoup, OpenAlex API, Pandas, and NetworkX**.

📅 **Due Date:** March 4th, 23:59  
📁 **Submission Format:** Jupyter Notebook (`.ipynb`) uploaded to DTU Learn  
📌 **Team Members:** (Add names and contributions here)

---

## **Assignment Structure**
The project is divided into four parts:

### **📌 Part 1: Web Scraping**
- **Goal:** Scrape the list of participants from the [IC2S2 2023 Conference Program](https://ic2s2-2023.org/program).
- **Method:** Used `BeautifulSoup` to extract names of keynote speakers, chairs, authors of talks, and posters.
- **Key Challenges:** Ensuring names are complete, accurate, and deduplicated.
- **Outcome:** A cleaned set of unique researcher names stored in a file.

### **📌 Part 2: Ready-Made vs Custom-Made Data**
- **Goal:** Compare the benefits and drawbacks of **custom-made data** (Centola's experiment) vs **ready-made data** (Nicolaides' study).
- **Analysis:** Discuss how these differences impact the interpretation of results.

### **📌 Part 3: Gathering Research Articles using the OpenAlex API**
- **Goal:** Use the [OpenAlex API](https://api.openalex.org/) to fetch research articles authored by IC2S2 2024 participants.
- **Data Filtering Criteria:**
  - Authors with **5-5000** total works.
  - Papers with **>10 citations**.
  - Works authored by **<10 individuals**.
  - Works related to **Computational Social Science**.
- **Methodology:**
  - Used API pagination (`per-page=200`).
  - Implemented batch requests (up to 25 authors per query).
  - Utilized `joblib` for multiprocessing.
- **Outcome:** Two datasets:
  - **IC2S2 Papers** (`papers.csv`): ID, year, citations, author IDs.
  - **IC2S2 Abstracts** (`abstracts.csv`): ID, title, abstract index.

### **📌 Part 4: Network of Computational Social Scientists**
- **Goal:** Construct a co-authorship network using **NetworkX**.
- **Steps:**
  1. Create a **weighted edgelist** from the paper dataset (co-authorship counts).
  2. Build a **graph** using `networkx.Graph()` and `add_weighted_edges_from()`.
  3. Add **node attributes**:
     - Author **display name** and **country** (from the authors dataset).
     - **Citation count** and **first publication year** (from papers dataset).
  4. Save the network as a **JSON file**.
- **Network Analysis:**
  - Number of nodes (authors) and edges (collaborations).
  - **Network density** and connectivity.
  - **Degree analysis**: average, median, mode, min, max.
  - **Top 5 most connected authors** and their contributions.

---

