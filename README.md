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

📂 **Scripts de inserção de dados:**  
```sql

-- 1. Inserindo o povoamento de Especialidade, Convenio, Tipo_quarto
INSERT INTO Especialidade (id_especialidade, nome_especialidade) VALUES
(1, 'Pediatria'), (2, 'Clínica Geral'), (3, 'Gastrenterologia'), (4, 'Dermatologia'),
(5, 'Cardiologia'), (6, 'Ortopedia'), (7, 'Neurologia');

INSERT INTO Convenio (id_convenio, nome_convenio, cnpj, tempo_carencia) VALUES
(1, 'Saúde Total', '11.222.333/0001-44', '30 dias'),
(2, 'Bem Viver', '22.333.444/0001-55', '60 dias'),
(3, 'MedMais', '33.444.555/0001-66', '15 dias'),
(4, 'Vida Plena', '44.555.666/0001-77', '0 dias');

INSERT INTO Tipo_quarto (id_tipo_quarto, descricao, valor_diaria) VALUES
(1, 'Apartamento', 450.00),
(2, 'Quarto Duplo', 280.00),
(3, 'Enfermaria', 150.00);

-- 2. Inserindo o catálogo de Medicamentos
INSERT INTO Medicamentos (id_medicamento, nome_medicamento) VALUES
(1, 'Amoxicilina 500mg'), (2, 'Paracetamol 750mg'), (3, 'Ibuprofeno 600mg'),
(4, 'Dipirona 500mg'), (5, 'Omeprazol 20mg'), (6, 'Losartana 50mg'),
(7, 'Sinvastatina 20mg'), (8, 'Metformina 850mg'), (9, 'Prednisona 20mg'),
(10, 'AAS 100mg'), (11, 'Nimesulida 100mg'), (12, 'Loratadina 10mg'),
(13, 'Clonazepam 2mg'), (14, 'Fluoxetina 20mg'), (15, 'Torsilax');

-- 3. Inserindo o povoamento dos Médicos, Enfermeiros, Pacientes
INSERT INTO Medico (id_medico, nome_medico, crm, tipo_medico, id_especialidade) VALUES
(1, 'Dr. Carlos Andrade', 'SP12345', 'Titular', 2), (2, 'Dra. Beatriz Lima', 'SP54321', 'Titular', 1),
(3, 'Dr. Fernando Gomes', 'SP67890', 'Titular', 3), (4, 'Dra. Helena Souza', 'SP09876', 'Residente', 4),
(5, 'Dr. Ricardo Alves', 'SP11223', 'Titular', 5), (6, 'Dra. Patricia Costa', 'SP33445', 'Titular', 6),
(7, 'Dr. Marcos Ribeiro', 'SP55667', 'Residente', 2), (8, 'Dra. Vanessa Martins', 'SP77889', 'Titular', 7),
(9, 'Dr. Lucas Ferreira', 'SP99001', 'Titular', 1), (10, 'Dra. Julia Nogueira', 'SP10102', 'Titular', 3);

INSERT INTO Enfermeiro (id_enfermeiro, nome_enfermeiro, cpf, coren) VALUES
(1, 'Ana Silva', '111.111.111-11', 1001), (2, 'Bruno Santos', '222.222.222-22', 1002),
(3, 'Carla Dias', '333.333.333-33', 1003), (4, 'Daniel Oliveira', '444.444.444-44', 1004),
(5, 'Elisa Pereira', '555.555.555-55', 1005), (6, 'Fabio Rocha', '666.666.666-66', 1006),
(7, 'Gabriela Alves', '777.777.777-77', 1007), (8, 'Hugo Mendes', '888.888.888-88', 1008),
(9, 'Isis Costa', '999.999.999-99', 1009), (10, 'Jorge Lima', '123.456.789-00', 1010);

INSERT INTO Paciente (id_paciente, nome_paciente, cpf, rg, data_nascimento, id_convenio) VALUES
(1, 'Maria Oliveira', '101.101.101-11', '1010101', '1990-05-15', 1), (2, 'João Pereira', '102.102.102-22', '1010102', '1985-11-20', 1),
(3, 'Ana Clara', '103.103.103-33', '1010103', '2015-01-30', 2), (4, 'Lucas Martins', '104.104.104-44', '1010104', '1977-07-10', 3),
(5, 'Beatriz Almeida', '105.105.105-55', '1010105', '1999-03-25', 4), (6, 'Carlos Souza', '106.106.106-66', '1010106', '1982-09-05', NULL),
(7, 'Fernanda Lima', '107.107.107-77', '1010107', '2018-12-12', NULL), (8, 'Guilherme Costa', '108.108.108-88', '1010108', '1995-02-18', NULL),
(9, 'Helena Gomes', '109.109.109-99', '1010109', '1963-10-01', 1), (10, 'Igor Fernandes', '110.110.110-00', '1010110', '2001-08-08', NULL),
(11, 'Juliana Ribeiro', '111.111.111-12', '1010111', '1988-06-14', 2), (12, 'Leonardo Barros', '112.112.112-13', '1010112', '1970-04-22', NULL),
(13, 'Marcia Dias', '113.113.113-14', '1010113', '1992-11-03', NULL), (14, 'Nelson Pinto', '114.114.114-15', '1010114', '1955-07-28', 3),
(15, 'Olivia Neves', '115.115.115-16', '1010115', '2005-09-17', NULL);

-- 4. Inserindo os quartos
INSERT INTO Quarto (id_quarto, numero, id_tipo_quarto) VALUES
(1, 101, 1), (2, 102, 1), (3, 201, 2), (4, 202, 2), (5, 301, 3);

-- 5. Inserindo as Receitas, e Item_receita, Consulta
INSERT INTO Receita (id_receita, data_emissao) VALUES
(1, '2015-03-10'), (2, '2015-05-22'), (3, '2016-01-15'), (4, '2016-02-20'),
(5, '2017-07-07'), (6, '2018-09-14'), (7, '2019-11-01'), (8, '2020-03-30'),
(9, '2021-06-10'), (10, '2021-12-05');

INSERT INTO Item_Receita (id_item_receita, id_receita, id_medicamento, quantidade, instrucoes_de_uso) VALUES
(1, 1, 1, '1 caixa', '1 comp. 8/8h por 7 dias'), (2, 1, 2, '1 caixa', '1 comp. 6/6h se dor'),
(3, 2, 5, '2 caixas', '1 comp. em jejum por 30 dias'), (4, 2, 4, '1 caixa', '20 gotas se dor'),
(5, 3, 2, '2 caixas', '1 comp. 8/8h se febre'), (6, 3, 11, '1 caixa', '1 comp. 12/12h por 3 dias'),
(7, 3, 12, '1 frasco', '1 comp. 1x ao dia'), (8, 4, 6, '1 caixa', '1 comp. 1x ao dia'),
(9, 4, 10, '2 caixas', '1 comp. após almoço'), (10, 5, 9, '1 caixa', '1 comp. 1x ao dia por 5 dias'),
(11, 5, 3, '1 caixa', '1 comp. se dor forte'), (12, 6, 7, 'Uso contínuo', '1 comp. à noite'),
(13, 6, 8, 'Uso contínuo', '2 comp. 2x ao dia'), (14, 7, 13, '1 caixa', '1 comp. antes de dormir'),
(15, 7, 14, '2 caixas', '1 comp. pela manhã'), (16, 8, 1, '2 caixas', '1 comp. 8/8h por 10 dias'),
(17, 8, 11, '1 caixa', '1 comp. 12/12h por 5 dias'), (18, 9, 15, '1 caixa', '1 comp. 6/6h por 3 dias'),
(19, 9, 3, '1 caixa', '1 comp. 8/8h se dor'), (20, 10, 5, '1 caixa', '1 comp. em jejum'),
(21, 10, 4, '1 frasco', '30 gotas se dor ou febre'), (22, 10, 2, '1 caixa', '1 comp. 8/8h');

INSERT INTO Consulta (id_consulta, data_realizacao, hora_realizacao, valor_consulta, id_medico, id_paciente, id_receita) VALUES
(1, '2015-03-10', '10:00:00', 300.00, 1, 1, 1), (2, '2015-05-22', '14:30:00', 300.00, 3, 2, 2),
(3, '2016-01-15', '09:00:00', 250.00, 2, 3, 3), (4, '2016-02-20', '11:15:00', 350.00, 5, 4, 4),
(5, '2017-07-07', '16:00:00', 400.00, 6, 6, 5), (6, '2018-09-14', '08:45:00', 350.00, 5, 9, 6),
(7, '2019-11-01', '13:00:00', 300.00, 7, 8, 7), (8, '2020-03-30', '15:20:00', 250.00, 2, 7, 8),
(9, '2021-06-10', '10:30:00', 400.00, 6, 10, 9), (10, '2021-12-05', '17:00:00', 300.00, 3, 1, 10),
(11, '2015-06-11', '09:15:00', 300.00, 1, 5, NULL), (12, '2016-03-01', '14:00:00', 250.00, 2, 11, NULL),
(13, '2017-08-18', '11:00:00', 350.00, 4, 12, NULL), (14, '2018-10-25', '16:30:00', 300.00, 1, 13, NULL),
(15, '2019-12-10', '08:00:00', 400.00, 6, 14, NULL), (16, '2020-04-05', '13:45:00', 300.00, 7, 15, NULL),
(17, '2021-07-12', '10:00:00', 350.00, 4, 3, NULL), (18, '2021-09-01', '14:30:00', 300.00, 1, 6, NULL),
(19, '2022-01-05', '09:30:00', 300.00, 3, 8, NULL), (20, '2022-01-10', '11:00:00', 250.00, 2, 1, NULL);

-- 6. Inserindo o evento de Internação
INSERT INTO Internacao (id_internacao, data_entrada, data_prev_alta, data_alta, procedimento, id_medico, id_paciente, id_quarto) VALUES
(1, '2015-07-01', '2015-07-05', '2015-07-06', 'Cirurgia Apendicite', 3, 2, 1),
(2, '2016-04-10', '2016-04-12', '2016-04-12', 'Observação Pediátrica', 2, 3, 5),
(3, '2017-09-20', '2017-09-30', '2017-09-30', 'Cirurgia Ortopédica', 6, 6, 2),
(4, '2018-11-15', '2018-11-20', '2018-11-21', 'Tratamento Cardiovascular', 5, 4, 1),
(5, '2019-05-01', '2019-05-03', '2019-05-03', 'Remoção de Cisto', 4, 8, 3),
(6, '2020-08-10', '2020-08-15', '2020-08-15', 'Tratamento Gastro', 3, 2, 2),
(7, '2021-10-01', '2021-10-10', '2021-10-09', 'Angioplastia', 5, 4, 1);

-- 7. Povoamento das relações N:N
INSERT INTO Internacao_Enfermeiro (id_internacao, id_enfermeiro) VALUES
(1, 1), (1, 2), (2, 3), (2, 4), (3, 5), (3, 6), (3, 1),
(4, 7), (4, 8), (5, 9), (5, 10), (6, 1), (6, 3), (7, 2), (7, 4);


> Novas atividades serão adicionadas neste README com suas respectivas modelagens ER e descrições.
