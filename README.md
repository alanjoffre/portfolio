# Portfólio: Alan Joffre
Desenvolvedor Python - Cientista de Dados
# Projeto: Ciência de Dados - Black Friday
- Importando os módulos.
- Carregando os dados.
- Visualização dos dados.
- Verificando os tipo de dados.
- Resumo Estátistico.
- Variáveis númericas.
- Variáveis categóricas.
- Exploratory Data Analysis (EDA).
- Será que temos mais usuários do sexo masculino ou do sexo feminino?
- Qual o valor médio da compra para cada sexo?
- Qual é a idade predominante entre seus usuários?
- Qual o valor médio de compra para cada faixa etária?
- Vamos observar o número de consumidores por ocupação.
- De qual categoria é a cidade com o maior número de usuários?
- Qual a média de compra por cidade?
- A quantos anos o usuário mora na cidade atual?
- Qual a média do valor da compra de acordo com o número de anos que o usuário mora na cidade atual?
- Agora queremos saber qual o estado civil dos consumidores.
- Qual o valor médio de compra para cada estado civil?
- Vamos analisar algumas informações sobre a categoria dos produtos.
- Agora vamos verificar graficamente as informações citadas acima.
- Distribuição dos valores para cada categoria.

- ***************************************************************************************************
- Considerações:
- A maioria dos usuários é do sexo masculino
- Com idade entre 26 a 30 anos
- Não são casados
- Residem na cidade de categoria B
- Moram 1 ano na cidade atual
- E compraram mais produtos da categoria 1.
- ***************************************************************************************************

# Projeto: Ciência de Dados - Google Play
- Objetivo: Os dados dos aplicativos da Play Store têm um enorme potencial para levar as empresas que desenvolvem essas aplicações ao sucesso. O objetivo deste projeto é analisar esses dados com o intuito de ajudar os desenvolvedores a entender que tipo de aplicativo provavelmente atrairá mais usuários.

- Importando os pacotes necessários.
- Lendo o arquivo.
- Primeiras 5 linhas.
- Tamanho do Dataframe.
- Identificando o tipo de cada variável.
- Corrigindo o nome das colunas.
- Visualizando os dados novamente.
- Verificando valores duplicados.
- Identificando registro.
- Removendo o registro.
- Convertendo o tipo dos dados.
- Removendo os aplicativos duplicados.
- Reorganizando os indices.
- Valores únicos.
- Limpeza da coluna.
- Preenchendo os registros nulos.
- Limpando os dados e convertendo os valores.
- Valores únicos da coluna "Price".
- Removendo o símbolo monetário e transformando o tipo de dado.
- Valores únicos da coluna.
- Identificando os aplicativos.
- Removendo as linhas.
- Os dados estão no formato Categoria; Subcategoria. Vamos dividi-los e extrair apenas a categoria principal.
- Extraindo a categoria principal.
- Temos "Music & Audio" e "Music", que na verdade são a mesma coisa, vamos corrigir isso.
- Corrigindo o nome da categoria.
- Convertendo a data de string para date.
- Criando a nova coluna.
- Extraindo a versão miníma.
- Dropando as colunas irrelevantes.
- Visualizando os valores faltantes.
- O que é classificar um app?
- Como essa classificação é feita?
- Removendo os valores faltantes.
- Verificando se os valores foram preenchidos corretamente.
- Análise Exploratória dos Dados (EDA)
- Quais são as categorias que tem o maior número de aplicativos?
- Wordcloud com a representação das categorias.
- Os aplicativos são direcionados para quais faixa etárias?
- Qual o maior volume de downloads?
- Quais são os 15 aplicativos com o maior número de downloads?
- Quais são os 15 aplicativos com as maiores avaliações?
- A loja tem mais aplicativos pagos ou gratuitos?
- Entre os aplicativos pagos quais são os preços mais frequentes?
- Quais são as classificações mais frequentes?

- ***************************************************************************************************
- Considerações:
- As maiores avaliações são para os aplicativos de rede social, o campeão é o Facebook.
- A maioria dos aplicativos da Play Store são gratuitos.
- Há um número elevado de aplicativos que custam 0.99 e 3.02 dólares.
- A distribuição da classificação está entre 4.0 e 4.7.
- Depois de toda essa análise podemos concluir que os aplicativos voltados para rede social e games são os que mais atraem os usuários, então um desenvolvedor pode usar essa análise como base para criar seu próximo aplicativo.

- ***************************************************************************************************
# Projeto: Ciência de Dados - Censo
- Importando os módulos.
- Carregando e visualizando os módulos.
- Descrição das principais Features.
- Informações sobre as colunas.
- Variáveis numéricas.
- Variáveis categóricas.
- Análise Exporatória.
- Distribuição das classes (variável income).
- Distribuição das classes por Nível de Escolaridade.
- Verificando a menor e a maior jornada de trabalho.
- Agrupar as horas trabalhadas em 3 categorias.
- Distribuição das classes por Horas trabalhadas.
- Distribuição das classes de acordo com a ocupação.
- Relação das colunas: age,sex e race com a coluna income.
- Verificando a idade mínima e máxima do dataset.
- Agrupar as idades em 3 categorias.
- Análise de Dados.
- Preenchendo os valores nulos da coluna 'workclass'.
- Preenchendo os valores nulos da coluna 'occupation'.
- Preenchendo os valores nulos da coluna 'native-country'.
- Verificando se ainda existem valores nulos no Dataset.
- Criando uma nova coluna com a renda final.
- Removendo as features irrelevantes.
- Trasnformando as variáveis categóricas em numéricas.
- Matriz de correlação (análise simultânea da associação entre variáveis).
- Verificando as features mais importantes para o modelo.
- Separando a classe dos Dados.
- Selecionando as features de maior importância.
- Treinando os modelos utilizando apenas as features selecionadas.
- Avaliação dos modelos de Machine Learning.
- Tunning dos modelos criados com Random Forest e DecisionTree.
- Random Forest aprensentou a menor taxa de erro após a padronização dos dados.
- Random Forest (possibilidade de otimização).
- Definindo a escala.
- Possíveis valores de estimators.
- Possíveis valores para o critério de divisão.
- Definindo um dicionário que recebe as listas de parâmetros e valores.
- Criando o modelo.
- Definindo K.
- Testando diferentes combinações com os parâmetros.
- Vamos agora ajustar os parâmeros do DecisionTree.
- Definindo a escala.
- Definindo a profundidade máxima da árvore.
- Possíveis valores para o critério de divisão.
- Definindo um dicionário que recebe as listas de parâmetros e valores.
- Criando o modelo.
- Definindo K.
- Testando diferentes combinações com os valores de K.
- Finalizando o Modelo.
- Preparando a versão final do modelo.
- Fazendo a persistência do modelo treinado para o disco.

# Projeto: Python - Flask
- Aplicação Web ToDo
- Desenvolvido em: HTML | Bootstrap5 | Python | Flask | SQLAlchemy | SQLite | CRUD |
- Procedimento: instalação e configuração
<p align="center">
  <img alt="mulheres-vozes-escuta" src="./assets/toDo.png" width="100%">
</p>
<br>

# Projeto: Python - Django



