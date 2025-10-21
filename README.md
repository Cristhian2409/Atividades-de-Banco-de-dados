# Atividade de Banco de Dados

Este repositório contém as atividades da disciplina de **Banco de Dados**, do curso de **Desenvolvimento Full-Stack** do **Instituto PROA**, em parceria com o **SENAC**. Cada atividade apresenta a modelagem de dados em formato **Entidade-Relacionamento (ER)** e uma breve descrição do contexto de cada sistema.  

---

## Atividade 1: O Hospital Fundamental

**Descrição:**  
Um pequeno hospital local busca desenvolver um novo sistema que atenda melhor às suas necessidades. Atualmente, parte da operação ainda se apoia em planilhas e arquivos antigos, mas espera-se que esses dados sejam transferidos para o novo sistema assim que ele estiver funcional.  

O hospital necessita de um sistema para sua área clínica que ajude a controlar consultas realizadas. Os médicos podem ser generalistas, especialistas ou residentes e têm seus dados pessoais cadastrados em planilhas digitais. Cada médico pode ter uma ou mais especialidades, como pediatria, clínica geral, gastroenterologia e dermatologia. Alguns registros antigos ainda estão em formulário de papel, mas será necessário incluir esses dados no novo sistema.  

Os pacientes também precisam de cadastro, contendo dados pessoais (nome, data de nascimento, endereço, telefone e e-mail), documentos (CPF e RG) e convênio. Para cada convênio, são registrados nome, CNPJ e tempo de carência.  

As consultas têm registro de data e hora, médico responsável, paciente, valor da consulta ou nome do convênio com número da carteira, e a especialidade buscada pelo paciente. Também é necessário informatizar a receita do médico, registrando medicamentos, quantidade e instruções de uso, permitindo geração de relatórios ou visualização online.  

**Ferramenta utilizada:** BR Modelo  

**Modelagem ER:**
![ER - O Hospital Fundamental](caminho/para/imagem1.png)  

---

## Atividade 2: Os Segredos do Hospital

**Descrição:**  
Após a primeira versão do projeto de banco de dados para o sistema hospitalar, notou-se a necessidade de expansão das funcionalidades, incluindo o controle de internação de pacientes.  

Nesta etapa, o Modelo ER da atividade anterior foi expandido, criando-se novas entidades e relacionamentos, definindo tipos de dados e integridade referencial para cada tabela. Além disso, foi desenvolvido um **script SQL** para criação do banco de dados completo, incluindo tabelas, colunas, chaves primárias e estrangeiras.  

**Ferramenta utilizada:** DB Design  

**Modelagem ER:**
![ER - Os Segredos do Hospital](caminho/para/imagem2.png)  

**Script SQL:**  
O script de criação de tabelas está disponível na pasta `scripts` do repositório, pronto para ser executado em MySQL.  

---

> **Observação:** A cada nova atividade da disciplina, este README será atualizado com a imagem da modelagem ER e sua respectiva descrição.
