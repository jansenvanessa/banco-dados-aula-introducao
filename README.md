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

<IMAGEM>

Vamos simular esse banco em uma tabela? https://docs.google.com/spreadsheets/d/1G0tPKeKvCHS1_Q0-w6GAWa4G_xKwdcwN73c9dOxL0V4/edit#gid=1916395408

### Banco de dados não relacionais (noSQL)

No banco de dados não relacional não temos esse esquema de tabelas e linhas de tabela. Se não temos tabelas como isso fica armazenado então? 
    
#### Modelos de bancos noSQL
    
MongoDB – CRUD, collection, database, document;
    
    (Citar "modelos" => Documento, Grafos, Chave/Valor, Colunas )
    
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
```
    
### Resumindo: Banco de Dados Relacional (SQL) x Banco de Dados Não Relacional (NoSQL):
    
![sql_nosql](https://miro.medium.com/max/1012/1*yYKwVI81AiZA78NJySgRYQ.png)

* O conceito de modelo relacional (SQL) se baseia no armazenamento de dados em tabelas que se relacionam. Já no modelo não-relacional (NoSQL) esses dados ficam armazenados em, por exemplo, documentos.
* Como saber então qual utilizar? Não sei! Tudo vai depender do seu projeto, é bom sempre analisar o que precisará ser feito para decidir o que é melhor de usar. Por exemplo, às vezes fazer consultas em diversas tabelas para conseguir retornar a informação que precisa, quando a base é exageradamente grande, pode exigir muito do seu banco de dados relacional. Pode ser que nesse caso faça sentido utilizar um não relacional (noSQL). Sempre vale uma análise pois cada caso é sempre um caso.

