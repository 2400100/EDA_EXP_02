**Netflix Shows & Movies**

**Aim**

To analyze Netflix dataset and compare movies vs TV shows, top producing countries, and release year trends.

**Procedure / Algorithm**

  1)Load dataset (netflix_titles.csv).
  2)Count movies vs TV shows.
  3)Group by country → top contributors.
  4)Create pivot table (release year vs type).
  5)Visualize with bar & line charts.

**Program**
```
from google.colab import files
uploaded = files.upload()

import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("netflix_titles.csv")
print(df.head())

# Count number of Movies and TV Shows
type_count = df['type'].value_counts()
print(type_count)

# Group by 'country' and count titles
country_counts = df['country'].value_counts().head(10)
print(country_counts)

# Pivot table to compare Movies and TV Shows by release year
pivot_table = df.pivot_table(index='release_year', columns='type', values='show_id', aggfunc='count').fillna(0)
print(pivot_table.tail())

# Bar chart for release year vs type
pivot_table.plot(kind='bar', figsize=(10,5))
plt.title('Movies and TV Shows by Release Year')
plt.xlabel('Release Year')
plt.ylabel('Count')
plt.show()

# Line chart for trend visualization
pivot_table.plot(kind='line', figsize=(10,5), marker='o')
plt.title('Trend of Movies vs TV Shows Over Years')
plt.xlabel('Release Year')
plt.ylabel('Count')
plt.grid(True)
plt.show()
```

**Ouptut**

<img width="843" height="816" alt="Screenshot 2025-10-08 091159" src="https://github.com/user-attachments/assets/ca5d998d-c657-46b9-adf0-43c4635cfdc8" />


<img width="378" height="108" alt="Screenshot 2025-10-08 091230" src="https://github.com/user-attachments/assets/e983cf33-12cd-4fa6-bc3e-9dd58f101abe" />


<img width="309" height="274" alt="Screenshot 2025-10-08 091327" src="https://github.com/user-attachments/assets/dd05b534-1645-4916-b1ae-0646999a6638" />


<img width="384" height="171" alt="Screenshot 2025-10-08 091351" src="https://github.com/user-attachments/assets/ac52ea80-9096-4026-b789-6fbf6c63f770" />


<img width="852" height="492" alt="download" src="https://github.com/user-attachments/assets/031680d1-46b8-42b5-b22e-77979fbf9ec8" />


<img width="850" height="470" alt="download" src="https://github.com/user-attachments/assets/87c3155f-ecd7-4c8e-950b-191a7c833ca2" />

**Result:**

Helps Netflix in content planning & investments.
