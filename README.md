# Graficos.py
Exemplos de criação de gráficos em Python


import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd

df = pd.read_csv('ecommerce_estatistica.csv')

print(df.head())

# Gráfico de Histograma
plt.figure(figsize=(10, 6))
plt.hist(df['idade'], bins=20, color='blue', edgecolor='black')
plt.title('Distribuição da idade dos Clientes')
plt.xlabel('Idade')
plt.ylabel('Frequência')
plt.show()

# Gráfico de Dispersão
plt.figure(figsize=(10, 6))
plt.scatter(df['idade'], df['gasto_medio'], alpha=0.5, color='purple')
plt.title('Relação entre Idade e Gasto Médio')
plt.xlabel('Idade')
plt.ylabel('Gasto Médio')
plt.show()

# Gráfico de Mapa de Calor
plt.figure(figsize=(10, 8))
correlation_matrix = df.corr()
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm', linewidths=0.5)
plt.title('Mapa de Calor das Correlações')
plt.show()

# Gráfico de Barra
plt.figure(figsize=(10, 6))
df['categoria_produto'].value_counts().plot(kind='bar', color='teal', edgecolor='black')
plt.title('Número de Produtos por Categoria')
plt.xlabel('Categoria do Produto')
plt.ylabel('Quantidade')
plt.show()

# Gráfico de Pizza
plt.figure(figsize=(8, 8))
df['categoria_produto'].value_counts().plot(kind='pie', autopct='%1.1f%%', startangle=140, colors=['blue', 'green', 'salmon', 'orange'])
plt.title('Distribuição de Produtos por Categoria')
plt.ylabel('')
plt.show()

# Gráfico de Densidade
plt.figure(figsize=(10, 6))
sns.kdeplot(df['gasto_medio'], shade=True, color='blue')
plt.title('Densidade do Gasto Médio')
plt.xlabel('Gasto Médio')
plt.ylabel('Densidade')
plt.show()

# Gráfico de Regressão
plt.figure(figzise=(10, 6))
sns.regplot(x='idade', y='gasto_medio', data=df, scatter_kws={'alpha':0.5}, line_kws={'color': 'red'})
plt.title('Relação entre Idade e Gasto Médio com linha de Regressão')
plt.xlabel('Idade')
plt.ylabel('Gasto Médio')
plt.show()
