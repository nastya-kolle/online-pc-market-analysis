# Online PC Market Analysis — TSU Internship Project

**Team:** Полична, Пантелеева, Колле, Линникова
**Task:** Task 1 (Advanced level) — Analysis of the online market for personal computers

## Links

| Resource | Link |
|---|---|
| Notebook (Google Colab) | [Open notebook](https://colab.research.google.com/drive/1WUMsM6gxc9zcorIYhzdvq-j19EPU0H-F?usp=sharing) |
| Presentation (Google Slides) | [View presentation](https://docs.google.com/presentation/d/1pxzikud57n-gtE0vw10uaEWSP59dnso2/edit?usp=sharing&ouid=100280460103057024776&rtpof=true&sd=true) |
| Video presentation | [Watch video](https://drive.google.com/file/d/1pRONUiVEQlm_GDXtLVUJ-I4gPbF98AXW/view?usp=sharing) |

## Project Card

- **Business goal:** help the client enter the online market to attract more customers and cut store, delivery, and advertising costs by 10%.
- **Analysis goal:** identify the factors that influence the price and popularity of personal computers sold on online marketplaces.
- **Research object:** personal computers offered on online marketplaces.
- **Research subject:** price and popularity (measured by number of sales) of PCs, along with their components.
- **Data:** a dataset scraped from a popular online store, covering the "Computers and all-in-ones" category — product name, seller, seller rating, country of manufacture, GPU, CPU, HDD/SSD/RAM volume, dimensions, and weight.
- **Methods:** statistical analysis, correlation analysis, and (for the ML track) regression modeling to predict PC price.
- **Deliverable:** an analytical report with conclusions and recommendations for the client's business goals.

## Project Structure

The notebook follows the Advanced-level structure required for the internship:

1. **Data study** — import, loading, and initial overview of the dataset.
2. **Data preprocessing** — dropping irrelevant columns, removing duplicates, unpacking nested JSON-like fields, cleaning/typing numeric columns (`price`, `sales`, `feedbacks`, storage volumes, warranty, etc.), and handling missing values.
3. **Exploratory & statistical analysis** — univariate analysis of quantitative and categorical features, correlation analysis, hypothesis testing (normality, Mann–Whitney, Kruskal–Wallis), and visualization.
4. **Modeling** — linear, non-linear (log-log), polynomial, and decision tree regression models to predict PC price, compared by R², MAE, and MSE.
5. **Final conclusions & recommendations** for the client.

## Selected Visuals from the Notebook

**Dataset overview after cleaning:**

![Dataset overview](images/01_dataset_overview.png)

**Price distribution:**

![Price distribution](images/02_price_distribution.png)

**Operating system distribution:**

![OS distribution](images/03_os_distribution.png)

**Country of manufacture:**

![Country of manufacture](images/04_country_pie.png)

**Pairwise relationships between quantitative features:**

![Pairgrid](images/05_pairgrid.png)

**Correlation heatmap:**

![Correlation heatmap](images/06_correlation_heatmap.png)

**Price vs. GPU type:**

![Price vs GPU](images/07_price_vs_gpu_boxplot.png)

**Decision tree regression model:**

![Decision tree](images/08_decision_tree.png)

## Key Findings & Recommendations

1. Full duplicates, anomalous records, and rows with many missing values were found — an additional check of the source data and collection methods is recommended, along with automated deduplication/formatting at the collection stage.
2. Focus should be placed on the parameters that most affect price: number of CPU cores, SSD/RAM volume, GPU type, and OS.
3. Products from Russia significantly outnumber those from China in the dataset; the average price is higher for Russian products (~54,734) than Chinese ones (~43,164) — despite being cheaper, Chinese builds are less common in this dataset.
4. Intel-based products dominate over AMD and others; average price for Intel (~59,675) exceeds AMD (~45,378) — a potential opportunity for the client in budget AMD/China segments.
5. Feedback count is the only feature with a statistically significant relationship to sales — deeper analysis of reviews and additional behavioral data (traffic sources, repeat purchases, time on site) is recommended.
6. Among the tested models, the **Decision Tree Regressor** performed best (highest R² and lowest error on both train and test sets) and is recommended for further price-prediction work.

## Repository Contents

- `стажировка_тгу___Поличной_Пантелеева_Колле_Линникова.ipynb` — full analysis notebook (also available via the Colab link above).
- `images/` — key charts extracted from the notebook.
