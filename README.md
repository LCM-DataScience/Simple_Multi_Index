📊 Diferenças entre DataFrame com Índice Simples e MultiIndex no Pandas 📈

Ao trabalhar com dados estruturados no Pandas, uma das decisões fundamentais é escolher entre um DataFrame com índice simples ou um MultiIndex. Ambos têm suas vantagens e são adequados para diferentes cenários.

✨ Índice Simples:
Um DataFrame com índice simples é aquele em que uma única coluna é usada como índice para identificar cada linha. É o formato padrão e mais comum no Pandas. No exemplo abaixo, cada linha é identificada por uma data única.

python

# DataFrame com Índice Simples
df_spl_index = pd.DataFrame(data_spl_index)

🔍 Vantagens:

    Simplicidade: Facilidade de acesso aos dados.
    Facilidade de manipulação: Funciona bem para operações básicas de seleção e filtragem.

🌟 MultiIndex:
Um DataFrame com MultiIndex é aquele em que duas ou mais colunas são usadas como índice, criando uma hierarquia de índices. Isso é útil quando os dados têm múltiplas dimensões ou categorias, como no exemplo abaixo, onde temos datas, tickers de ações e tipos de ações.

python

# DataFrame com MultiIndex
index_levels = pd.MultiIndex.from_product([datas, tickers, tipos_act], names=['Date', 'Ticker', 'Tipo de ação'])
df_multi_index = pd.DataFrame(data_multi_index, index=index_levels)

🔍 Vantagens:

    Hierarquia de índices: Útil para dados multidimensionais ou categorizados.
    Facilidade de seleção: Permite selecionar dados de forma mais granular, especificando os níveis do índice.

🔄 Opções de Criação de Multi-Index:
Além disso, o Pandas oferece diversas opções para criar MultiIndex, como:

    MultiIndex.from_tuples: Para criar um MultiIndex a partir de uma lista de tuplas.
    MultiIndex.from_product: Como usamos no exemplo, para criar um MultiIndex a partir do produto cartesiano de várias listas.
    Definindo MultiIndex diretamente ao criar um DataFrame.

