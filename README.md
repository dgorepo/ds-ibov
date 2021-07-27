## Bovespa com Python

##### Projeto desenvolvido para analisar desempenho de carteira de investimentos na Bolsa de Valores de São Paulo (Bovespa) com Python

#### Bibliotecas

Para este projeto, foram utilizadas em especial as bibliotecas **yfinance** e **investpy**, para tanto será preciso inicialmente fazer a instalação delas.

```
!pip install yfinance
!pip install investpy
```

Posteriormente faremos os imports de todas as bibliotecas que será utilizadas

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
