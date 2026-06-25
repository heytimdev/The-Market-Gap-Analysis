# Project Brief: The "Sugar Trap" Market Gap Analysis

**Client:** Helix CPG Partners (Strategic Food & Beverage Consultancy)  
**Deliverable:** Interactive Dashboard, Code Notebook & Insight Presentation

---

## 1. Business Context
**Helix CPG Partners** advises major food manufacturers on new product development. Our newest client, a global snack manufacturer, wants to launch a "Healthy Snacking" line. They believe the market is oversaturated with sugary treats, but they lack the data to prove where the specific gaps are.

They have hired us to answer one question: **"Where is the 'Blue Ocean' in the snack aisle?"**

Specifically, they are looking for product categories that are currently under-served—areas where consumer demand for health (e.g., High Protein, High Fiber) is not being met by current product offerings (which are mostly High Sugar, High Fat).

## 2. The Data
You will use the **Open Food Facts** dataset, a free, open, and massive database of food products from around the world.

* **Source:** [Open Food Facts Data](https://world.openfoodfacts.org/data)
* **Format:** CSV (Comma Separated Values)
* **Warning:** The full dataset is massive (over 3GB). You are **not** expected to process the entire file. You should filter the data early or work with a manageable subset (e.g., the first 500,000 rows or specific categories).

## 3. Tooling Requirements
You have the flexibility to choose your development environment:

* **Option A (Recommended):** Use a cloud-hosted notebook like **Google Colab**, or **Deepnote**, etc.
* **Option B:** Use a local **Jupyter Notebook** or **VS Code**.
    * *Condition:* If you choose this, you must ensure your code is reproducible. Do not reference local file paths (e.g., `C:/Downloads/...`). Assume the dataset is in the same folder as your notebook.
* **Dashboarding:** The final output must be a **publicly accessible link** (e.g., Tableau Public, Google Looker Studio, Streamlit Cloud, or PowerBI Web).

---

## 4. User Stories & Acceptance Criteria

### Story 1: Data Ingestion & "The Clean Up"
**As a** Strategy Director,  
**I want** a clean dataset that removes products with erroneous nutritional information,  
**So that** my analysis is not skewed by bad data entry.

* **Acceptance Criteria:**
    * Handle missing values: Decide what to do with rows that have `null` or empty `sugars_100g`, `proteins_100g`, or `product_name`.
    * Handle outliers: Filter out biologically impossible values.
    * **Deliverable:** A cleaned Pandas DataFrame or SQL table export.

### Story 2: The Category Wrangler
**As a** Product Manager,  
**I want** to group products into readable high-level categories,  
**So that** I don't have to look at 10,000 unique, messy tags like `en:chocolate-chip-cookies-with-nuts`.

* **Acceptance Criteria:**
    * The `categories_tags` column is a comma-separated string (e.g., `en:snacks, en:sweet-snacks, en:biscuits`). You must parse this string.
    * Create a logic to assign a "Primary Category" to each product based on keywords.
    * Create at least 5 distinct high-level buckets.

### Story 3: The "Nutrient Matrix" Visualization
**As a** Marketing Lead,  
**I want** to see a Scatter Plot comparing Sugar (X-axis) vs. Protein (Y-axis) for different categories,  
**So that** I can visually spot where the products are clustered.

* **Acceptance Criteria:**
    * Create a dashboard (PowerBI, Tableau, Streamlit, or Python-based charts) displaying this relationship.
    * Allow the user to filter the chart by the "High Level Categories" you created in Story 2.
    * **Key Visual:** Identify the "Empty Quadrant" (e.g., High Protein + Low Sugar).

### Story 4: The Recommendation
**As a** Client,  
**I want** a clear text recommendation on what product we should build,  
**So that** I can take this to the R&D team.

* **Acceptance Criteria:**
    * On the dashboard, include a "Key Insight" box.
    * Complete this sentence: *"Based on the data, the biggest market opportunity is in [Category Name], specifically targeting products with [X]g of protein and less than [Y]g of sugar."*

---

## 5. Bonus User Story: The "Hidden Gem"
**As a** Health Conscious Consumer,  
**I want** to know which specific ingredients are driving the high protein content in the "good" products,  
**So that** I can replicate this in our new recipe.

* **Acceptance Criteria:**
    * Analyze the `ingredients_text` column for products in your "High Protein" cluster.
    * Extract and list the Top 3 most common protein sources (e.g., "Whey", "Peanuts", "Soy").

---

## 6. The "Candidate's Choice" Challenge
**As a** Creative Analyst,  
**I want** to add one additional feature or analysis to this project that I believe provides massive value,  
**So that** I can show off my business acumen.

* **Instructions:**
    * Add one more chart, filter, or metric that wasn't asked for.
    * Explain **why** you added it.
    * **There is no wrong answer, but you must justify your choice.**

---

## 7. Submission Guidelines
Please edit this `README.md` file in your forked repository to include the following three sections at the top:

### A. The Executive Summary
* A 3-5 sentence summary of your findings.

Analysis of 41,003 food products (filtered to roughly 1,960 snacks) confirms the snack aisle is saturated with sugary, low protein offerings, leaving a clear "blue ocean" in the space where protein is high and sugar is low. I recommend developing a snack targeting 15g of protein and under 5g of sugar per 100g, a position occupied by only 3.9% of current snacks yet proven viable by the products already there. Critically, this space has no entrenched competitor: the few products that exist are supermarket private labels (Carrefour, Picard, Auchan), not dedicated snack brands, making it open territory to claim rather than a market to fight into. To replicate the protein profile of the strongest products, R&D should build around dairy and milk protein and nuts (peanut and almond), the genuine protein drivers in this cluster. The opportunity is therefore not just a demand gap, but a defensible, formulatable, and brandable one.

### B. Project Links
* **Link to Notebook:** (e.g., Google Colab, etc.). *Ensure sharing permissions are set to "Anyone with the link can view".*
https://deepnote.com/workspace/HeyTim-5e116f84-c0ec-4e7a-9565-4173eb9028a6/project/Timothy-Kyebambos-Untitled-project-06cfe8dd-f244-4976-89fb-21bee9309f63/clean_data_1.csv?utm_source=share-modal&utm_medium=product-shared-content&utm_campaign=notebook&utm_content=06cfe8dd-f244-4976-89fb-21bee9309f63
* **Link to Dashboard:** (e.g., Tableau Public / Power BI Web, etc.).
https://app.powerbi.com/links/YsJvBxUlYM?ctid=33ba9ef5-10bb-4f84-a591-e0b30bbe75e7&pbi_source=linkShare
* **Link to Presentation:** A link to a short slide deck (PDF, PPT) AND (Optional) a 2-minute video walkthrough (YouTube) explaining your results.

https://docs.google.com/presentation/d/1TuRyViYn96Q2-taEUhldvG4pRBOY8pzL/edit?usp=drive_link&ouid=101349613438268220137&rtpof=true&sd=true
### C. Technical Explanation
* Briefly explain how you handled the "Data Cleaning".
The raw file was loaded into Power Query, where I first removed columns that had no bearing on the analysis (such as energy, creators, url, last modified time,   sodium and a lot more) to keep the model focused. I then handled missing data by removing rows with null values in the key fields (product_name, sugars_100g, proteins_100g), since incomplete nutritional records would distort the protein versus sugar comparison. Finally, I addressed outliers: values are measured per 100g, so any figure above 100g is biologically impossible. I filtered these out of sugars_100g and proteins_100g to ensure the analysis ran on clean, credible data.
* Explain your "Candidate's Choice" addition.
I added a "Who Owns the Blue Ocean?" competitor chart: a bar chart of brands within the target zone (protein at or above 15g, sugar under 5g), ranked by product count. Every prior step proved the gap exists; this answers the question the client cares about most before investing, which is can we win it? The chart reveals that no dedicated snack brand competes in this space. The few products that exist belong to supermarket private labels (Carrefour, Picard, Auchan), and the leader holds only five products. This reframes the finding from "here is an opportunity" to "here is an opportunity with no entrenched competitor," which is the difference between a market to fight into and open territory to claim.

**Important Note on Code Submission:**
* Upload your `.ipynb` notebook file to the repo.
* **Crucial:** Also upload an **HTML or PDF export** of your notebook so we can see your charts even if GitHub fails to render the notebook code.
* Once you are ready, please fill out the [Official Submission Form Here](https://forms.office.com/e/heitZ9PP7y) with your links

---

## 🛑 CRITICAL: Pre-Submission Checklist

**Before you submit your form, you MUST complete this checklist.**

> ⚠️ **WARNING:** If you miss any of these items, your submission will be flagged as "Incomplete" and you will **NOT** be invited to an interview. 
>
> **We do not accept "permission error" excuses. Test your links in Incognito Mode.**

### 1. Repository & Code Checks
- [ ] **My GitHub Repo is Public.** (Open the link in a Private/Incognito window to verify).
- [ ] **I have uploaded the `.ipynb` notebook file.**
- [ ] **I have ALSO uploaded an HTML or PDF export** of the notebook.
- [ ] **I have NOT uploaded the massive raw dataset.** (Use `.gitignore` or just don't commit the CSV).
- [ ] **My code uses Relative Paths.** 

### 2. Deliverable Checks
- [ ] **My Dashboard link is publicly accessible.** (No login required).
- [ ] **My Presentation link is publicly accessible.** (Permissions set to "Anyone with the link can view").
- [ ] **I have updated this `README.md` file** with my Executive Summary and technical notes.

### 3. Completeness
- [ ] I have completed **User Stories 1-4**.
- [ ] I have completed the **"Candidate's Choice"** challenge and explained it in the README.

**✅ Only when you have checked every box above, proceed to the submission form.**

---
