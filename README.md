# Atividade de Banco de Dados

Este repositório contém as atividades da disciplina de **Banco de Dados**, do curso de **Desenvolvimento Full-Stack** do **Instituto PROA**, em parceria com o **SENAC**. Cada atividade apresenta a modelagem de dados em formato **Entidade-Relacionamento (ER)** e uma breve descrição do sistema.  

---

## Atividade 1: O Hospital Fundamental

**Descrição:**  
Sistema para controlar consultas de um hospital, com cadastro de médicos (generalistas, especialistas ou residentes), pacientes, convênios e receitas médicas. Permite registrar consultas, especialidades, medicamentos e gerar relatórios ou visualização online.  

**Ferramenta utilizada:** BR Modelo  

**Modelagem ER:**
<img width="972" height="497" alt="hospital_1" src="https://github.com/user-attachments/assets/004221cd-5eb9-4139-af65-4ceefd350db1" />

---

## Atividade 2: Os Segredos do Hospital

**Descrição:**  
Expansão do modelo anterior, incluindo controle de internação de pacientes. Foram criadas novas entidades e relacionamentos, com definição de tipos de dados e integridade referencial, além de script SQL para criação do banco completo.Tudo sendo em Modelo lógico.  

**Ferramenta utilizada:** DB Design  

**Modelo Lógico**
<img width="1046" height="785" alt="hospital_modelo_logico" src="https://github.com/user-attachments/assets/f378380e-b5c0-4539-bc37-fa142631e3d5" />


**Script SQL:**  
O script de criação das tabelas está disponível na pasta `scripts`.  

Parte 1 - Script

<img width="708" height="721" alt="p1" src="https://github.com/user-attachments/assets/bd586a95-6867-4433-b9d3-42343ff672c5" />


Parte 2 - Script

<img width="781" height="763" alt="p2" src="https://github.com/user-attachments/assets/3c36adab-7b08-482b-bffa-d21296d46eae" />

As ferramentas utlizadas foram o dbdesigner e brmodelo

---

## Atividade 3: O Prisioneiro dos Dados  

**Descrição:**  
Esta atividade teve como objetivo o **povoamento do banco de dados hospitalar**, garantindo a inserção de dados essenciais para testes, validações e demonstrações de funcionamento do sistema.  

Foram elaborados **scripts SQL** responsáveis por preencher todas as tabelas e relacionamentos definidos no modelo anterior, assegurando a integridade dos dados e o correto vínculo entre as entidades do sistema hospitalar.  


**Dados Inseridos:** 
- 👨‍⚕️ **10 médicos** de diferentes especialidades (pediatria, clínica geral, gastroenterologia, dermatologia, entre outras).  
- 🧠 **7 especialidades médicas** distintas.  
- 🧍‍♂️ **15 pacientes** cadastrados.  
- 📅 **20 consultas** realizadas entre *01/01/2015* e *01/01/2022*, sendo 10 com receituário contendo dois ou mais medicamentos.  
- 🏥 **4 convênios médicos**, vinculados a pacientes e consultas.  
- 🛏️ **7 internações**, com diferentes **tipos de quarto** (apartamento, duplo e enfermaria).  
- 💉 **10 enfermeiros**, com cada internação associada a pelo menos dois deles.  


## 💾 Scripts SQL  

Os scripts de povoamento foram desenvolvidos para simular o funcionamento real do sistema, permitindo o teste das operações de inserção, consulta e relacionamento entre as tabelas.  

📂 **Exemplo ilustrativo:**  
```sql
-- Inserindo especialidades
INSERT INTO especialidade (id_especialidade, nome) VALUES (1, 'Clínica Geral');

-- Inserindo médicos
INSERT INTO medico (id_medico, nome, id_especialidade) VALUES (1, 'Dr. João Silva', 1);



> Novas atividades serão adicionadas neste README com suas respectivas modelagens ER e descrições.
