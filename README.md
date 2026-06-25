

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
* 
The raw file was loaded into Power Query, where I first removed columns that had no bearing on the analysis (such as energy, creators, url, last modified time,   sodium and a lot more) to keep the model focused. I then handled missing data by removing rows with null values in the key fields (product_name, sugars_100g, proteins_100g), since incomplete nutritional records would distort the protein versus sugar comparison. Finally, I addressed outliers: values are measured per 100g, so any figure above 100g is biologically impossible. I filtered these out of sugars_100g and proteins_100g to ensure the analysis ran on clean, credible data.
* Explain your "Candidate's Choice" addition.
* 
I added a "Who Owns the Blue Ocean?" competitor chart: a bar chart of brands within the target zone (protein at or above 15g, sugar under 5g), ranked by product count. Every prior step proved the gap exists; this answers the question the client cares about most before investing, which is can we win it? The chart reveals that no dedicated snack brand competes in this space. The few products that exist belong to supermarket private labels (Carrefour, Picard, Auchan), and the leader holds only five products. This reframes the finding from "here is an opportunity" to "here is an opportunity with no entrenched competitor," which is the difference between a market to fight into and open territory to claim.


