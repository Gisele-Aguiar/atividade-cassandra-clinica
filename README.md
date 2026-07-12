# Clínica Cassandra - Atividade

## Desenvolvimento de Banco de Dados em Cassandra DB

### Tema

**Sistema de Clínica Médica**

## Introdução

Este projeto apresenta o desenvolvimento de um banco de dados NoSQL utilizando o **Apache Cassandra** para gerenciamento de informações de uma clínica médica.

O Cassandra foi escolhido por ser um banco de dados distribuído, altamente escalável e adequado para aplicações que necessitam armazenar grandes volumes de dados com alta disponibilidade.

## Objetivo

O objetivo deste projeto é desenvolver um banco de dados orientado a consultas para armazenar informações de uma clínica médica, incluindo:

* Pacientes;
* Médicos;
* Consultas;
* Exames;
* Receitas médicas.

A modelagem foi realizada seguindo os conceitos do Cassandra DB, priorizando desempenho e organização dos dados conforme as necessidades do sistema.

---

# Modelagem do Banco de Dados

## Keyspace

```sql
CREATE KEYSPACE clinica
WITH replication = {
'class': 'SimpleStrategy',
'replication_factor': 1
};
```

Utilização do Keyspace:

```sql
USE clinica;
```

---

# Estrutura das Tabelas

## Pacientes

Armazena informações dos pacientes cadastrados na clínica.

Campos principais:

* ID do paciente;
* Nome;
* CPF;
* Data de nascimento;
* Telefone.

---

## Médicos

Armazena informações dos profissionais responsáveis pelos atendimentos.

Campos principais:

* ID do médico;
* Nome;
* Especialidade;
* CRM.

---

## Consultas

Registra os atendimentos realizados.

Campos principais:

* ID da consulta;
* Paciente;
* Médico;
* Data da consulta;
* Diagnóstico.

---

## Exames

Armazena informações dos exames realizados pelos pacientes.

Campos principais:

* ID do exame;
* Paciente;
* Tipo de exame;
* Resultado;
* Data do exame.

---

## Receitas

Armazena prescrições médicas.

Campos principais:

* ID da receita;
* Paciente;
* Medicamento;
* Dosagem;
* Orientações.

---

# Consultas Principais

## Listar pacientes cadastrados

```sql
SELECT * FROM pacientes;
```

## Listar médicos cadastrados

```sql
SELECT * FROM medicos;
```

## Consultar exames realizados

```sql
SELECT * FROM exames;
```

## Consultar receitas médicas

```sql
SELECT * FROM receitas;
```

---

# Tecnologias Utilizadas

* Apache Cassandra;
* Docker;
* Cassandra Query Language (CQL);
* GitHub.

---

# Estrutura do Projeto

```
atividade-cassandra-clinica

│
├── README.md
│
└── scripts
    │
    ├── keyspace.cql
    │
    ├── tabelas.cql
    │
    └── inserts.cql
```

---

# Características do Cassandra Utilizadas

* Banco de dados NoSQL;
* Modelagem orientada a consultas;
* Alta disponibilidade;
* Escalabilidade horizontal;
* Armazenamento distribuído.

---

# Conclusão

O desenvolvimento deste projeto permitiu aplicar os conceitos de bancos de dados NoSQL utilizando o Apache Cassandra.

A solução proposta demonstra como um sistema de clínica médica pode organizar seus dados de forma eficiente, garantindo disponibilidade, desempenho e possibilidade de crescimento conforme a demanda.
