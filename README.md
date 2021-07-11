<h1 align="center">
    <br>
    <p align="center">Semana 12 - Introdução ao Banco de Dados<p>
</h1>

## O que é um banco de dados?

![banco_de_dados](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTW8kxwgWPiXr77gcQiAxMqBTLKkuJlFK8PfRRWHsUjyeJ0NvLeGAjQHKemgrFZCJYHRZ0&usqp=CAU)

* Banco de dados é uma coleção organizada onde se pode armazenar dados, de forma estruturada podendo ser consultada por um programa ou pessoa permitindo extrair informações.

### Exemplo

![clinica_medica](https://image.freepik.com/free-vector/doctor-patient-desk-hospital-office-clinic-visit-exam-meeting-with-physician-conversation-with-medic-about-diagnosis-results_284092-936.jpg)

Temos uma clínica médica e precisamos organizar nossos dados para que possamos controlar tudo! Que tipo de dados temos?

* Dados de Pacientes: Nome, Plano de Saúde, Carteirinha, Endereço, Telefone
* Dados de Profissionais da Saúde: Nome, Documento profissional (ex: CRM para médicas(os), Coren para enfermeiras(os)), Especialidade, Endereço, Telefone
* Dados de Consultas: Médico, Paciente, Data Hora, Prescrições (remédios receitados), Exames (exames prescritos), Prontuário (anotações da consulta)

Podemos organizar nossos dados de forma relacional e de forma não relacional. Para isso podemos utilizar um banco de dados relacional ou um banco de dados não relacional. Mas o que é cada uma dessas duas formas diferentes???!

### Banco de dados relacionais

No banco de dados relacional nossas informações ficam em tabelas e se relacionam. Vamos montar nosso banco de dados relacional da nossa clínica? Primeiro vamos desenhar um modelo para nosso banco:

<IMAGEM>

Vamos simular esse banco em uma tabela? https://docs.google.com/spreadsheets/d/1G0tPKeKvCHS1_Q0-w6GAWa4G_xKwdcwN73c9dOxL0V4/edit#gid=1916395408

### Banco de dados não relacionais

No banco de dados não relacional não temos esse esquema de tabelas e linhas de tabela. Se não temos tabelas como isso fica armazenado então? Ficam em documentos!
    
Como ficariam minhas consultas em um banco noSQL (não relacional)?
    
```
[
    {
        "id": ,
        "dataHora": ,
        "profissionalSaude" : { },
        "paciente": {},
        "prescricoes": "",
        "exames": "",
        prontuario: "",
    },
    {
        "id": ,
        "dataHora": ,
        "profissionalSaude" : { },
        "paciente": {},
        "prescricoes": "",
        "exames": "",
        prontuario: "",
    },
```
    
### Resumindo: Banco de Dados Relacional (SQL) x Banco de Dados Não Relacional (NoSQL):
    
![sql_nosql](https://miro.medium.com/max/1012/1*yYKwVI81AiZA78NJySgRYQ.png)

* O conceito de modelo relacional (SQL) se baseia no armazenamento de dados em tabelas que se relacionam. Já no modelo não-relacional (NoSQL) esses dados ficam armazenados em documentos.
* Como saber então qual utilizar? Não sei! Tudo vai depender do seu projeto, é bom sempre analisar o que precisará ser feito para decidir o que é melhor de usar. Por exemplo, às vezes fazer consultas em diversas tabelas para conseguir retornar a informação que precisa, quando a base é exageradamente grande, pode exigir muito do seu banco de dados relacional. Pode ser que nesse caso faça sentido utilizar um não relacional (noSQL). Sempre vale uma análise pois cada caso é sempre um caso.
