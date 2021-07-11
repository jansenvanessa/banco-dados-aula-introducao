<h1 align="center">
    <br>
    <p align="center">Semana 12 - Introdução ao Banco de Dados<p>
</h1>

## O que é um banco de dados?

![banco_de_dados](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTW8kxwgWPiXr77gcQiAxMqBTLKkuJlFK8PfRRWHsUjyeJ0NvLeGAjQHKemgrFZCJYHRZ0&usqp=CAU)

* Banco de dados é uma coleção organizada onde se pode armazenar dados, de forma estruturada podendo ser consultada por um programa ou pessoa permitindo extrair informações.

## Clínica Jansen's Anatomy

![clinica_medica_greys_anatomy](https://uploads.jovemnerd.com.br/wp-content/uploads/2018/10/greys-anatomy-1210x540.png)

### Problema

A clínica Jansen's Health é um pouco "cringe" então costuma agendar as consultas e dados do paciente na agenda a caneta. Com o passar do tempo e com a clínica crescendo está ficando insustentável manter o que temos hoje. Toda vez que precisamos de qualquer informação do paciente ou mesmo das consultas do médico demoramos muito para achar o que precisamos. Além disso temos dados super importantes em anotações, como prontuário e todo um histórico de pacientes. Se perdermos uma folha, podemos perder algo muito importante e sensível. Com todo esse cenário caótico, a clínica pediu nossa ajuda para organizar esses dados para melhorar o dia a dia deles e dos pacientes.

![homer_desesperado](https://medicinamardelplata.files.wordpress.com/2018/05/homer.png)


### Como resolver isso?

Nesse primeiro momento, onde vamos ajudá-los, a clínica precisa organizar os dados de consultas. Essas consultas são compostas de informações da consulta e informações do paciente atendido e médico que atendeu.

O que temos desses dados?

* **Dados de Pacientes**: *Nome, Plano de Saúde, Carteirinha, Endereço, Telefone*
* **Dados de Médicos**: *Nome, Documento profissional (ex: CRM), Especialidade, Telefone*
* **Dados de Consultas**: *Médico, Paciente, Data Hora, Prescrições (remédios receitados), Exames (exames prescritos), Prontuário (anotações da consulta)*

Pronto, anotamos as informações utilizadas no dia a dia da clínica e agora? Como a gente vai organizar isso? Podemos organizar nossos dados de forma relacional e de forma não relacional. Para isso podemos utilizar um banco de dados relacional ou um banco de dados não relacional. Mas o que é cada uma dessas duas formas diferentes???!

![bob_esponja_pensativo](https://64.media.tumblr.com/tumblr_m2a0k4mEF71rsmfs0o1_250.gifv)

---

### Banco de dados relacionais (SQL)

No banco de dados relacional nossas informações ficam em tabelas e se relacionam. Vamos montar nosso banco de dados relacional da nossa clínica? Primeiro vamos desenhar um modelo para nosso banco:

![bd_relacional](https://i.imgur.com/8l5vVxf.png?1)

Vamos simular esse banco em uma tabela? https://docs.google.com/spreadsheets/d/1G0tPKeKvCHS1_Q0-w6GAWa4G_xKwdcwN73c9dOxL0V4/edit#gid=1916395408

### Banco de dados não relacionais (noSQL)

No banco de dados não relacional não temos esse esquema de tabelas e linhas de tabela. Se não temos tabelas como isso fica armazenado então? 
    
#### Modelos de bancos noSQL
    
// TO DO
MongoDB – CRUD, collection, database, document;  (Citar "modelos" => Documento, Grafos, Chave/Valor, Colunas )
    
    
### Base de dados no banco de dados não relacional
    
Como ficariam as consultas médicas do Jansen's Anatomy em um banco noSQL (não relacional)? Poderiam ficar assim nesse formato, por exemplo:
    
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
    
### Banco de Dados Relacional (SQL) x Banco de Dados Não Relacional (NoSQL):
    
![sql_nosql](https://miro.medium.com/max/1012/1*yYKwVI81AiZA78NJySgRYQ.png)

//TO DO

#### Banco de Dados Relacional (SQL):
* Vantagens: 
* Desvantagens:

#### Banco de Dados Não Relacional (NoSQL):
* Vantagens: 
* Desvantagens:

* **Como saber então qual utilizar?** Não sei! Tudo vai depender do seu projeto, é bom sempre analisar o que precisará ser feito para decidir o que é melhor de usar. Por exemplo, às vezes fazer consultas em diversas tabelas para conseguir retornar a informação que precisa, quando a base é exageradamente grande, pode exigir muito do seu banco de dados relacional. Pode ser que nesse caso faça sentido utilizar um não relacional (noSQL). Sempre vale uma análise pois cada caso é sempre um caso.

## SGBD (Sistema de Gerenciamento de Banco de Dados)
//TO DO
< Imagem>

### O que é?
//TO DO
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
