# Analysed India's largest companies according to there revenue. 
### Project Overview 

This data analysis project aims analyzing data of India’s largest companies based on their revenue. By analyzing various aspects of the production , sector , geographical area. This project focuses on extracting, processing. Using Python libraries such as Pandas, Matplotlib, and Beautiful Soup, we scrape data from Wikipedia, clean and process it.

### Data Sources

-Wikipedia [Link](https://en.wikipedia.org/wiki/List_of_largest_companies_in_India)

### Tools
- Python(Pandas,Matplotlib,BeautifulSoup) [Download](https://www.python.org/downloads/)
- Anaconda [Download](https://www.anaconda.com/download)
- Jupitar Notebook [Download](https://jupyter.org/install)
- Excel [Download](https://www.microsoft.com/en-us/microsoft-365/excel)

### Data Extraction/Preparation 
The initial extraction phase we performed following tasks :
1. Inspect wikipedia page on which there is data of India's largest companies.
2. Found the table tag by navigating it.
3. Import Beautifulsoup , Pandas , Matplotlib in jupitar notebook.
4. Extract data by using these libraries .
5. Converted this data to CSV format.

###  Exploratory Data Analysis
1. From this Analysis we analysed that the Reliance Industries has the highest number of revenue as 109.43(billion $)
2. From this we analysed that Banking sectors has the most number no of banks as compared to other sectors.
3. We also analysed that Mumbai has the most number of companies as compared all other cites which we represented as pie chart.

### Data Analysis
```Python
import pandas as pd
from bs4 import BeautifulSoup

url='https://en.wikipedia.org/wiki/List_of_largest_companies_in_India'

page = requests.get(url)

soup= BeautifulSoup(page.text,'html')

soup.find_all('table',class_='wikitable sortable')[0]

world_list=table.find_all('th')

df=pd.DataFrame(columns=world_class_title)

for row in column_data[1:]:
    row_data=row.find_all('td')
    row_class_data=[data.text.strip() for data in row_data]
    length=len(df)
    df.loc[length]=row_class_data


df['Revenue(billions US$)']=df['Revenue(billions US$)'].astype(float)

df.groupby("Name")["Revenue(billions US$)"].mean().sort_values(ascending=False)
```
### Results
This section summarizes the findings from the exploratory data analysis (EDA) of India’s largest companies by revenue. The analysis involves descriptive statistics and visualizations to understand revenue distribution, identify top companies, and analyze growth and decline trends.

Key Findings

1. Distribution of Revenue

The distribution of revenue among India’s largest companies shows a significant range. Most companies have revenues clustered in the lower range, with a few companies exhibiting exceptionally high revenues.

2. Top 10 Companies by Revenue

The analysis highlights the top 10 companies by revenue, showcasing the leading players in India’s corporate sector.

-The EDA provides valuable insights into the revenue dynamics of India’s largest companies. Key takeaways include:

1. Revenue Distribution: A small number of companies dominate the revenue landscape, with significant disparities between the top companies and the rest.

2. Top Performers: Major conglomerates and industry leaders consistently rank among the top in terms of revenue.

3. Revenue vs. Profit: While higher revenues generally lead to higher profits, some companies struggle with lower profit margins despite high revenues.

4. Growth Trends: Identifying companies with consistent growth or decline helps assess their long-term viability and market position.
