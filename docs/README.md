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


<a id='resultados'></a>
## Resultados

- ### RQ 01. Qual a relação entre o tamanho dos PRs e o feedback final das revisões?

||||
|:-:|:-:|:-:|
| Relação entre Decisão da Review e Adições de Linhas | Relação entre Decisão da Review e Remoção de Linhas | Relação entre Decisão da Review e Total de arquivos |
|<img  src="https://github.com/ArthurAlexi/LAB-EXPERIMENTACAO-03/assets/90854173/e6de5b09-e857-46a5-920d-f509a4057e60" alt="Relação entre Decisão da Review e Adições de Linhas" align="left" height="auto" width="400">|<img src="https://github.com/ArthurAlexi/LAB-EXPERIMENTACAO-03/assets/90854173/b1882eb7-c528-4aa2-af25-b438317223b8" alt="Relação entre Decisão da Review e Remoção de Linhas (Violin Plot por Decisão)" align="left" height="auto" width="400">| <img src="https://github.com/ArthurAlexi/LAB-EXPERIMENTACAO-03/assets/90854173/d83c8395-f9ab-465a-bfe5-34d2bc87421a" alt="Relação entre Decisão da Review e Total de arquivos" align="left" height="auto" width="400" >|

- ### RQ 02. Qual a relação entre o tempo de análise dos PRs e o feedback final das revisões?

<div align="center">

<img  src="https://github.com/ArthurAlexi/LAB-EXPERIMENTACAO-03/assets/90854173/eb041386-2e9e-4792-b61b-e9716d7536e4" alt="Relação entre Decisão da Review e tempo de fechamento"  height="auto"  width="600" >
 
</div>


- ### RQ 03. Qual a relação entre a descrição dos PRs e o feedback final das revisões?

<div align="center">

<img  src="https://github.com/ArthurAlexi/LAB-EXPERIMENTACAO-03/assets/90854173/21ad2b69-46a3-435e-8e88-fa858eb3db3e" alt="Relação entre Decisão da Review e feedback final das revisões"  height="auto"  width="600" >
 
</div>

- ### RQ 04. Qual a relação entre as interações nos PRs e o feedback final das revisões?

<div align="center">

<img  src="https://github.com/ArthurAlexi/LAB-EXPERIMENTACAO-03/assets/90854173/880447e4-3584-43d3-b4ad-bdd4208c9194" alt="Relação entre Decisão da Review e Interações"  height="auto"  width="600" >
 
</div>

- ### RQ 05. Qual a relação entre o tamanho dos PRs e o número de revisões realizadas?

||||
|:-:|:-:|:-:|
| Relação entre número de revisões realizadas e Total de arquivos | Relação entre número de revisões realizadas e Adições de Linhas | Relação entre número de revisões realizadas e Remoção de Linhas |
|<img  src="https://github.com/ArthurAlexi/LAB-EXPERIMENTACAO-03/assets/90854173/4cf04cb0-f37e-413e-b83c-14a08127e225" alt="Relação entre número de revisões realizadas e Adições de Linhas" align="left" height="auto" width="300">|<img src="https://github.com/ArthurAlexi/LAB-EXPERIMENTACAO-03/assets/90854173/c7d35b5f-bf94-4b2a-80d0-073b7a0fe36a" alt="Relação entre número de revisões realizadas e Remoção de Linhas" align="left" height="auto" width="300">| <img src="https://github.com/ArthurAlexi/LAB-EXPERIMENTACAO-03/assets/90854173/8cc5f359-8b1b-4e23-9aa8-e9c14cc87eb3" alt="Relação entre número de revisões realizadas e Total de arquivos" align="left" height="auto" width="300" >|

- ### RQ 06. Qual a relação entre o tempo de análise dos PRs e o número de revisões realizadas?

|||
|:-:|:-:|
| Fechamento | Merge |
|<img  src="https://github.com/ArthurAlexi/LAB-EXPERIMENTACAO-03/assets/90854173/11305f10-1ea6-4c44-b2a4-5936277f5ff2" alt="" align="left" height="auto" width="500">|<img src="https://github.com/ArthurAlexi/LAB-EXPERIMENTACAO-03/assets/90854173/c2b26d98-df45-4953-88d5-6f0255b123f0" alt="Relação entre número de revisões realizadas e Remoção de Linhas" align="left" height="auto" width="500">|

- ### RQ 07. Qual a relação entre a descrição dos PRs e o número de revisões realizadas?

|||
|:-:|:-:|
| total de comentários x Reviws | nº caracteres no body x Reviws |
|<img  src="https://github.com/ArthurAlexi/LAB-EXPERIMENTACAO-03/assets/90854173/a982e738-d861-4a6f-974a-4242384a7ab7" alt="" align="left" height="auto" width="500">|<img src="https://github.com/ArthurAlexi/LAB-EXPERIMENTACAO-03/assets/90854173/60cef679-6aac-458d-b8fc-fd73e47db0eb" alt="Relação entre número de revisões realizadas e Remoção de Linhas" align="left" height="auto" width="500">|

- ### RQ 08. Qual a relação entre as interações nos PRs e o número de revisões realizadas?

<div align="center">

<img  src="https://github.com/ArthurAlexi/LAB-EXPERIMENTACAO-03/assets/90854173/65b6d036-ae75-412b-bae7-bff049525e91" alt=""  height="auto"  width="600" >
 
</div>
