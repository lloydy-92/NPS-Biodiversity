# Biodiversity Analysis - National Park Service
This project explores species data from US national parks to identify which organisms are most at risk and how conservation priorities could be better informed through data-driven insights.

## Overview
The analysis focuses on understanding the relationships between conservation status, organism category, and species observatuons. It aims to help the National Park Service (NPS) prioritise conservation efforts more effectively.

## Objectives
1. **Identify at-risk species and their distribution across parks**
   - Determine which species are most under threat.
   - Assess how these species are distributed across different parks.
2. **Explore the relationship between observation frequency and conservation status**
   - Analyse whether species that are more endangered are observed less frequently.
   - User visualisations (boxplots, scatterplots) to investigate potential correlations.
3. **Test difference in conservation protection across organism categories**
   - Compare how protection levels differ between categories (e.g. mammals vs birds).
   - Use chi-square tests to evaluate statistical significance between protected and non-protected species groups.
  
## Key Insights (Summary)
> For full results, visualisations, and detailed discussion, open the Jupyter notebook *biodiversity.ipynb* in this repository.
- Merged and cleaned two biodiversity datasets usings ```pandas```.
- Filtered for species under active conservation (excluding '*No Intervention*').
- Used grouping and aggregation to count at-risk species per category.
- Visualised observations patterns using ```matplotlib``` and ```seaborn```. For example:
  - **Box plots**: Comparing observation counts by conservation status.
  - **Bar graphs**: Exploring correlations between species count and organism category, grouped by conservation status.
  - **Heatmap**: Comparing chi-square significance values between all combinations of organism category pairs.
- Generated contingency tables and applied chi-square tests to determine significant differences between organism categories.

## Tools & Libraries
| Purpose | Libraries Used |
|----------|----------------|
| Data manipulation | `pandas`, `numpy` |
| Statistical testing | `scipy.stats (chi2_contingency)`, `itertools` |
| Data visualization | `matplotlib`, `seaborn` |
| Environment | Jupyter Notebook (`%matplotlib inline`) |


## Installation
1. **Clone this repository**
   ```bash
   git clone https://github.com/lloydy-92/NPS-Biodiversity.git
   cd NPS-Biodiversity
2. **(Optional) Create and activate a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate       # On Windows use: venv\Scripts\activate
3. **Install dependencies**
   ```bash
   pip install pandas numpy scipy matplotlib seaborn jupyter
4. **Launch the notebook**
   ```bash
   jupyter notebook biodiversity.ipynb

## Project Structure
```bash
NPS-Biodiversity/
├── biodiversity.ipynb        # Main analysis notebook
├── data/
│   ├── species_info.csv      # Dataset containing species metadata
│   └── observations.csv      # Dataset containing park observation data
├── requirements.txt          # Python dependencies
├── analysis.md               # Written analysis file
└── README.md                 # Project documentation
```

## Contributing
Contributions, suggestions, and improvements are welcome and encouraged! If you would like the enhance any aspect of the project, such as analysis or visualisations:
1. Fork the repository
2. Create a feature branch
   ```bash
   git checkout -b feature/improve-analysis
3. Commit your changes
   ```bash
   git commit -m 'Add new visualisation'
4. Push to the branch
   ```bash
   git push origin feature/improve-analysis
5. Open a Pull Request

## Author
**Sam Lloyd**, sammy.lloyd@live.com, *github.com/lloydy-92*

## Acknowledgements
- National Park Service for making biodiversity data publicly available.
- Codecademy Data Science Path for providing structured guidance on this project.
- The open-source community for libraries like ```pandas```, ```matplotlib```, and ```seaborn```.
---------------------------------------------------------------------------------------------------
"*The greatest threat to our planet is the belief that someone else will save it.*" - Robert Swan
