## Bovespa com Python

##### Projeto desenvolvido para analisar desempenho de carteira de investimentos na Bolsa de Valores de São Paulo (Bovespa) com Python

#### Bibliotecas

Para este projeto, foram utilizadas em especial as bibliotecas **yfinance** e **investpy**, para tanto será preciso inicialmente fazer a instalação delas.

```
!pip install yfinance
!pip install investpy
```

Posteriormente faremos os imports de todas as bibliotecas que serão utilizadas

```
import yfinance as yf
import investpy as ip
import pandas as pd
import numpy as np
import pandas_datareader as web
import seaborn as sns
import matplotlib.pyplot as plt
import warnings
from datetime import date, timedelta
```

Montando a lista de ativos

```
lista_ativos = ['WEGE3.SA', 'LREN3.SA',
                'MGLU3.SA', 'VALE3.SA',
                'RENT3.SA', 'PRIO3.SA']
```

Utilizando loop para extrair os valores de preços de fechamento de todos os papéis, o período definido foi dos últimos 2 anos.

```
df = pd.DataFrame()

end_date = date.today() # Formato 'aaa-mm-dd'
start_date = end_date - timedelta(days=2*365) # Formato 'aaa-mm-dd'


for acoes in lista_ativos:
    df[acoes] = yf.download(acoes, start=start_date, end=end_date)['Adj Close']
```

Limpando o dataframe de valores nulos e plotando o primeiro gráfico
```
df = df.dropna()
df.plot(figsize=(20, 6), grid=True, colormap="Set1")
```

![Captura de tela de 2021-07-27 10-18-07](https://user-images.githubusercontent.com/1071578/127160618-ff905507-e0c6-428c-ab4b-e1b4d0e45f53.png)


Utilizando a biblioteca seaborn para detalhar o gráfico de cada ativo

```
sns.set()
df.plot(subplots=True, figsize=(20,8))
plt.show()
```

![Captura de tela de 2021-07-27 10-19-04](https://user-images.githubusercontent.com/1071578/127160665-c5d6d247-e1c6-45ce-8268-2ee5777a8d03.png)
