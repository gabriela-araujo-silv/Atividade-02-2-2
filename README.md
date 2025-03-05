# Atividade-02-2-2
Código 2/2 da atividade 2
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np

# Criando um DataFrame fictício com os dados da loja
dados = pd.DataFrame({
    "Dia": ["Segunda", "Terça", "Quarta", "Quinta", "Sexta", "Sábado", "Domingo"],
    "Vendas": [500, 700, 650, 800, 1200, 1500, 1300],
    "Clientes": [50, 65, 60, 75, 110, 150, 140],
    "Lucro": [100, 150, 130, 200, 350, 400, 370]
})

# Gráfico de Barras - Total de vendas por dia
plt.figure(figsize=(10, 5))
sns.barplot(x="Dia", y="Vendas", data=dados, palette="Blues")
plt.title("Total de Vendas por Dia da Semana")
plt.xlabel("Dia da Semana")
plt.ylabel("Total de Vendas")
plt.xticks(rotation=30)
plt.show()

# Gráfico de Dispersão - Relação entre Número de Clientes e Vendas
plt.figure(figsize=(8, 5))
sns.scatterplot(x="Clientes", y="Vendas", data=dados, color="b", s=100)
plt.title("Relação entre Clientes e Total de Vendas")
plt.xlabel("Número de Clientes")
plt.ylabel("Total de Vendas")
plt.grid(True)
plt.show()

# Heatmap - Correlação entre Vendas, Clientes e Lucro
plt.figure(figsize=(6, 5))
sns.heatmap(dados.drop(columns=["Dia"]).corr(), annot=True, cmap="coolwarm", linewidths=0.5)
plt.title("Correlação entre Vendas, Clientes e Lucro")
plt.show()
