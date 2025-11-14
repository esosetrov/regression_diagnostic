# Regression Diagnostics

Comprehensive implementation of regression diagnostic tests using statsmodels for model validation and assumption checking in real-world data analysis.

## Overview
Regression diagnostics is essential for validating model assumptions and ensuring reliable statistical inference. This project demonstrates practical application of diagnostic tests including:

- **Normality testing** - Jarque-Bera, Omnibus, Shapiro-Wilk tests
- **Heteroskedasticity detection** - Breusch-Pagan, Goldfeld-Quandt, White tests
- **Multicollinearity assessment** - VIF, condition number analysis
- **Influence analysis** - Cook's distance, DFBETAS, leverage plots
- **Model specification** - Harvey-Collier, Rainbow tests for linearity

## Features
- Complete regression diagnostics workflow
- Multiple model comparison and evaluation
- Robust standard errors implementation
- Automated diagnostic summary with PASS/FAIL status
- Comprehensive visualization suite
- Real-world dataset application (Guerry historical data)

## Installation
```bash
# Clone repository
git clone https://github.com/yourusername/regression-diagnostics.git
cd regression-diagnostics

# Install dependencies
pip install numpy pandas matplotlib seaborn statsmodels scipy
```

## Usage
```python
import pandas as pd
import statsmodels.formula.api as smf
import statsmodels.stats.api as sms

# Load data and fit model
url = "https://raw.githubusercontent.com/vincentarelbundock/Rdatasets/master/csv/HistData/Guerry.csv"
dat = pd.read_csv(url)
model = smf.ols("Lottery ~ Literacy + np.log(Pop1831)", data=dat).fit()

# Run comprehensive diagnostics
from regression_diagnostics import comprehensive_diagnostics
results = comprehensive_diagnostics(model, dat)
```

## Key Results
The analysis reveals:
- **Model performance**: R² = 0.349, RMSE = 20.04
- **Normality**: All tests confirm normal residuals (p > 0.05)
- **Homoscedasticity**: Constant variance assumption satisfied
- **Linearity**: No significant specification errors detected
- **Influence**: 4 influential observations identified

## Diagnostic Tests Implemented
- **Residual Analysis**: Q-Q plots, residual distributions, scale-location plots
- **Influence Metrics**: Cook's distance, DFBETAS, leverage statistics
- **Multicollinearity**: Variance Inflation Factors (VIF), condition numbers
- **Robustness Checks**: Huber-White standard errors comparison
- **Model Comparison**: Multiple specification testing

## Applications
- Academic research and statistical education
- Model validation in data science projects
- Quality assurance for regression analyses
- Teaching statistical methods and diagnostics
- Pre-deployment model checking

## Project Structure
regression-diagnostics/
├── regression-diagnostic-tests-in-a-real-life-context.ipynb  # Main analysis notebook
├── requirements.txt                                          # Python dependencies
├── README.md                                                 # Project documentation
├── LICENSE                                                   # MIT License
└── .gitignore                                               # Version control settings

## Dependencies
- Python 3.7+
- matplotlib
- numpy
- pandas
- scipy
- seaborn
- statsmodels

## Contributing
Contributions welcome! Please feel free to submit issues and pull requests.

## License
MIT License - see LICENSE file for details.

## References
1. StatsModels Documentation: https://www.statsmodels.org
2. Guerry, A.-M. (1833). *Essay on the Moral Statistics of France*
3. Cleveland, W. S. (1979). *Robust Locally Weighted Regression*
4. Fox, J. (2016). *Applied Regression Analysis and Generalized Linear Models*
