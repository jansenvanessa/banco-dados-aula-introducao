<h1 align="center">
    <br>
    <p align="center">Semana 12 - Introdução ao Banco de Dados<p>
</h1>

## O que é um banco de dados?

Antigamente organizávamos nossos dados em papel e arquivos físicos, e com o tempo ficava bem difícil administrar essas informações. Além da dificuldade para lidar com essas informações, existia também um enorme risco de perdermos essa folha de papel que tinha nosso dado ou mesmo cair em mãos erradas. Hoje com um banco de dados conseguimos armazenar essas informações digitalmente, de forma segura, e recuperar muito mais facilmente os dados que precisamos, além de permitir que mais de uma pessoa acesse a mesma informação ao mesmo tempo, o que seria impossível com uma única folha de papel.

Em termos gerais, podemos definir banco de dados como uma coleção organizada onde se pode armazenar dados, de forma estruturada podendo ser consultada por um programa ou pessoa permitindo extrair informações. Ficou um pouco confuso? Não se preocupe, vamos entender melhor o que é e como funciona ao longo desse curso! Ao final essa definição ficará muito mais clara.

![banco_de_dados](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTW8kxwgWPiXr77gcQiAxMqBTLKkuJlFK8PfRRWHsUjyeJ0NvLeGAjQHKemgrFZCJYHRZ0&usqp=CAU)

## Clínica Jansen's Anatomy

![clinica_medica_greys_anatomy](https://uploads.jovemnerd.com.br/wp-content/uploads/2018/10/greys-anatomy-1210x540.png)

### Problema

A clínica Jansen's Health é um pouco "cringe", então costuma agendar as consultas e dados do paciente na agenda a caneta. Com o passar do tempo e com a clínica crescendo está ficando insustentável manter o que temos hoje. Toda vez que precisamos de qualquer informação do paciente ou mesmo das consultas do médico demoramos muito para achar o que precisamos. Além disso temos dados super importantes em anotações, como prontuário e todo um histórico de pacientes. Se perdermos uma folha, podemos perder algo muito importante e sensível. Com todo esse cenário caótico, a clínica pediu nossa ajuda para organizar esses dados para melhorar o dia a dia deles e dos pacientes.

![homer_desesperado](https://medicinamardelplata.files.wordpress.com/2018/05/homer.png)


### Como resolver isso?

Nesse primeiro momento, onde vamos ajudá-los, a clínica precisa organizar os dados de consultas. Essas consultas são compostas de informações da consulta e informações do paciente atendido e médico que atendeu.

O que temos desses dados?

* **Dados de Pacientes**: *Nome, Plano de Saúde, Carteirinha, Endereço, Telefone*
* **Dados de Médicos**: *Nome, Documento profissional (ex: CRM), Especialidade, Telefone*
* **Dados de Consultas**: *Médico, Paciente, Data Hora, Prescrições (remédios receitados), Exames (exames prescritos), Prontuário (anotações da consulta)*

Pronto, anotamos as informações utilizadas no dia a dia da clínica e agora? Como a gente vai organizar isso? Podemos organizar nossos dados de forma relacional e de forma não relacional. Mas o que é cada uma dessas duas formas diferentes???!

![bob_esponja_pensativo](https://64.media.tumblr.com/tumblr_m2a0k4mEF71rsmfs0o1_250.gifv)

---

### Banco de dados relacionais (SQL)

No banco de dados relacional nossas informações ficam em tabelas e se relacionam. Os bancos de dados relacionais são conhecidos como banco de dados SQL. Essa sigla SQL siginifica “Structured Query Language” que traduzindo para o português significa: “Linguagem de Consulta Estruturada”.
Com o SQL, você pode executar vários comandos para criar, alterar, gerenciar, consultar, dentre outras informações no seu banco de dados. Costumamos dizer que bancos SQL seguem uma modelagem relacional, pois estes se baseiam no fato de que todos seus dados sejam guardados em tabelas.

Agora que entendemos um pouco o que seria um banco de dados relacional, vamos montar um esboço do nosso banco de dados relacional da nossa clínica? Primeiro vamos desenhar um modelo para nosso banco:

![bd_relacional](https://i.imgur.com/8l5vVxf.png?1)

Vamos simular esse banco em uma tabela? https://docs.google.com/spreadsheets/d/1G0tPKeKvCHS1_Q0-w6GAWa4G_xKwdcwN73c9dOxL0V4/edit#gid=1916395408

Um exemplo de um comando SQL para trazer todas as informações da minha tabela de Pacientes seria:

```
SELECT * FROM PACIENTES
```
Esse comando acima significa: *selecionar tudo de Pacientes*. Feito isso serão retornadas todas as linhas da tabela Pacientes.

### Banco de dados não relacionais (noSQL)

No banco de dados não relacional não utilizamos o *SQL* (por isso chamamos de noSQL - não SQL) e também não temos esse esquema de tabelas e linhas. Se não temos tabelas como isso fica armazenado então? Temos alguns modelos de bancos noSQL e vamos falar um pouco deles agora para entender melhor como os dados ficariam armazenados:

![bd_nao_relacional](https://i.imgur.com/fHnOR4O.png)

#### Banco de dados de Documentos (noSQL)
    
Esse banco de dados foi projetado para armazenar e consultar dados como documentos do tipo JSON. Os bancos de dados de documentos facilitam para que os desenvolvedores armazenem e consultem dados usando o mesmo formato de modelo de documento que usam no código da aplicação. **Um exemplo de banco de dados de documentos é o famoso MongoDB!**

As consultas médicas do Jansen's Anatomy em um banco noSQL (não relacional) de Documentos ficariam assim nesse formato:
    
```
[
    {
        "_id": "a24e470f-08c0-4c03-8312-18575a41d247",
        "dataHora": "12/07/2021 10:00:00" ,
        "medico" : { 
                nome: "Sarah Freitas", 
                documentoProfissional: "CRM-SP 1234",
                especialidade: "Clínica Médica",
                telefone: "(11) 1212-12112",
        },
        "paciente": {
                nome: "Rita da Silva",
                telefone: "(11) 8888-8888"
        },
        "prescricoes": "Tomar remédio x para dor 2 vezes ao dia por 5 dias.",
        "exames": "Ressonancia Magnetica e Raio X",
        prontuario: "Paciente se queixa de dor nas costas",
    },
    {
        "_id": "72a84cf4-c21d-4ed1-9cff-ab23260182d7",
        "dataHora": "12/07/2021 11:00",
        "medico" : { 
                nome: "Sarah Freitas", 
                documentoProfissional: "CRM-SP 1234",
                especialidade: "Clínica Médica",
                telefone: "(11) 1212-12112",
        },
        "paciente": {
                nome: "Daniel Borges",
                planoSaude : "Bradesco",
                carteirinha: "98765432",
                endereco: "Avenida dos Papagaios número 131 apto 55A",
                telefone: "(11) 7777-7777"
        },
        "prescricoes": "Remédio para dor de estômago",
        "exames": "Endoscopia",
        prontuario: "Paciente se queixa de dor e queimação no estômago",
    },
    // E todo o restante dos dados em diante
]
```
#### Banco de dados de Grafos (noSQL)

Os bancos de dados grafo utilizam nós para armazenar entidades de dados e bordas para armazenar os relacionamentos entre as entidades. Uma borda tem sempre um nó inicial, um nó final, um tipo e um direcionamento, o que possibilita a descrição dos relacionamentos entre pais e filhos, das ações, das propriedades e assim por diante. A quantidade e os tipos de relacionamentos que um nó pode ter são ilimitados. **Um exemplo de banco de dados de Grafos é o Arangodb.**

O gráfico a seguir é um exemplo de gráfico de rede social. Considerando as pessoas (nós) e seus relacionamentos (bordas), é possível descobrir quem são os “amigos dos amigos” de uma pessoa específica:

![bd_nao_relacional](https://d1.awsstatic.com/diagrams/foaf-graph.e5e42865e0ee97a2972f9014d28f525ef68a981b.png)

#### Banco de dados de Chave-Valor (noSQL)

É um tipo de banco de dados não relacional que usa um método de chave-valor simples para armazenar dados. Um banco de dados de chave-valor armazena dados como um conjunto de pares de chave-valor em que uma chave funciona como um identificador exclusivo. Os dados dentro de bancos de chave-valor são formados por duas partes: uma string, que representa a chave, e os dados em si, que são o valor. A chave é usada como um índice, permitindo que o usuário faça a requisição dos dados relacionados a ela. **Um exemplo de banco de dados de Chave-Valor é o Redis.**

#### Banco de dados Colunar (noSQL)

Enquanto um banco de dados relacional é otimizado para armazenar linhas de dados, um banco de dados colunar é otimizado para recuperação rápida de colunas de dados, normalmente em aplicativos analíticos. O armazenamento orientado a colunas para tabelas do banco de dados é um fator importante para a performance de consulta analítica, pois ele reduz expressivamente os requisitos gerais de E/S de disco e diminui a quantidade de dados que você precisa carregar do disco. **Um exemplo de banco de dados colunar é o Cassandra.**
    
### Banco de Dados Relacional (SQL) x Banco de Dados Não Relacional (noSQL)

Agora que sabemos o que é um banco relacional (SQL) e um banco de dados não relacional (noSQL), podemos falar um pouquinho das vantagens e desvantagens de cada um desses:
    
![sql_nosql](https://miro.medium.com/max/1400/0*LR8ZkHpzwTAZjBtI.png)

A diferença essencial entre as duas teconologia é que uma é baseada em esquema (Relacional) e a outra não (Não relacional). Para trabalhar com um banco SQL (Relacional) a primeira coisa que voce precisa fazer é projetar a estrutura do banco, isto é, voce não consegue inserir um dado se não tiver previamente definido os "esquemas" das tabelas, enquanto que em um banco de dados NoSQL (Não relacional) isso não é necessário.

O NoSQL tem muitas vantagens para ser utilizado. Mas não é por isso que devemos utilizá-lo em todas as situações. Em muitos sistemas, você pode (e até deve) usar o modelo relacional. O NoSQL é mais indicado para aqueles sistemas que tenham necessidades maiores de armazenamento e desempenho. O NoSQL não veio para substituir o SQL, mas sim para oferecer mais uma alternativa de um banco de dados mais flexível no suporte de dados. Sendo assim, você pode usar ambas as soluções para diferentes casos de uso. Por isso, o mais comum em soluções escalares de sucesso é a utilização de uma arquitetura híbrida, aproveitando o melhor dois dois modelos.

#### Qual banco de dados utilizar? SQL ou NoSQL?

Depende! Tudo vai depender do seu projeto, então sempre bom analisar o que precisará ser feito para decidir qual banco de dados é melhor para usar. Por exemplo, às vezes fazer consultas em diversas tabelas para conseguir retornar a informação que precisa, quando a base é exageradamente grande, pode exigir muito do seu banco de dados relacional. Pode ser que nesse caso faça sentido utilizar um não relacional (noSQL). Sempre vale uma análise pois cada caso é sempre um caso.

## SGBD (Sistema de Gerenciamento de Banco de Dados)

Os Sistemas de Gerenciamento de Banco de Dados são softwares utilizados para gerir as estruturas de armazenamento dos dados, permitem realizar manipulações, bem como controlar as permissões de utilização dos bancos de dados. Aqui nesse curso iremos focar no MongoDB para trabalhar com nossos dados!

![sgdb](https://i.imgur.com/kJokS8A.png?1)

## O que é o MongoDB?

## Instalação do MongoDB e Robo 3T



## Comandos básicos

1. Base de Dados
    1. Exibir existentes - `show dbs`
    1. Selecionar para uso (e criar, caso não exista) - `use nome-do-database`
    1. Excluir base selecionada - `db.dropDatabase()`
1. Coleção
    1. Criar coleção de documentos - `db.createCollection('nome-da-collection')` (Mongo é case sensitive)
    1. Exibir todas as coleções - `show collections`
    1. Apagar coleção de documentos - `db.nomedacollection.drop()`
1. Documentos
    1. Inserir - `db.nomedacollection.insert(documento)`
    1. Importar documentos de um arquivo - `mongoimport <options> <connection-string> <file>`
    1. Consultar -  `db.nomedacollection.find({selecao})`
        1. Igualdade - `{<key>:<value>}`
        1. Menor que - `{<key>:{$lt:<value>}}`
        1. Menor ou igual - `{<key>:{$lte:<value>}}`
        1. Maior que - `{<key>:{$gt:<value>}}`
        1. Maior ou igual - `{<key>:{$gte:<value>}}`
        1. Diferente - `{<key>:{$ne:<value>}}`
        1. AND - `{<key>:<value>, <key>:<value>}`
        1. OR - `$or:[{<key>:<value>},{<key>:<value>}]`
    1. Atualizar - `db.nomedacollection.update({selecao}, {$set:{campos-atualizados}})` (Considerar o multi)
    1. Excluir - `db.nomedacollection.remove({selecao})` (Considerar exclusão de seleção, apenas um e todos)
    1. Projetar - `db.nomedacollection.find({selecao},{<key>:1})`
    1. Limitar - `db.nomedacollection.find().limit(numero)`
    1. "Pular" - `db.nomedacollection.find().skip(numero)`
    1. Ordernar -  `db.nomedacollection.find().sort({<key>:1})` (Considerar crescente e decrescente, e combinações)

### Comandos extras

* Embelezamento - `pretty()`
* Atualizar ou Inserir - `save()`
* Indexação
* Agregação
* Backup
* Restauração

## Acabamos, e agora? Vamos exercitar!

![exercise](https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcQzkx9NbIzjUfe7io1-mvfkRybTZGH-C0RL0A&usqp=CAU)

Agora que já sabemos o que é um banco de dados, já sabemos como instalar um e já conhecemos os comandos para utilizá-lo, podemos e devemos exercitar! O que podemos criar de novo? O que podemos atualizar? O que podemos buscar de informação nesse banco de dados?

// TO DO - passar dever de casa

Espero que tenha gostado da atividade e o segredo é praticar!!! Quanto mais exercícios fizer, melhor :) Abs e até mais!

---
## Links Extras:

- [https://kenzie.com.br/blog/banco-de-dados/](https://kenzie.com.br/blog/banco-de-dados/)
- [https://rockcontent.com/br/blog/banco-de-dados/](https://rockcontent.com/br/blog/banco-de-dados/)
- [https://medium.com/xp-inc/comparando-os-termos-utilizados-no-nosql-com-sql-e862788e2374](https://medium.com/xp-inc/comparando-os-termos-utilizados-no-nosql-com-sql-e862788e2374)
- [https://medium.com/@albsilva/o-fantastico-mundo-do-nosql-2e72c5640e69](https://medium.com/@albsilva/o-fantastico-mundo-do-nosql-2e72c5640e69)
- [https://gabriel-faraday.medium.com/o-que-%C3%A9-nosql-9d7fd54792d4](https://gabriel-faraday.medium.com/o-que-%C3%A9-nosql-9d7fd54792d4)
- [https://medium.com/qaninja/principais-diferen%C3%A7as-de-um-banco-de-dados-tradicional-e-o-mongodb-4fc1117453f8](https://medium.com/qaninja/principais-diferen%C3%A7as-de-um-banco-de-dados-tradicional-e-o-mongodb-4fc1117453f8)
- [https://www.fiveacts.com.br/sgbd/](https://www.fiveacts.com.br/sgbd/)
