# anotacaopandas
anotacao pandas
Os mais comuns A biblioteca Pandas possui muitas funções e métodos implementados que nos ajudam, e muito, em nosso dia-a-dia na análise exploratória de dados.

Nesta aula, vamos aprender a utilizar os mais comuns conforme estão listados abaixo:

rename : renomeia os 'rótulos' dos eixos (índices ou colunas)

apply : aplica uma determinada função ao longo de um eixo quando for chamado diretamente pelo DataFrame ou aplica uma função numa Series em questão

map : "mapeia" uma Series aplicando determinada função a cada elemento desta

agg : agrega uma ou mais operações à uma Series

min : retorna o valor mínimo de uma Series

max : retorna o valor máximo de uma Series

sum : retorna a soma dos valores de uma Series

mean : retorna a média dos valores de uma Series

count : conta as células não vazias de cada linha ou coluna

value_counts : retorna uma Series contendo a contagem de linhas exclusivas no DataFrame

sort_values : classifica / ordena os valores ao longo de qualquer eixo

insert : insire uma nova coluna no DataFrame no local especificado

drop : remova linhas ou colunas especificando diretamente seus nomes

Importação da biblioteca pandas
import pandas as pd

Configuração para que os números fiquem com 2 casas decimais
pd.options.display.float_format = '{:,.2f}'.format

df = pd.DataFrame( { 'Linguagem': ['Python', 'R', 'SQL', 'C', 'Java', 'Javascript', 'Elixir'], 'Popularidade': ['Alta', 'Baixa', 'Altíssima', 'Média', 'Altíssima', 'Altíssima', 'Baixa'], 'Versão': [3.10, 4.2, None, None, 11, 16, 1.12], 'Desenvolvedores': [7_000_000, 500_000, 20_000_000, 3_500_000, 16_000_000, 25_000_000, 200_000], 'Data de Lançamento': ['1991-02-20', '1993-08-03', '1986-01-01', '1972-01-01', '1995-05-23', '1995-12-04', '2012-01-01'] } )

df

dfs = pd.DataFrame( data=[], columns=['Lógica de Programação', 'Python', 'Data Science', 'HTML & CSS', 'JavaScript', 'React Native'], index=['Amanda', 'Camila', 'Cinthia', 'Gisele', 'Helen', 'Carol', 'Clara', 'Paula'] )

dfs

import numpy as np

dfs = dfs.apply(lambda nota: np.random.uniform
(low=5.0, high=10.0, size=8), axis='index') dfs

dfs['Média'] = dfs.mean(axis='columns') dfs

dfs['Situação'] =
dfs['Média'].map(lambda media: 'APROVADO' if media > 7 else 'REPROVADO') dfs

situacao = dfs['Média'].map(lambda media: 'APROVADO' if media > 7 else 'REPROVADO') dfs.insert(0, 'Status', situacao) dfs

#Base de dados 1° df

#Todas as colunas e colocar em caixa alta df.rename(str.upper, axis='columns', inplace=True) df

#Alterar o nome da coluna df.rename(columns={'LINGUAGEM': 'LINGUAGENS'}, inplace=True) df
