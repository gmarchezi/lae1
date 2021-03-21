# DISCIPLINA: Laboratório de Extensão 1 - lae1

# TRABALHO 01:  Título do Trabalho
Trabalho desenvolvido durante a disciplina:

# Sumário

### 1. Componentes <br>
Integrantes do grupo<br>
Gabriel Marchezi:gabrielmarchezi@gmail.com<br>
Manoel Rodrigues:manoel.rl@gmail.com<br>
Matheus Oliveira:matheussouzapoliveira@gmai.com<br>

### 2.Apresentação dos Datasets (Clássico + Em estudo)<br>
<br>Visão geral das bases de dados<br>

> Após obter a(s) base(s) de dados Responda as seguintes perguntas sobre o conjunto de dados:
* seus dados são sobre o que? 
* o que você deseja com este conjunto de dados?
* quais são os tipos de atributos existentes e qual é o atributo alvo? 
* quais são os problemas existentes?
* qualidade e clareza: garantir que a semântica dos atributos seja clara (nomes coerentes com os dados, se necessário renomear atributos).

>#### 2.1 Visão geral da base de dados clássica:<br>
>A base de dados clássica é o Titanic, essa base de dados possui dados sobre os tripulantes do navio Titanic, de acordo com os atributos existentes, o objetivo é saber se um tripulante sobreviveu ou não sobreviveu ao acidente.
![Dicionário - Base de Dados Titanic](https://github.com/gmarchezi/lae1/blob/main/Imagens/dicionario_titanic.PNG?raw=true)
O atributo alvo do Titanic é o "Survived", 0 = Não Sobreviveu e 1 = Sobreviveu. Os problemas encontrados na base de dados foram a coluna "Cabin", que possuia a maioria de suas linhas nulas, a coluna "Age", que possuia 177 linhas nulas.
>#### 2.2 Visão geral da base de dados em estudo:<br>
>O dataset em estudo contém informações sobre uma pesquisa feita com algumas pessoas, essas pessoas responderam algumas perguntas específicas com o objetivo de predizer se esta pessoa possui ou nao depressão. O dataset possui respostas de perguntas sobre depressão (prefixo "D"), doenças crônicas (prefixo "CC") e perguntas gerais para auxilio (prefixo "SC"). Considerando os cinquenta melhores atributos, selecionados utilizando o método chi2, tinhamos 35 colunas numéricas e 15 categóricas. As dificuldades encontradas no dataset além do grande número de colunas foram o alto volume de nulos, principalmente nas colunas com prefixo "D" que são direcionadas à depressão.

### 3.Pré-processamento dos Datasets <br>

Realize o Pré-processamento e Tratamento de Dados em sua base/dataset.

>#### 3.1 Pré-processamento e tratamento na base de dados clássica:<br>
>1- Análise de nulos<br> Através do método "Heatmap" e da função "isnull", verificamos que a coluna "Cabin" possuia nulos na maioria de suas linhas, então resolvemos tirar essa coluna, a coluna "Age" também possuia nulos, mas não era a maioria das linhas, então resolvemos retirar as linhas da base de dados onde o atributo "Age" estava nulo.<br>
>![Heatmap Titanic](https://github.com/gmarchezi/lae1/blob/main/Imagens/Titanic_Analise_Nulos.png?raw=true)<br>
>2- Remoção de atributos<br>Retiramos as colunas que a princípio não afetaria no resultado final, como "PassengerId", "Name", "Ticket" e "Embarked".<br>
>3- Label Encoding<br>Utilizamos o método Label Encoding no atributo "Sex", pois se trata de uma variável binária e queriamos trabalhar apenas com números, 0 = Feminino e 1 = Masculino.<br>
>![Label Encoding Titanic](https://github.com/gmarchezi/lae1/blob/main/Imagens/Titanic_Label_Encoding.png?raw=true)<br>
>4- Balanceamento<br> Decidimos balancear os dados, já que a quantidade de "Não Sobreviventes" era maior do que a de "Sobreviventes", então utilizamos o método "undersample" para igualar "Não Sobreviventes" e "Sobreviventes", e não ter discrepância na precisão dos modelos.<br>
>5- Melhores atributos<br> Através do algoritmo "chi²" nós verificamos quais atributos tinham mais "influência" na base de dados, observamos que a coluna "Fare" tinha uma pontuação muito alta, então decidimos normalizar a coluna e observar a pontuação novamente, o resultado depois na normalização foi mais satisfatório.<br>

>#### 3.2 Pré-processamento e tratamento na base de dados em estudo:<br>
>1- Análise de nulos<br> Através do método "Heatmap" e da função "isnull", verificamos que a base de dados possuia muitos nulos, então decidimos remover as colunas que possuia mais de 90% de seus dados nulos.<br>
>Antes da Remoção<br>![Antes da Remoção](https://github.com/gmarchezi/lae1/blob/main/Imagens/Depressao_Analise_Nulos.png?raw=true)
>Depois da Remoção<br>![Depois da Remoção](https://github.com/gmarchezi/lae1/blob/main/Imagens/Depressao_Analise_Nulos_2.png?raw=true)
>2- Melhores atributos<br>Utilizando o algoritmo "chi²" selecionamos os 50 melhores atributos gerais e utilizamos este mesmo algoritmo para selecionar os 30 melhores atributos de depressão, os 10 de doença crônica e 10 das perguntas gerais. Logo tivemos 2 datasets diferentes para testes.<br>
>3- Balanceamento<br> Fazendo a contagem de pessoas com depressão e pessoas sem a doença conseguimos observar que existiam mais diagnosticos positivos que negativos então resolvemos realizar um "undersample" para o balanceamento das informações e não termos discrepância na precisão dos modelos.<br>
>![Balanceamento](https://github.com/gmarchezi/lae1/blob/main/Imagens/Balanceamento.png?raw=true)

### 4.Análise Exploratória dos datasets<br>
Explore conjunto de dados por meio de uma ferramenta (EDA), destacando em suas observações o que for considerado mais relevante.

>#### 4.1 Análise exploratória na base de dados clássica:<br>
>Com o pandas profiling conseguimos observar que existiam 8 variáveis dentre elas 5 do tipo numérica e 3 categoricas. Percebemos também que tiveram mais não sobreviventes que sobreviventes, além disso a quantidade de pessoas do sexo masculino era maior que a de pessoas do sexo feminino e os passageiros em sua maioria possuiam de 20 à 30 anos.<br>
>Passageiros da terceira classe eram em sua maioria quase 50% dos registros como o esperado por ser a classe mais economica.
>#### 4.2 Análise exploratória na base de dados em estudo:<br>
>...    
Sugestão: Utilizar ferramentas como Pandas Proffile e Sweetviz , Seaborn e Matplotlib <br>
    
[Tutorial básico com Seaborn](https://github.com/profmoisesomena/escience_and_tools/blob/master/seaborn/Seaborn_introduction.ipynb "Seaborn Introduction")

># Marco de Entrega 01: Itens do Sprint 01 <br>
    
### 5.processos de Classificação  (explicação + datasets)<br>
    A) Explicação sobre o algoritmo/método de classificação adotado
    B) Implementar método nos datasets utilizados
    
>#### 5.1 Processo de classificação na base de dados clássica:<br>
>...
>#### 5.2 Processo de classificação na base de dados obtida:<br>
>...


### 6.processos de Estimação  (explicação + datasets)<br>
    A) Explicação sobre o algoritmo/método de classificação adotado
    B) Implementar método nos datasets utilizados
    
>#### 6.1 Processo de estimação/regressão na base de dados clássica:<br>
>...
>#### 6.2 Processo de estimação/regressão na base de dados obtida:<br>
>...
>
># Marco de Entrega 02: Itens do Sprint 02 <br>

### 7.Automated machine learning - AutoML <br>
    A) Explicação sobre o que é e o processo de AutoML
    B) Aplicar o processo de AutoML nos conjuntos de dados utilizados
    
>#### 7.1 Processo de AutoML na base de dados clássica:<br>
>...
>#### 7.2 Processo de AutoML na base de dados obtida:<br>
>...
>
### 8. Resultados e Artefatos
>#### 8.1 Slides Finais
>#### 8.3 Demais artefatos solicitados pelo professor


># Marco de Entrega 03: Conclusão das atividades <br>

### 9 FORMATACAO NO GIT:<br> 
https://help.github.com/articles/basic-writing-and-formatting-syntax/
<comentario no git>
    
##### About Formatting
    https://help.github.com/articles/about-writing-and-formatting-on-github/
    
##### Basic Formatting in Git
    
    https://help.github.com/articles/basic-writing-and-formatting-syntax/#referencing-issues-and-pull-requests
    
    
##### Working with advanced formatting
    https://help.github.com/articles/working-with-advanced-formatting/
#### Mastering Markdown
    https://guides.github.com/features/mastering-markdown/

    
### OBSERVAÇÕES IMPORTANTES

#### Todos os arquivos que fazem parte do projeto (Imagens, pdfs, arquivos fonte, etc..), devem estar presentes no GIT. Os arquivos do projeto vigente não devem ser armazenados em quaisquer outras plataformas.
1. <strong>Caso existam arquivos com conteúdos sigilosos<strong>, comunicar o professor que definirá em conjunto com o grupo a melhor forma de armazenamento do arquivo.

#### Todos os grupos deverão fazer Fork deste repositório e dar permissões administrativas ao usuário do git "profmoisesomena", para acompanhamento do trabalho.

#### Os usuários criados no GIT devem possuir o nome de identificação do aluno (não serão aceitos nomes como Eu123, meuprojeto, pro456, etc). Em caso de dúvida comunicar o professor.

Link para curso de GIT<br>
![https://www.youtube.com/curso_git](https://www.youtube.com/playlist?list=PLo7sFyCeiGUdIyEmHdfbuD2eR4XPDqnN2?raw=true "Title")


