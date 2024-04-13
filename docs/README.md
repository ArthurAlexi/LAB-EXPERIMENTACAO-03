# Relatório

#### Sumário:

- [Introdução](#introducao)
- [Metodologia](#metodologia)
- [Definiçãs de métricas](#metricas)
- [Hipóteses informais](#hipoteses)
- [Questões de pesquisa](#questoes)
- [Resultados](#resultados)
- [Conclusão](#conclusao)


<a id='introducao'></a>
## Introdução

A prática de code review tornou-se uma constante nos processos de desenvolvimento agéis. Em linhas gerais, ela consiste na interação entre desenvolvedores e revisores visando inspecionar o código produzido antes de integrá-lo à base principal. Assim, garante-se a qualidade do código integrado, evitando-se também a inclusão de defeitos. No contexto de sistemas open source, mais especificamente dos desenvolvidos através do GitHub, as atividades de code review acontecem a partir da avaliação de contribuições submetidas por meio de Pull Requests (PR). Ou seja, para que se integre um código na branch principal, é necessário que seja realizada uma solicitação de pull, que será avaliada e discutida por um colaborador do projeto. Ao final, a solicitação de merge pode ser aprovada ou rejeitada pelo revisor. Em muitos casos, ferramentas de verificação estática realizam uma primeira análise, avaliando requisitos de estilo de programação ou padrões definidos pela organização.

Neste contexto, o objetivo deste laboratório é analisar a atividade de code review desenvolvida em repositórios populares do GitHub, identificando variáveis que influenciam no merge de um PR, sob a perspectiva de desenvolvedores que submetem código aos repositórios selecionados. 

<a id='metodologia'></a>
## Metodologia

1. Criação do Dataset
O dataset utilizado neste laboratório será composto por PRs submetidos a repositórios:

- populares (ou seja, avaliaremos PRs submetidos aos 200 repositórios mais populares do GitHub);
- que possuam pelos menos 100 PRs (MERGED + CLOSED).
Além disso, a fim de analisar pull requests que tenham passado pelo processo de code review, selecionaremos apenas aqueles:

- com status MERGED ou CLOSED;
- que possuam pelo menos uma revisão (total count do campo review).

Por fim, visando remover do nosso dataset PRs que foram revisados de forma automática (por meio de bots ou ferramentas de CI/CD), selecionaremos aqueles cuja revisão levou pelo menos uma hora (isto é, a diferença entre a data de criação e de merge (ou close) é maior que uma hora).

<a id='metricas'></a>
### 3. Definição de Métricas

Para cada dimensão, realizaremos as correlações com as métricas definidas a seguir:

- Tamanho: número de arquivos; total de linhas adicionadas e removidas.
- Tempo de Análise: intervalo entre a criação do PR e a última atividade (fechamento ou merge).
- Descrição: número de caracteres do corpo de descrição do PR (na versão markdown).
- Interações: número de participantes; número de comentários.

<a id='questoes'></a>
### 3. Questões de Pesquisa

#### A. Feedback Final das Revisões (Status do PR):

- RQ 01. Qual a relação entre o tamanho dos PRs e o feedback final das revisões?
- RQ 02. Qual a relação entre o tempo de análise dos PRs e o feedback final das revisões?
- RQ 03. Qual a relação entre a descrição dos PRs e o feedback final das revisões?
- RQ 04. Qual a relação entre as interações nos PRs e o feedback final das revisões?
 

#### B. Número de Revisões:

- RQ 05. Qual a relação entre o tamanho dos PRs e o número de revisões realizadas?
- RQ 06. Qual a relação entre o tempo de análise dos PRs e o número de revisões realizadas?
- RQ 07. Qual a relação entre a descrição dos PRs e o número de revisões realizadas?
- RQ 08. Qual a relação entre as interações nos PRs e o número de revisões realizadas?

<a id='hipoteses'></a>
## Hipóteses informais

- RQ 01. Qual a relação entre o tamanho dos PRs e o feedback final das revisões?

PRs com tamanho maior podem levar a feedbacks mais críticos devido à complexidade envolvida, resultando em uma menor probabilidade de aprovação.

- RQ 02. Qual a relação entre o tempo de análise dos PRs e o feedback final das revisões?

PRs que passam por análise mais demorada podem receber feedbacks mais detalhados e precisos, levando a uma maior probabilidade de aprovação.

- RQ 03. Qual a relação entre a descrição dos PRs e o feedback final das revisões?

PRs com descrições claras e informativas podem levar a uma compreensão mais fácil do que está sendo proposto, aumentando a probabilidade de aprovação.

- RQ 04. Qual a relação entre as interações nos PRs e o feedback final das revisões?

 Um maior número de interações nos PRs, como discussões construtivas entre colaboradores, pode indicar uma revisão mais profunda e colaborativa, levando a uma maior probabilidade de aprovação.

- RQ 05. Qual a relação entre o tamanho dos PRs e o número de revisões realizadas?

PRs com tamanho maior podem exigir mais revisões devido à sua complexidade e potencial para conter mais erros ou problemas.

- RQ 06. Qual a relação entre o tempo de análise dos PRs e o número de revisões realizadas?

PRs que passam por análise mais demorada podem levar a um maior número de revisões, já que há mais tempo para identificar e discutir possíveis problemas.

- RQ 07. Qual a relação entre a descrição dos PRs e o número de revisões realizadas?

PRs com descrições mais detalhadas e claras podem levar a um menor número de revisões, pois proporcionam uma compreensão mais completa do que está sendo proposto.

- RQ 08. Qual a relação entre as interações nos PRs e o número de revisões realizadas?

Um maior número de interações nos PRs pode indicar uma revisão mais colaborativa e iterativa, resultando em um maior número de revisões à medida que os colaboradores trabalham juntos para aprimorar o código.
