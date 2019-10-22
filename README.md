Trabalho 2 de Inteligência Artificial   Tema: Algoritmos de busca Forward Chaining e Backward Chaining - Famílias da mitologia nórdica
Professora: Aline Paes Disciplina/Semestre: Inteligência Artificial/2019.1
Alunos: Alan Gomes, Eduardo Peniche e Marcelo José

1. Introdução
Construímos o grafo de conhecimento, extraindo as relações e entidades da base textual, que então foi traduzido para a linguagem Prolog. Em seguida escrevemos as regras em Prolog. Utilizamos o plugin Prolog Development Tools (ProDT) na IDE Eclipse para fazer a parte em Prolog.
Decidimos então após discussões as perguntas a serem respondidas a partir da base de conhecimento extraída do texto relativo a mitologia nórdica, tanto em Prolog como em Python.

2. Base Textual
Utilizamos como base textual a árvore genealógica dos deuses da mitologia nórdica, com a motivação de que é uma forma fácil entender, uma vez que é bastante intuitivo. A base foi montada a partir do site https://thenorsegods.com/norse-gods/​ .

3. Perguntas Elaboradas
As perguntas foram escolhidas visando construir diferentes funções para trabalharmos com a base de várias maneiras diferentes.
3.1.1 Quem é filho de X que é filho da mulher de Y? ​ (ou seja, se o filho é legítimo)
3.1.1. Qual é o tio de X?
3.2.1 X descende de Y ?
3.3.1 O pai do deus do(a) X é o deus do(a) Y ​ (seriam os stats) ​ ?

4. Respostas Devolvidas
4.1. Quem é filho de X que é filho da mulher de Y?
Filhos legítimos Odin: Balder
Thor: []
4.2. Qual é o tio de X?
Tios de Balder: Ve , Vili
Tios de Thor: Day , Ve , Vili
Tios de Odin: []
4.3. ​ X descende de Y ?
Magni é descendente de Loki = Sim
Thor é descendente de Odin = Sim
Loki é descendente de Odin = Não
4.4. ​ O pai do deus do(a) X é o deus do(a) Y ?
Deus do trovão é filho do deus da lógica = Sim
Deus do amor é filho do deus da lógica = Sim
Deus do amor é filho do deus do conhecimento = Sim
Deus do amor é filho do deus do trovão = Não

5.Base de conhecimento
A base de conhecimento utilizada foi extraída a partir da base textual, indicada no item ​ 1. ​

6. Outras fontes de informação utilizadas
Como foi dito anteriormente, não foi utilizada uma base textual do wikipedia, e também não nos apoiamos em uma base de conhecimento já existente (como o Freebase).

7. Documentação Associada à implementação
Não foi realizada uma documentação à parte, contudo todo o código em Python está comentado.

8. Resultados Obtidos 
Esse é gafo das relações de geração: X é parent de Y

Consultas:
8.1 ​ ancestral(buri,modi). : a árvore de resposta dessa consulta será: modi -> thor -> odin -> bor -> buri. A resposta é True.
Mas o algoritmo consultará de forma recursiva todos os nós “filhos” até que chegar ao nó de destino. Encontrando o nó de destino a resposta é True, se não encontrar o nó de deistino a resposta é False.
8.2 descendent(magni,loki). : a árvore de resposta dessa consulta será: loki - > narvi -> night -> earth -> thor -> magni. A resposta é True.
Mas o algoritmo consultará de forma recursiva todos os nós “filhos” até que chegar ao nó de destino. Encontrando o nó de destino a resposta é True, se não encontrar o nó de deistino a resposta é False.
8.3 ancestral(forseti,thor). : a árvore de resposta dessa consulta será: thor -> odin -> bor -> buri -> earth -> night -> narvi -> loki -> skgyn. Como não foi encontrado o nó de deistino, o resultado da consulta será False.
8.4 descendent(frya,hod). : a árvore de resposta dessa consulta será: hod -> odin -> bor -> buri. Como o nó de destino não foi encontrado temos False como o resultado da consulta.

9. Conclusão
As perguntas foram respondidas utilizando as regras, no qual utilizamos Python e também o Prolog. Nós realizamos algumas perguntas utilizando o algoritmo de Forward Chaining, e outras no Backward Chaining, visando utilizar o algoritmo que melhor atendia a pergunta em questão.
