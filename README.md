# BD-BIBLIOTECA
## Descrição

Você foi designado para criar um sistema de biblioteca. Aqui estão os detalhes adicionais:

## TABELAS:
/*Inicio criacao tabelas*/

create table autores (
    id int primary key auto_increment,
    nome varchar(100) not null,
    data_nascimento date not null,
    nacionalidade varchar(100)
);

create table editoras (
    id int primary key auto_increment,
    nome varchar(100) not null,
    endereco varchar(100)
);

create table livros (
    id int primary key auto_increment,
    titulo varchar(100) not null,
    isbn varchar(50),
    ano_publicacao int,
    estoque int not null,
    autores_id int,
    editoras_id int,
    foreign key (autores_id) references autores(id),
    foreign key (editoras_id) references editoras(id)
);

create table clientes (
    id int primary key auto_increment,
    nome varchar(100) not null,
    email varchar(100) not null,
    cpf varchar(100) not null
);

create table emprestimos (
    id int primary key auto_increment,
    livro_id int not null,
    cliente_id int not null,
    data_emprestimo date not null,
    data_devolucao date not null,
    status varchar(20),
    foreign key (livro_id) references livros(id),
    foreign key (cliente_id) references clientes(id)
);

/*Fim criacao tabelas*/
		
## RELACIONAMENTOS:
![exer](https://github.com/Ig0rFA/BD-BIBLIOTECA/blob/main/BD-BIBLIOTECA/Modelagem%20Biblioteca.png)

## Inserts:
/*Inicio inserts*/
insert into autores (id, nome, data_nascimento, nacionalidade) values (01,'Jorge Amado', '1912-08-10', 'Brasileiro');
insert into autores (id, nome, data_nascimento, nacionalidade) values (02,'Paulo Coelho', '1947-08-24', 'Brasileiro');
insert into autores (id, nome, data_nascimento, nacionalidade) values (03,'Machado de Assis', '1839-06-21', 'Brasileiro');
INSERT INTO autores (nome, data_nascimento, nacionalidade) VALUES ('Machado de Assis', '1839-06-21', 'Brasileiro');
INSERT INTO autores (nome, data_nascimento, nacionalidade) VALUES ('George Orwell', '1903-06-25', 'Inglês');
INSERT INTO autores (nome, data_nascimento, nacionalidade) VALUES ('Jane Austen', '1775-12-16', 'Inglês');
INSERT INTO autores (nome, data_nascimento, nacionalidade) VALUES ('Gabriel Garcia Márquez', '1927-03-06', 'Colombiano');
INSERT INTO autores (nome, data_nascimento, nacionalidade) VALUES ('Haruki Murakami', '1949-01-12', 'Japonês');
INSERT INTO autores (nome, data_nascimento, nacionalidade) VALUES ('J.K. Rowling', '1965-07-31', 'Britânico');
INSERT INTO autores (nome, data_nascimento, nacionalidade) VALUES ('Emily Dickinson', '1830-12-10', 'Americano');
INSERT INTO autores (nome, data_nascimento, nacionalidade) VALUES ('Leo Tolstoy', '1828-09-09', 'Russo');
INSERT INTO autores (nome, data_nascimento, nacionalidade) VALUES ('J.R.R. Tolkien', '1892-01-03', 'Inglês');
INSERT INTO autores (nome, data_nascimento, nacionalidade) VALUES ('Agatha Christie', '1890-09-15', 'Inglês');
INSERT INTO autores (nome, data_nascimento, nacionalidade) VALUES ('F. Scott Fitzgerald', '1896-09-24', 'Americano');
INSERT INTO autores (nome, data_nascimento, nacionalidade) VALUES ('Margaret Atwood', '1939-11-18', 'Canadense');
INSERT INTO autores (nome, data_nascimento, nacionalidade) VALUES ('Pablo Neruda', '1904-07-12', 'Chileno');
INSERT INTO autores (nome, data_nascimento, nacionalidade) VALUES ('Isaac Bashevis Singer', '1902-07-14', 'Polonês');
INSERT INTO autores (nome, data_nascimento, nacionalidade) VALUES ('Gustave Flaubert', '1821-12-12', 'Francês');
INSERT INTO autores (nome, data_nascimento, nacionalidade) VALUES ('Virginia Woolf', '1882-01-25', 'Inglês');
INSERT INTO autores (nome, data_nascimento, nacionalidade) VALUES ('Albert Camus', '1913-11-07', 'Argelino');


insert into editoras (id, nome, endereco) values (01,'Record', 'rua record 01');
insert into editoras (id, nome, endereco) values (02,'Planeta', 'rua planeta 02');
insert into editoras (id, nome, endereco) values (03,'Globo', 'rua globo 03');
insert into editoras (id, nome, endereco) values (04, 'Companhia das Letras', 'rua companhia das letras 04'),
insert into editoras (id, nome, endereco) values (05, 'Autêntica', 'rua autêntica 05'),
insert into editoras (id, nome, endereco) values (06, 'Leya', 'rua leya 06'),
insert into editoras (id, nome, endereco) values (07, 'HarperCollins', 'rua harpercollins 07'),
insert into editoras (id, nome, endereco) values (08, 'Penguin Random House', 'rua penguin random house 08'),
insert into editoras (id, nome, endereco) values (09, 'Galera Record', 'rua galera record 09'),
insert into editoras (id, nome, endereco) values (10, 'Summus', 'rua summus 10'),
insert into editoras (id, nome, endereco) values (11, 'FTD', 'rua FTD 11'),
insert into editoras (id, nome, endereco) values (12, 'Scipione', 'rua scipionie 12'),
insert into editoras (id, nome, endereco) values (13, 'Moderna', 'rua moderna 13'),
insert into editoras (id, nome, endereco) values (14, 'Saraiva', 'rua saraiva 14'),
insert into editoras (id, nome, endereco) values (15, 'Cultura', 'rua cultura 15'),
insert into editoras (id, nome, endereco) values (16, 'Zahar', 'rua zahar 16'),
insert into editoras (id, nome, endereco) values (17, 'Intrínseca', 'rua intrínseca 17'),
insert into editoras (id, nome, endereco) values (18, 'Todavia', 'rua todavia 18'),
insert into editoras (id, nome, endereco) values (19, 'Patuá', 'rua patuá 19'),
insert into editoras (id, nome, endereco) values(20, 'Nós', 'rua nós 20'),

insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (01,'Capitães da Areia', '978-85-200-0457-3', 1937, 10, 1, 1);
insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (02,'O Alquimista', '978-85-08-00660-9', 1988, 20, 2, 2);
insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (03,'Dom Casmurro', '978-85-01-01100-1', 1899, 30, 3, 3);
insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (04, 'Grande Sertão: Veredas', '978-85-309-0001-0', 1956, 40, 3, 1),
insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (05, 'Memórias Póstumas de Brás Cubas', '978-85-01-01000-0', 1881, 50, 3, 2),
insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (06, 'Iracema', '978-85-01-00900-0', 1865, 60, 1, 3),
insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (07, 'Quincas Borba', '978-85-01-00800-0', 1891, 70, 3, 1),
insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (08, 'Vidas Secas', '978-85-01-00700-0', 1938, 80, 2, 2),
insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (09, 'O Cortiço', '978-85-01-00600-0', 1890, 90, 2, 3),
insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (10, 'Macunaíma', '978-85-01-00500-0', 1928, 100, 2, 1),
insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (11, 'A Hora da Estrela', '978-85-01-00400-0', 1977, 110, 3, 2),
insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (12, 'A Hora da Estrela', '978-85-01-00300-0', 1977, 120, 3, 3),
insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (13, 'O Pequeno Príncipe', '978-85-01-00200-0', 1943, 130, 4, 1),
insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (14, 'Cem Anos de Solidão', '978-85-01-00100-0', 1967, 140, 5, 2),
insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (15, 'O Senhor dos Anéis', '978-85-01-00000-0', 1954-1955, 150, 6, 3),
insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (16, 'A Divina Comédia', '978-85-01-99999-0', 1308-1320, 160, 7, 1),
insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (17, 'O Príncipe', '978-85-01-99998-0', 1513, 170, 7, 2),
insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (18, 'O Código Da Vinci', '978-85-01-99997-0', 2003, 180, 8, 3),
insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (19, 'Harry Potter', '978-85-01-99996-0', 1997-2007, 190, 9, 1),
insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (20, 'As Crônicas de Nárnia', '978-85-01-99995-0', 1949-1954, 200, 10, 2),
insert into livros (id, titulo, isbn, ano_Publicacao, estoque, autores_id, editoras_id) values (21, 'A Guerra dos Tronos', '978-85-01-99994-0', 1996-2011, 210, 11, 3);

insert into clientes (id, nome, email, cpf) values (01,'Igor', 'igor@gmail.com',11122233344);
insert into clientes (id, nome, email, cpf) values (02,'Rafael', 'rafael@gmail.com',55566677788);
insert into clientes (id, nome, email, cpf) values (03,'Janio', 'janio@gmail.com',99910101011);
insert into clientes (id, nome, email, cpf) values (04, 'Maria', 'maria@gmail.com',22233344455),
insert into clientes (id, nome, email, cpf) values (05, 'João', 'joao@gmail.com',66677788899),
insert into clientes (id, nome, email, cpf) values (06, 'Ana', 'ana@gmail.com',10101010110),
insert into clientes (id, nome, email, cpf) values (07, 'Pedro', 'pedro@gmail.com',20202020202),
insert into clientes (id, nome, email, cpf) values (08, 'Carlos', 'carlos@gmail.com',30303030303),
insert into clientes (id, nome, email, cpf) values (09, 'Luiza', 'luiza@gmail.com',40404040404),
insert into clientes (id, nome, email, cpf) values (10, 'Francisco', 'francisco@gmail.com',50505050505),
insert into clientes (id, nome, email, cpf) values (11, 'Clara', 'clara@gmail.com',60606060606),
insert into clientes (id, nome, email, cpf) values (12, 'Daniel', 'daniel@gmail.com',70707070707),
insert into clientes (id, nome, email, cpf) values (13, 'Eduardo', 'eduardo@gmail.com',80808080808),
insert into clientes (id, nome, email, cpf) values (14, 'Beatriz', 'beatriz@gmail.com',90909090909),
insert into clientes (id, nome, email, cpf) values (15, 'Guilherme', 'guilherme@gmail.com',100100100100),
insert into clientes (id, nome, email, cpf) values (16, 'Fernanda', 'fernanda@gmail.com',11111111111),
insert into clientes (id, nome, email, cpf) values (17, 'Matheus', 'matheus@gmail.com',12121212121),
insert into clientes (id, nome, email, cpf) values (18, 'Isabela', 'isabela@gmail.com',13131313131),
insert into clientes (id, nome, email, cpf) values (19, 'Lucas', 'lucas@gmail.com',14141414141),
insert into clientes (id, nome, email, cpf) values (20, 'Letícia', 'leticia@gmail.com',15151515151);

insert into emprestimos (id, livro_id, cliente_id, data_emprestimo, data_devolucao, status) values (01,1, 1, '2023-10-27', '2023-10-30', 'Pendente');
insert into emprestimos (id, livro_id, cliente_id, data_emprestimo, data_devolucao, status) values (02,2, 2, '2023-11-27', '2023-11-29', 'Devolvido');
insert into emprestimos (id, livro_id, cliente_id, data_emprestimo, data_devolucao, status) values (03,3, 3, '2023-12-27', '2024-01-25', 'Atrasado');
insert into emprestimos (id, livro_id, cliente_id, data_emprestimo, data_devolucao, status) values (04, 1, 4, '2023-08-27', '2023-08-30', 'Pendente'),
insert into emprestimos (id, livro_id, cliente_id, data_emprestimo, data_devolucao, status) values (05, 2, 5, '2023-09-27', '2023-09-29', 'Devolvido'),
insert into emprestimos (id, livro_id, cliente_id, data_emprestimo, data_devolucao, status) values (06, 3, 6, '2023-10-27', '2023-10-30', 'Atrasado'),
insert into emprestimos (id, livro_id, cliente_id, data_emprestimo, data_devolucao, status) values (07, 1, 7, '2023-11-27', '2023-11-29', 'Pendente'),
insert into emprestimos (id, livro_id, cliente_id, data_emprestimo, data_devolucao, status) values (08, 2, 8, '2023-12-27', '2023-12-29', 'Devolvido'),
insert into emprestimos (id, livro_id, cliente_id, data_emprestimo, data_devolucao, status) values (09, 3, 9, '2023-01-27', '2023-01-29', 'Atrasado'),
insert into emprestimos (id, livro_id, cliente_id, data_emprestimo, data_devolucao, status) values(10, 1, 10, '2023-02-27', '2023-02-29', 'Pendente'),
insert into emprestimos (id, livro_id, cliente_id, data_emprestimo, data_devolucao, status) values (11, 2, 11, '2023-03-27', '2023-03-29', 'Devolvido'),
insert into emprestimos (id, livro_id, cliente_id, data_emprestimo, data_devolucao, status) values (12, 3, 12, '2023-04-27', '2023-04-29', 'Atrasado'),
insert into emprestimos (id, livro_id, cliente_id, data_emprestimo, data_devolucao, status) values (13, 1, 13, '2023-05-27', '2023-05-29', 'Pendente'),
insert into emprestimos (id, livro_id, cliente_id, data_emprestimo, data_devolucao, status) values (14, 2, 14, '2023-06-27', '2023-06-29', 'Devolvido'),
insert into emprestimos (id, livro_id, cliente_id, data_emprestimo, data_devolucao, status) values (15, 3, 15, '2023-07-27', '2023-07-29', 'Atrasado'),
insert into emprestimos (id, livro_id, cliente_id, data_emprestimo, data_devolucao, status) values (16, 1, 16, '2023-08-27', '2023-08-29', 'Pendente'),
insert into emprestimos (id, livro_id, cliente_id, data_emprestimo, data_devolucao, status) values (17, 2, 17, '2023-09-27', '2023-09-29', 'Devolvido'),
insert into emprestimos (id, livro_id, cliente_id, data_emprestimo, data_devolucao, status) values (18, 3, 18, '2023-10-27', '2023-10-29', 'Atrasado'),
insert into emprestimos (id, livro_id, cliente_id, data_emprestimo, data_devolucao, status) values (19, 1, 19, '2023-11-27', '2023-11-29', 'Pendente'),
insert into emprestimos (id, livro_id, cliente_id, data_emprestimo, data_devolucao, status) values (20, 2, 20, '2023-12-27', '2023-12-29', 'Devolvido');
/*Fim inserts*/

		

## STORE PROCEDURE:

-- Crie outra stored procedure para recuperar a lista de livros emprestados por um cliente específico.
/*Inicio stored procedure novo emprestimo*/
delimiter $$
create procedure Registra_Novo_Emprestimo (
IN livro_id int,
in cliente_id int,
in data_emprestimo date,
in data_devolucao date
)
begin

declare qtd int;

select estoque into qtd from livros where id = livro_id;
if qtd > 0 THEN

update livros set estoque = estoque - 1 where id = livro_id;
insert into emprestimos (livro_id, cliente_id, data_emprestimo, data_devolucao, status) values (livro_id, cliente_id, data_emprestimo, data_devolucao, 'Pendente');

ELSE
signal sqlstate '45000'
set message_text = 'O livro nao esta disponivel para emprestimo';

end if;
end $$
delimiter ;
/*Fim stored procedure novo emprestimo*/

-- Crie outra stored procedure para recuperar a lista de livros emprestados por um cliente específico.
/*Inicio stored procedure recuperar livros emprestados*/
delimiter $$
create procedure Recuperar_Livros_Emprestados (
in cliente_id int
)
begin

select * from emprestimos where id = cliente_id;

end $$
delimiter ;
/*Fim stored procedure recuperar livros emprestados*/
		

-- Implemente uma stored procedure que calcule multas para empréstimos atrasados.
      /*Inicio stored procedure calcular multas*/
delimiter $$
create procedure Calcular_Multa_Livros (
in cliente_id int
)
begin
update emprestimos set status = 'atrasado' where data_devolucao < CURRENT_DATE;

  update emprestimos
  set multas = (data_devolucao - data_emprestimo) * 20
  where status = 'atrasado';

end $$
delimiter ;
/*Fim stored procedure calcular multas*/
    
## Views:

-- Crie uma view que mostre os livros disponíveis para empréstimo, excluindo aqueles que já foram emprestados.
/*Inicio views livros disponiveis*/
create view livros_disponiveis as select * from livros where estoque > 0;
/*Fim views livros disponiveis*/

select * from livros_disponiveis;

/*Inicio views livros disponiveis*/
create view Emprestimos_Detalhado  as select * from emprestimos inner join  livros on emprestimos.livro_id = livros.id;
/*Fim views livros disponiveis*/

## Link SQL completo:
![exer](https://github.com/Ig0rFA/BD-BIBLIOTECA/blob/main/BD-BIBLIOTECA/Biblioteca.sql)

