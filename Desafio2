-- Criação do Banco de Dados
CREATE DATABASE IF NOT EXISTS HospitalDB;

-- Usar o Banco de Dados
USE HospitalDB;

-- Criação das Tabelas
CREATE TABLE IF NOT EXISTS Hospital (
    HospitalID INT AUTO_INCREMENT PRIMARY KEY,
    Nome VARCHAR(255),
    CNPJ VARCHAR(14),
    MedicoChefeID INT
);

CREATE TABLE IF NOT EXISTS Medico (
    MedicoID INT AUTO_INCREMENT PRIMARY KEY,
    CRM VARCHAR(10),
    Especialidade VARCHAR(255),
    Nome VARCHAR(255),
    EnderecoRua VARCHAR(255),
    EnderecoNumero INT,
    EnderecoBairro VARCHAR(255)
);

CREATE TABLE IF NOT EXISTS Paciente (
    PacienteID INT AUTO_INCREMENT PRIMARY KEY,
    NumeroProntuario INT,
    Nome VARCHAR(255),
    Telefones VARCHAR(255),
    FichaMedica TEXT
);

CREATE TABLE IF NOT EXISTS Exame (
    ExameID INT AUTO_INCREMENT PRIMARY KEY,
    Numero INT,
    Nome VARCHAR(255),
    Descricao TEXT,
    Preparo TEXT
);

CREATE TABLE IF NOT EXISTS Consulta (
    ConsultaID INT AUTO_INCREMENT PRIMARY KEY,
    Data DATE,
    MedicoID INT,
    PacienteID INT
);

CREATE TABLE IF NOT EXISTS ConsultaExame (
    ConsultaID INT,
    ExameID INT
);

CREATE TABLE IF NOT EXISTS MedicoPaciente (
    MedicoID INT,
    PacienteID INT
);

-- Inserir dados nas tabelas
INSERT INTO Hospital (Nome, CNPJ, MedicoChefeID) VALUES ('Hospital A', '12345678901', 1);
INSERT INTO Medico (CRM, Especialidade, Nome, EnderecoRua, EnderecoNumero, EnderecoBairro) VALUES ('12345', 'Cardiologia', 'Dr. Smith', 'Rua Principal', 123, 'Bairro Central');
INSERT INTO Paciente (NumeroProntuario, Nome, Telefones, FichaMedica) VALUES (1001, 'Alice', '123-456-7890', 'Hipertensão');
INSERT INTO Exame (Numero, Nome, Descricao, Preparo) VALUES (5001, 'Exame de Sangue', 'Análise de sangue completo', 'Jejum de 12 horas');

-- Inserir dados nas tabelas de relacionamento
INSERT INTO Consulta (Data, MedicoID, PacienteID) VALUES ('2023-10-15', 1, 1);
INSERT INTO ConsultaExame (ConsultaID, ExameID) VALUES (1, 1);
INSERT INTO MedicoPaciente (MedicoID, PacienteID) VALUES (1, 1);

-- Consultas
-- Seleção de dados de uma tabela
SELECT * FROM Hospital;

-- Utilizar funções de agregação
SELECT COUNT(*) AS TotalHospitais FROM Hospital;
SELECT AVG(NumeroProntuario) AS MediaProntuario FROM Paciente;

-- Seleção condicional com uma tabela
SELECT * FROM Paciente WHERE Nome = 'Alice';

-- Seleção condicional com mais de uma tabela (utilizando JOIN)
SELECT Hospital.Nome, Medico.Nome
FROM Hospital
INNER JOIN Medico ON Hospital.MedicoChefeID = Medico.MedicoID;

-- Manipulação de dados
-- Edição de dados simples
UPDATE Paciente SET Telefones = '987-654-3210' WHERE Nome = 'Alice';

-- Deleção de dados
DELETE FROM Exame WHERE ExameID = 1;

-- Deleção condicional
DELETE FROM Consulta WHERE Data < '2023-10-15';
