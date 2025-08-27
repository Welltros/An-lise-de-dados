🎵 Análise de Músicas no Spotify (2023)
📌 Objetivo

Explorar os dados de músicas mais tocadas no Spotify em 2023 para identificar padrões de popularidade por gênero, artistas e países.

📂 Fonte de Dados

A base de dados analisada foi retirada do link abaixo.
https://www.kaggle.com/datasets/nelgiriyewithana/top-spotify-songs-2023

.

Contém informações de 50.000 músicas, com atributos como artista, gênero, popularidade, streams.

🔎 Etapas da Análise

Dicionário de dados:
<img width="3315" height="1907" alt="dicionario_spotify" src="https://github.com/user-attachments/assets/6f679d68-bc0f-44be-b422-8dbf6f48f6d2" />

Exploração inicial dos dados – inspeção das colunas e criação de dicionário de dados.

Correlação de características musicais.

Na minha análise dos dados do Spotify, constatei que as características musicais fornecidas na tabela não demonstram uma correlação significativa com o sucesso das músicas, como evidenciado claramente em meu gráfico comparativo. Em outras palavras, não encontrei um padrão discernível que possa ser diretamente associado ao número de streams de uma música específica.
– verificando se BPM, tonalidade, energia ou danceabilidade influenciam streams.

import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

Suponha que 'data' seja o seu DataFrame contendo os dados do Spotify


Renomear as colunas problemáticas


Selecionar as colunas de interesse

selected_columns = ['streams', 'danceability_%', 'valence_%', 'energy_%', 'acousticness_%', 'instrumentalness_%', 'liveness_%', 'speechiness_%']


data_selected = data[selected_columns]


Calcular a matriz de correlação

correlation_matrix = data_selected.corr()


Plotar o mapa de calor da matriz de correlação

plt.figure(figsize=(10, 8))

sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm', center=0)

plt.title('Mapa de Calor - Correlação entre Características e Streams', fontsize=16)
plt.show()



<img width="612" height="463" alt="correlação" src="https://github.com/user-attachments/assets/fabd5cd9-0a6b-4743-a722-3dafed810567" />


Mês de lançamento mais favorável – análise sazonal.

Sem dúvida, ao analisar o padrão de lançamentos musicais ao longo do tempo, identifiquei que os meses mais favoráveis para o lançamento de uma música bem-sucedida são setembro e janeiro, conforme claramente ilustrado em meu gráfico de análise.

<img width="612" height="463" alt="mês de lançamento" src="https://github.com/user-attachments/assets/4beada27-7571-48a0-9ffc-57f9946c4725" />


Gênero musical mais ouvido – categorização manual dos gêneros.
A partir da compilação das 20 músicas mais populares, notei a ausência de dados sobre os gêneros musicais na tabela original. Como resultado, atribuí manualmente um gênero a cada música, a fim de realizar uma análise exploratória. Observei que, dentro desta amostra, 14 das 20 músicas foram classificadas como 'Pop', enquanto 4 foram identificadas como 'Hip Hop', e as restantes 2 foram categorizadas como 'Outros'.

<img width="612" height="463" alt="Gênero Musical" src="https://github.com/user-attachments/assets/9e687f30-1366-4dd4-ab25-55a50a9b58e5" />


Comparação de desempenho entre artistas – solo vs colaborações.

📊 Resultados Principais

🎶 Não existe correlação significativa entre características musicais e sucesso (streams).

📅 Setembro e Janeiro foram identificados como os meses mais favoráveis para lançamentos.

🎤 O gênero Pop domina com 70% das músicas mais populares.

👥 Músicas com apenas 1 colaborador tiveram, em média, mais streams que colaborações múltiplas.

📷 Visualizações
