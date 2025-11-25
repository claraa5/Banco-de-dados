CREATE TABLE Proprietario (
    id_proprietario INT AUTO_INCREMENT PRIMARY KEY,
    endereco VARCHAR(100),
    telefone VARCHAR(20)
);

CREATE TABLE Pessoa_fisica (
    cpf VARCHAR(11) PRIMARY KEY,
    id_proprietario INT UNIQUE,
    nome VARCHAR(100),
    data_nascimento DATE,

    FOREIGN KEY (id_proprietario) REFERENCES Proprietario(id_proprietario)
);

CREATE TABLE Pessoa_juridica (
    cnpj VARCHAR(14) PRIMARY KEY,
    id_proprietario INT UNIQUE,
    razao_social VARCHAR(100),

    FOREIGN KEY (id_proprietario) REFERENCES Proprietario(id_proprietario)
);

CREATE TABLE Animal (
    id_animal INT AUTO_INCREMENT PRIMARY KEY,
    id_proprietario INT,
    nome VARCHAR(100),
    data_nascimento DATE,
    antecedentes VARCHAR(200),

    FOREIGN KEY (id_proprietario) REFERENCES Proprietario(id_proprietario)
);

CREATE TABLE Procedimentos (
    id_procedimento INT AUTO_INCREMENT PRIMARY KEY,
    id_animal INT,
    nome_procedimento VARCHAR(200),
    custo DECIMAL(10,2),
    duracao TIME,

    FOREIGN KEY (id_animal) REFERENCES Animal(id_animal)
);

CREATE TABLE Consulta (
    id_consulta INT AUTO_INCREMENT PRIMARY KEY,
    id_animal INT,
    data_hora DATETIME,
    tipo_consulta VARCHAR(100),
    diagnostico VARCHAR(200),
    observacoes TEXT,

    FOREIGN KEY (id_animal) REFERENCES Animal(id_animal)
);

CREATE TABLE Medicamentos (
    id_medicamento INT AUTO_INCREMENT PRIMARY KEY,
    id_procedimento INT,
    descricao VARCHAR(100),
    tipo VARCHAR(50),
    quantidade INT,

    FOREIGN KEY (id_procedimento) REFERENCES Procedimentos(id_procedimento)
);

CREATE TABLE Funcionarios (
    id_funcionario INT AUTO_INCREMENT PRIMARY KEY,
    cpf VARCHAR(11) UNIQUE,
    nome VARCHAR(100),
    telefone VARCHAR(20),
    cargo VARCHAR(100),
    endereco VARCHAR(100)
);

CREATE TABLE Veterinario (
    crm VARCHAR(20) PRIMARY KEY,
    id_funcionario INT UNIQUE,

    FOREIGN KEY (id_funcionario) REFERENCES Funcionarios(id_funcionario)
);
