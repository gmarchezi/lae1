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
>... 

### 3.Pré-processamento dos Datasets <br>

Realize o Pré-processamento e Tratamento de Dados em sua base/dataset.

>#### 3.1 Pré-processamento e tratamento na base de dados clássica:<br>
>Verificamos os nulos em cada coluna utilizando o método "Heatmap" oferecido pela biblioteca Seaborn para ter uma análise visual e a função "isnull" da biblioteca Pandas para termos a quantidade de nulos em cada coluna, tratamos esses nulos retirando a coluna "Cabin" que possuia nulos na maioria das linhas, retiramos as linhas onde o atributo "Age" estava nulo, também retiramos colunas que a princípio não afetaria no resultado final, como "PassengerId", "Name", "Ticket" e "Embarked". Utilizamos o método Label Enconding na coluna "Sex", pois se trata de uma variável binária e queriamos trabalhar com números, 0 = Feminino e 1 = Masculino. Fizemos um balanceamento por meio da função "sample", já que a quantidade de Não Sobreviventes era consideravelmente maior do que a de Sobreviventes e isso poderia afetar a precisão do modelo, aplicamos o método "chi²" para verificar os atributos mais influentes do dataset através de uma pontuação que o mesmo retorna, verificamos que o atributo "Fare" possuia uma pontuação muito grande em relação aos outros atributos e isso poderia afetar a pontuação dos outros atributos e a precisão do modelo, fizemos a normalização da coluna "Fare" e aplicamos o "chi²" novamente e as pontuações mudaram, ficando assim mais plausível com o que esperávamos.
>#### 3.2 Pré-processamento e tratamento na base de dados em estudo:<br>
>...    

### 4.Análise Exploratória dos datasets<br>
Explore conjunto de dados por meio de uma ferramenta (EDA), destacando em suas observações o que for considerado mais relevante.

>#### 4.1 Análise exploratória na base de dados clássica:<br>
>...
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


