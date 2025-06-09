import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
df =pd.read_csv("C:\\Users\\WIN-10\\Downloads\\titanic3.csv")
survival_by_class = df.groupby('pclass')['survived'].mean().reset_index()
sns.set(style="whitegrid")
plt.figure(figsize=(8, 5))
sns.barplot(x='pclass', y='survived', data=survival_by_class, palette='Blues_d')
plt.title('Survival Rate by Passenger Class', fontsize=16)
plt.xlabel('Passenger Class')
plt.ylabel('Survival Rate')
plt.ylim(0, 1)
plt.xticks(ticks=[0, 1, 2], labels=['1st Class', '2nd Class', '3rd Class'])
plt.tight_layout()
plt.show()
