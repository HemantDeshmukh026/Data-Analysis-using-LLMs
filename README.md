# PandasAI

**PandasAI is a python library seamlessly blending pandas and generative AI for conversational data analysis.**

Explore the documentation: [PandasAI Documentation](https://docs.pandas-ai.com/en/latest/)

## Overview

PandasAI is an open-source project designed to enhance your data analysis and manipulation workflow. Leveraging the power of generative AI, it enables natural language interactions with pandas, allowing users to pose questions and perform a wide range of data tasks effortlessly.

## Key Features

- **Ease of Use:** Pose natural language queries for data analysis tasks.
- **Powerful Functionality:** Perform data exploration, analysis, visualization, cleaning, imputation, and feature engineering.
- **Integration:** Seamlessly integrates with pandas and popular data analysis libraries.

## How It Works

PandasAI employs a generative AI model to convert natural language queries into executable Python code. Simply ask questions, and PandasAI will handle code generation and execution, providing insightful results.

## Getting Started

Visit the [documentation](https://docs.pandas-ai.com/en/latest/) for installation instructions, usage examples, and to unlock the potential of conversational data analysis with PandasAI.

## Who Should Use PandasAI?

- Data analysts seeking an intuitive and efficient workflow.
- Beginners in pandas looking to enhance their data analysis capabilities.

## Practice with PandasAI
I generated a random dataset with 1000 records and applied PandasAI for conversational data analysis. The example above demonstrates how to set up PandasAI, create a SmartDataframe, and ask questions about the data. Feel free to explore and experiment with your own datasets!

# Example Usage with PandasAI

## Generating Sample Data

```python
import numpy as np
import pandas as pd
from random import choices 

np.random.seed(10)

num_of_records = 1000
num_of_outlets = 10
num_of_products = 20

# Two Quarters (Jan - March, April - June)
dates = pd.date_range(start='2023-01-01', end='2023-06-30')
dates = choices(dates, k=num_of_records)

units_sold = np.random.randint(1, 200, num_of_records)
price_per_unit = np.random.uniform(10, 500, num_of_records)
total_sales = units_sold * price_per_unit

outlets = choices(range(1, num_of_outlets + 1), k=num_of_records)
products = choices(range(1, num_of_products + 1), k=num_of_records)

df = pd.DataFrame({
    'Date': dates,
    'Outlet': outlets,
    'Product': products,
    'Unit_Sold': units_sold,
    'Price_per_unit': price_per_unit,
    'Total_sales': total_sales
})
```
## Using PandasAI for Conversational Data Analysis
```
# Install PandasAI
!pip install pandasai

# Import PandasAI modules
from pandasai import SmartDataframe
from pandasai.llm.openai import OpenAI

# Set up OpenAI API key
llm = OpenAI(OPENAI_API_KEY)

# Create a SmartDataframe with PandasAI
sdf = SmartDataframe(df, config={"llm": llm})

# Use PandasAI to ask questions about the data
sdf.chat('Return the product with the highest sales')
```
