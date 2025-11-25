🐾 Banco de Dados – Clínica Veterinária

Este repositório contém o banco de dados relacional de uma clínica veterinária, desenvolvido para gerenciar proprietários, animais, consultas, procedimentos, medicamentos e funcionários.

🎯 Objetivo do Projeto

O objetivo deste projeto é fornecer uma base de dados organizada para:

Gerenciar proprietários (pessoa física e jurídica)

Registrar animais e seu histórico

Controlar consultas veterinárias

Registrar procedimentos realizados

Controlar medicamentos aplicados

Gerenciar funcionários e veterinários

🛠️ Tecnologias Utilizadas

SGBD: MySQL

Linguagem: SQL

Paradigma: Banco de dados relacional

🗄️ Estrutura do Banco de Dados

O banco de dados é composto pelas seguintes tabelas:

🧍 Proprietario

Armazena os dados dos proprietários:

id_proprietario (PK)

endereco

telefone

🧍 Pessoa_fisica

Representa os proprietários do tipo pessoa física:

cpf (PK)

id_proprietario (FK, UNIQUE)

nome

data_nascimento

🏢 Pessoa_juridica

Representa os proprietários do tipo pessoa jurídica:

cnpj (PK)

id_proprietario (FK, UNIQUE)

razao_social

🐶 Animal

Armazena os dados dos animais:

id_animal

id_proprietario (FK)

nome

data_nascimento

antecedentes

🩺 Consulta

Registra as consultas feitas:

id_consulta

id_animal (FK)

data_hora

tipo_consulta

diagnostico

observacoes

💉 Procedimentos

Representa procedimentos realizados:

id_procedimento

id_animal (FK)

nome_procedimento

custo

duracao

💊 Medicamentos

Controla os medicamentos utilizados:

id_medicamento

id_procedimento (FK)

descricao

tipo

quantidade

👥 Funcionarios

Armazena os dados dos funcionários:

id_funcionario

cpf

nome

telefone

cargo

endereco

👨‍⚕️ Veterinario

Tabela específica dos veterinários:

crm (PK)

id_funcionario (FK, UNIQUE)

🔗 Relacionamentos

Um proprietário pode ter vários animais

Cada animal pode ter várias consultas

Cada animal pode participar de vários procedimentos

Cada procedimento pode usar vários medicamentos

Um funcionário pode ser um veterinário

🚀 Como executar o banco
1. Criar o banco
CREATE DATABASE clinica_veterinaria;
USE clinica_veterinaria;

📌 Importar o script

Execute o arquivo com o SQL do banco (o script que você montou) em:

MySQL Workbench

phpMyAdmin

DBeaver

SQL Fiddle

🧪 Exemplos de consultas
Consultar animais e seus donos
SELECT a.nome AS nome_animal, pf.nome AS nome_dono
FROM Animal a
JOIN Proprietario p ON a.id_proprietario = p.id_proprietario
LEFT JOIN Pessoa_fisica pf ON p.id_proprietario = pf.id_proprietario;

Listar consultas de um animal
SELECT c.data_hora, c.tipo_consulta, c.diagnostico
FROM Consulta c
WHERE c.id_animal = 1;

📁 Estrutura Sugerida
📦 clinica-veterinaria-db/
 ┣ 📂 scripts/
 ┃ ┗ 📜 banco.sql
 ┣ 📂 diagramas/
 ┃ ┗ 📸 modelo_er.png
 ┗ 📜 README.md
