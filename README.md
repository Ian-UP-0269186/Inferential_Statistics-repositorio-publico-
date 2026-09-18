# Inferential_Statistics-repositorio-publico-
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

np.random.seed(1)

bernoulli = np.random.binomial(n=1, p=0.6, size=1000)
print("Bernoulli (0s y 1s):")
print(bernoulli)

binomial_3 = np.random.binomial(n=3, p=0.6, size=1000)
print("\nBinomial n=3:")
print(binomial_3)

df = pd.DataFrame()

for i in range(1, 101):
    muestras_binomiales = np.random.binomial(n=1000, p=0.6, size=50)
    columna_nombre = f'muestra_{i}'
    df[columna_nombre] = muestras_binomiales

df_media = pd.DataFrame({'Muestra de las medias': df.mean()})

sns.displot(df_media['Muestra de las medias'], kde=True)
plt.title('Teorema Central del Límite (Variables Binomiales)')
plt.show()

df_exp = pd.DataFrame()

for i in range(1, 101):
    muestras_exp = np.random.exponential(scale=1.0, size=50)
    columna_nombre = f'muestra_{i}'
    df_exp[columna_nombre] = muestras_exp

df_exp_media = pd.DataFrame({'Muestra de las medias': df_exp.mean()})

sns.displot(df_exp_media['Muestra de las medias'], kde=True)
plt.title('Teorema Central del Límite (Variables Exponenciales)')
plt.show()
