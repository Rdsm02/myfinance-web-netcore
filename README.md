# My Finance Web
MyFinance Projeto do Curso de Pós Graduação em Engenharia de Software PUC MG

<br>

## Arquitetura

<hr>

Abaixo será apresentada toda arquitetura do projeto construído

<br>

### Banco de Dados
<hr>
A figura abaixo representa a modelagem lógica do banco de dados da aplicação modelo DER - Diagrama de Entidades e Relacionamentos

<br>

<img src="docs\DER.png" alt="diagram">

<br>

Abaixo encontra-se o script da tabela representada acima



```javascript
CREATE DATABASE my_finance;

USE my_finance

CREATE TABLE plano_contas (
    id int identity(1,1) not null,
    descricao varchar(50), not null,
    tipo char(1) not null,
    primary key(id)
);


CREATE TABLE transacao (
    id bigint identity(1,1) not null,
    plano_contas_id int not null,
    data datetime not null,
    valor decimal(18,2) not null,
    tipo char(1) not null,
    historico text null,
    primary key(id),
    foreign key(plano_contas_id) references plano_contas
);
```

