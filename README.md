# exercicio-bd-

create database `bd_exercicio`;

use `bd_exercicio`;

CREATE TABLE `bd_exercicio`.`tb_funcionario` (
`func_codigo` INT NOT NULL PRIMARY KEY,
`func_nome` VARCHAR(60) NULL,
`func_cpf` VARCHAR(13) NULL,
`forn_end` VARCHAR(90) NULL,
`forn_salario` NUMERIC,
`ger_depto_cod` INT,
`trab_depto_cod` INT,
`proj_cod` INT
);

CREATE TABLE `bd_exercicio`.`tb_departamento` (
`depto_codigo` INT NOT NULL PRIMARY KEY,
`depto_nome` VARCHAR(60) NULL,
`local_cod` INT
);

 CREATE TABLE `bd_exercicio`. `tb_projeto` (
 `proj_codigo` INT NOT NULL PRIMARY KEY,
 `proj_numero` INT,
 `depto_cod` INT,
 `local_cod` INT
 );  
 
 CREATE TABLE `bd_exercicio`. `tb_local` (
 `local_codigo` INT NOT NULL PRIMARY KEY,
`local_desc` VARCHAR(60) NULL
);

ALTER TABLE `bd_exercicio`.`tb_funcionario`
ADD INDEX `fk_ger_depto_cod_idx` (`ger_depto_cod` ASC);

ALTER TABLE `bd_exercicio`.`tb_funcionario`
ADD CONSTRAINT `fk_ger_depto_cod`
    FOREIGN KEY (`ger_depto_cod`)
REFERENCES `bd_exercicio`.`tb_departamento` (`depto_codigo`);

ALTER TABLE `bd_exercicio`.`tb_funcionario`
ADD INDEX `fk_trab_depto_cod_idx` (`trab_depto_cod` ASC);

ALTER TABLE `bd_exercicio`.`tb_funcionario`
ADD CONSTRAINT `fk_trab_depto_cod`
    FOREIGN KEY (`trab_depto_cod`)
    REFERENCES `bd_exercicio`. `tb_departamento` (`depto_codigo`);

ALTER TABLE `bd_exercicio`. `tb_funcionario`
ADD INDEX `fk_proj_cod_idx` (`proj_cod` ASC);

ALTER TABLE bd_exercicio. tb_funcionario
ADD CONSTRAINT `fk_proj_cod`
    FOREIGN KEY (`proj_cod`)
    REFERENCES `bd_exercicio`.`tb_projeto` (`proj_codigo`);
 
ALTER TABLE `bd_exercicio`. `tb_departamento`
ADD INDEX `fk_local_depto_cod_idx` (`local_cod` ASC);

ALTER TABLE `bd_exercicio`. `tb_departamento`
ADD CONSTRAINT `fk_depto_local_cod`
    FOREIGN KEY (`local_cod`)
    REFERENCES `bd_exercicio`. `tb_local` (`local_codigo`);

ALTER TABLE `bd_exercicio`. `tb_projeto`
ADD INDEX `fk_local_proj_cod_idx` (`local_cod` ASC);

ALTER TABLE `bd_exercicio`. `tb_projeto`
ADD CONSTRAINT `fk_proj_local_cod`
    FOREIGN KEY (`local_cod`)
    REFERENCES `bd_exercicio`. `tb_local` (`local_codigo`);

INSERT INTO `bd_exercicio`.`tb_local` (local_codigo, local_desc) VALUES (1, 'São Paulo'),
(2, 'Rio de Janeiro'),
(3, 'Belo Horizonte'),
(4, 'Salvador'),
(5, 'Fortaleza'),
(6, 'Curitiba'),
(7, 'Manaus'),
(8, 'Recife'),
(9, 'Porto Alegre'),
(10, 'Belém'),
(11, 'Goiânia'),
(12, 'São Luís'),
(13, 'Maceió'),
(14, 'Natal'),
(15, 'Teresina'),
(16, 'Campo Grande'),
(17, 'João Pessoa'),
(18, 'Aracaju'),
(19, 'Cuiabá'),
(20, 'Rio Branco'),
(21, 'Palmas'),
(22, 'Boa Vista'),
(23, 'Macapá'),
(24, 'Porto Velho'),
(25, 'Vitória'),
(26, 'Florianópolis'),
(27, 'Belo Horizonte'),
(28, 'São Vicente'),
(29, 'Niterói'),
(30, 'Santos'),
(31, 'Diadema'),
(32, 'São Bernardo do Campo'),
(33, 'Osasco'),
(34, 'Guarulhos'),
(35, 'Campinas'),
(36, 'São José dos Campos'),
(37, 'Sorocaba'),
(38, 'Ribeirão Preto'),
(39, 'Bauru'),
(40, 'Jundiaí'),
(41, 'Piracicaba'),
(42, 'Barueri'),
(43, 'São Carlos'),
(44, 'Londrina'),
(45, 'Maringá'),
(46, 'Joinville'),
(47, 'Ponta Grossa'),
(48, 'Caxias do Sul'),
(49, 'Santa Maria'),
(50, 'Taubaté');

INSERT INTO `bd_exercicio`.`tb_departamento`(depto_codigo, depto_nome, local_cod) VALUES
(1, 'TI', 1),
(2, 'RH', 2),
(3, 'ADM', 3),
(4, 'TI', 1),
(5, 'RH', 2),
(6, 'ADM', 3),
(7, 'TI', 1),
(8, 'RH', 2),
(9, 'ADM', 3),
(10, 'TI', 1),
(11, 'RH', 2),
(12, 'ADM', 3),
(13, 'TI', 1),
(14, 'RH', 2),
(15, 'ADM', 3),
(16, 'TI', 1),
(17, 'RH', 2),
(18, 'ADM', 3),
(19, 'TI', 1),
(20, 'RH', 2),
(21, 'ADM', 3),
(22, 'TI', 1),
(23, 'RH', 2),
(24, 'ADM', 3),
(25, 'TI', 1),
(26, 'RH', 2),
(27, 'ADM', 3),
(28, 'TI', 1),
(29, 'RH', 2),
(30, 'ADM', 3),
(31, 'TI', 1),
(32, 'RH', 2),
(33, 'ADM', 3),
(34, 'TI', 1),
(35, 'RH', 2),
(36, 'ADM', 3),
(37, 'TI', 1),
(38, 'RH', 2),
(39, 'ADM', 3),
(40, 'TI', 1),
(41, 'RH', 2),
(42, 'ADM', 3),
(43, 'TI', 1),
(44, 'RH', 2),
(45, 'ADM', 3),
(46, 'TI', 1),
(47, 'RH', 2),
(48, 'ADM', 3),
(49, 'TI', 1),
(50, 'RH', 2);

INSERT INTO `bd_exercicio`.`tb_projeto` (proj_codigo, proj_numero, depto_cod, local_cod) VALUES
(1, 11, 1, 1),
(2, 22, 1, 1),
(3, 33, 1, 1),
(4, 44, 1, 1),
(5, 55, 1, 1),
(6, 66, 1, 1),
(7, 77, 1, 1),
(8, 88, 1, 1),
(9, 99, 1, 1),
(10, 100, 1, 1),
(11, 111, 2, 2),
(12, 222, 2, 2),
(13, 333, 2, 2),
(14, 444, 2, 2),
(15, 555, 2, 2),
(16, 666, 2, 2),
(17, 777, 2, 2),
(18, 888, 2, 2),
(19, 999, 2, 2),
(20, 1000, 2, 2),
(21, 1111, 3, 3),
(22, 2222, 3, 3),
(23, 3333, 3, 3),
(24, 4444, 3, 3),
(25, 5555, 3, 3),
(26, 6666, 3, 3),
(27, 7777, 3, 3),
(28, 8888, 3, 3),
(29, 9999, 3, 3),
(30, 10000, 3, 3),
(31, 11111, 1, 1),
(32, 22222, 1, 1),
(33, 33333, 1, 1),
(34, 44444, 1, 1),
(35, 55555, 1, 1),
(36, 66666, 1, 1),
(37, 77777, 1, 1),
(38, 88888, 1, 1),
(39, 99999, 1, 1),
(40, 100000, 1, 1),
(41, 111111, 2, 2),
(42, 222222, 2, 2),
(43, 333333, 2, 2),
(44, 444444, 2, 2),
(45, 555555, 2, 2),
(46, 666666, 2, 2),
(47, 777777, 2, 2),
(48, 888888, 2, 2),
(49, 999999, 2, 2),
(50, 1000000, 2, 2);

INSERT INTO `bd_exercicio`.`tb_funcionario` (func_codigo, func_nome, func_cpf, forn_end, forn_salario, ger_depto_cod, proj_cod) VALUES
(1, 'Jose Silva', '12312312344', 'Endereco 1', 2000, null, 1, 1),
(2, 'Maria Oliveira', '23423423455', 'Endereco 2', 2500,null, 1, 1),
(3, 'Carlos Pereira', '34534534566', 'Endereco 3', 3000,null, 1, 1),
(4, 'Ana Costa', '45645645677', 'Endereco 4', 2200,null, 1, 1),
(5, 'Lucas Mendes', '56756756788', 'Endereco 5', 1800,null, 1, 1),
(6, 'Juliana Santos', '67867867899', 'Endereco 6', 2600,null, 1, 1),
(7, 'Felipe Almeida', '78978978900', 'Endereco 7', 2900,null, 1, 1),
(8, 'Fernanda Lima', '89089089011', 'Endereco 8', 3100,null, 1, 1),
(9, 'Roberto Souza', '90190190122', 'Endereco 9', 2300,null, 1, 1),
(10, 'Patricia Ramos', '01201201233', 'Endereco 10', 2700,null, 1, 1),
(11, 'Marcio Ribeiro', '12345678901', 'Endereco 11', 3000,null, 1, 1),
(12, 'Tatiane Martins', '23456789012', 'Endereco 12', 2500,null, 1, 1),
(13, 'Gustavo Nascimento', '34567890123', 'Endereco 13', 3100,null, 1, 1),
(14, 'Aline Teixeira', '45678901234', 'Endereco 14', 2200,null, 1, 1),
(15, 'Renato Ferreira', '56789012345', 'Endereco 15', 2400,null, 1, 1),
(16, 'Sofia Carvalho', '67890123456', 'Endereco 16', 2300,null, 1, 1),
(17, 'Ricardo Andrade', '78901234567', 'Endereco 17', 2500,null, 1, 1),
(18, 'Camila Santos', '89012345678', 'Endereco 18', 2800,null, 1, 1),
(19, 'Daniela Costa', '90123456789', 'Endereco 19', 3000,null, 1, 1),
(20, 'Thiago Lopes', '01234567890', 'Endereco 20', 2000,null, 1, 1),
(21, 'Fabio Moreira', '12312312345', 'Endereco 21', 2100,null, 1, 1),
(22, 'Larissa Barros', '23423423456', 'Endereco 22', 2400,null, 1, 1),
(23, 'Diego Almeida', '34534534567', 'Endereco 23', 2900,null, 1, 1),
(24, 'Nathalia Pires', '45645645678', 'Endereco 24', 2600,null, 1, 1),
(25, 'Vinicius Rocha', '56756756789', 'Endereco 25', 2800,null, 1, 1),
(26, 'Leticia Cunha', '67867867890', 'Endereco 26', 3000,null, 1, 1),
(27, 'Bruno Dias', '78978978901', 'Endereco 27', 2300,null, 1, 1),
(28, 'Bianca Vieira', '89089089012', 'Endereco 28', 2200,null, 1, 1),
(29, 'Jorge Martins', '90190190123', 'Endereco 29', 2700,null, 1, 1),
(30, 'Cecilia Fernandes', '01201201234', 'Endereco 30',null, 3100, 1, 1),
(31, 'Fábio Gomes', '12345678910', 'Endereco 31', 2900,null, 1, 1),
(32, 'Claudia Pinto', '23456789021', 'Endereco 32', 2500,null, 1, 1),
(33, 'Henrique Silva', '34567890132', 'Endereco 33', 2600,null, 1, 1),
(34, 'Patrícia Alves', '45678901243', 'Endereco 34', 2400,null, 1, 1),
(35, 'Alberto Lima', '56789012354', 'Endereco 35', 2200,null, 1, 1),
(36, 'Mariana Sampaio', '67890123465', 'Endereco 36', 3000,null, 1, 1),
(37, 'Eduardo Santos', '78901234576', 'Endereco 37', 2700,null, 1, 1),
(38, 'Isabela Costa', '89012345687', 'Endereco 38', 2000,null, 1, 1),
(39, 'Rodrigo Lima', '90123456798', 'Endereco 39', 2300,null, 1, 1),
(40, 'André Martins', '01234567809', 'Endereco 40', 2400,null, 1, 1),
(41, 'Patricia Souza', '12312312345', 'Endereco 41', 2600,null, 1, 1),
(42, 'Cristiano Azevedo', '23423423456', 'Endereco 42', 2900,null, 1, 1),
(43, 'Carmen da Silva', '34534534567', 'Endereco 43', 3000,null, 1, 1),
(44, 'Sergio Mello', '45645645678', 'Endereco 44', 2200,null, 1, 1),
(45, 'Ana Paula', '56756756789', 'Endereco 45', 1800,null, 1, 1),
(46, 'João Ribeiro', '67867867890', 'Endereco 46', 2500,null, 1, 1),
(47, 'Tânia Ferreira', '78978978901', 'Endereco 47', 3100,null, 1, 1),
(48, 'Leandro Martins', '89089089012', 'Endereco 48', 2400,null, 1, 1),
(49, 'Paula Nascimento', '90190190123', 'Endereco 49', 2000,null, 1, 1),
(50, 'Felipe Mendes', '01201201234', 'Endereco 50', 2700,null, 1, 1);

INSERT INTO `bd_exercicio`.`tb_funcionario` (func_codigo, func_nome, func_cpf, forn_end, forn_salario, ger_depto_cod, trab_depto_cod, proj_cod) VALUES
(1, 'Ana Silva', '12345678944', 'Endereco 1', 2000, 2, 2, 2),
(2, 'João Pereira', '98765432100', 'Endereco 2', 2200, 2, 2, 2),
(3, 'Maria Oliveira', '11223344556', 'Endereco 3', 2500, 2, 2, 2),
(4, 'Carlos Santos', '22334455667', 'Endereco 4', 2100, 2, 2, 2),
(5, 'Juliana Costa', '33445566778', 'Endereco 5', 2300, 2, 2, 2),
(6, 'Fernanda Lima', '44556677889', 'Endereco 6', 2400, 2, 2, 2),
(7, 'Ricardo Gomes', '55667788990', 'Endereco 7', 2600, 2, 2, 2),
(8, 'Tatiane Rocha', '66778899001', 'Endereco 8', 2700, 2, 2, 2),
(9, 'Roberto Alves', '77889900112', 'Endereco 9', 2800, 2, 2, 2),
(10, 'Renata Martins', '88990011223', 'Endereco 10', 2900, 2, 2, 2),
(11, 'Eduardo Ferreira', '99001122334', 'Endereco 11', 3000, 2, 2, 2),
(12, 'Patrícia Mendes', '10111213141', 'Endereco 12', 3100, 2, 2, 2),
(13, 'Leonardo Pires', '12131415161', 'Endereco 13', 3200, 2, 2, 2),
(14, 'Camila Sousa', '13141516171', 'Endereco 14', 3300, 2, 2, 2),
(15, 'Mariana Lima', '14151617181', 'Endereco 15', 3400, 2, 2, 2),
(16, 'Felipe Cardoso', '15161718191', 'Endereco 16', 3500, 2, 2, 2),
(17, 'Tatiane Martins', '16171819202', 'Endereco 17', 3600, 2, 2, 2),
(18, 'André Alves', '17181920211', 'Endereco 18', 3700, 2, 2, 2),
(19, 'Sofia Dias', '18192021222', 'Endereco 19', 3800, 2, 2, 2),
(20, 'Lucas Nascimento', '19202122233', 'Endereco 20', 3900, 2, 2, 2),
(21, 'Aline Araújo', '20212223344', 'Endereco 21', 4000, 2, 2, 2),
(22, 'Gustavo Silva', '21222324455', 'Endereco 22', 4100, 2, 2, 2),
(23, 'Ana Clara', '22232425566', 'Endereco 23', 4200, 2, 2, 2),
(24, 'Rafael Mendes', '23242526677', 'Endereco 24', 4300, 2, 2, 2),
(25, 'Bianca Oliveira', '24252627788', 'Endereco 25', 4400, 2, 2, 2),
(26, 'Samuel Costa', '25262728899', 'Endereco 26', 4500, 2, 2, 2),
(27, 'Júlia Almeida', '26272829900', 'Endereco 27', 4600, 2, 2, 2),
(28, 'Vinícius Soares', '27282930011', 'Endereco 28', 4700, 2, 2, 2),
(29, 'Lívia Barreto', '28293031122', 'Endereco 29', 4800, 2, 2, 2),
(30, 'João Paulo', '29293132233', 'Endereco 30', 4900, 2, 2, 2),
(31, 'Tainá Rocha', '30313233344', 'Endereco 31', 5000, 2, 2, 2),
(32, 'Marcos Assunção', '31323334455', 'Endereco 32', 5100, 2, 2, 2),
(33, 'Eliane Fernandes', '32333445566', 'Endereco 33', 5200, 2, 2, 2),
(34, 'Sérgio Lima', '33343556677', 'Endereco 34', 5300, 2, 2, 2),
(35, 'Tatiane Lima', '34353667788', 'Endereco 35', 5400, 2, 2, 2),
(36, 'César Rodrigues', '35363778899', 'Endereco 36', 5500, 2, 2, 2),
(37, 'Jessica Lima', '36373879900', 'Endereco 37', 5600, 2, 2, 2),
(38, 'Guilherme Costa', '37383980011', 'Endereco 38', 5700, 2, 2, 2),
(39, 'Fernanda Moreira', '38394081122', 'Endereco 39', 5800, 2, 2, 2),
(40, 'Tiago Almeida', '39404182233', 'Endereco 40', 5900, 2, 2, 2),
(41, 'Mariana Martins', '40414283344', 'Endereco 41', 6000, 2, 2, 2),
(42, 'Henrique Pires', '41424384455', 'Endereco 42', 6100, 2, 2, 2),
(43, 'Bruna Silva', '42434485566', 'Endereco 43', 6200, 2, 2, 2),
(44, 'Jorge Almeida', '43444586677', 'Endereco 44', 6300, 2, 2, 2),
(45, 'Claudia Santos', '44454687788', 'Endereco 45', 6400, 2, 2, 2),
(46, 'Leandro Ferreira', '45464788899', 'Endereco 46', 6500, 2, 2, 2),
(47, 'Luan Silva', '46474889900', 'Endereco 47', 6600, 2, 2, 2),
(48, 'Amanda Ramos', '47484990011', 'Endereco 48', 6700, 2, 2, 2),
(49, 'Patrícia Martins', '48495091122', 'Endereco 49', 6800, 2, 2, 2),
(50, 'Carlos Alberto', '49505192233', 'Endereco 50', 6900, 2, 2, 2);


