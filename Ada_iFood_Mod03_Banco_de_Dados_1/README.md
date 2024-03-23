# Banco de Dados 1
- Professor Matheus Andrade

## Aula 1
### O que é banco de dado?

 Um banco de dados é um sistema organizado de informações que pode ser acessado, gerenciado e atualizado de maneira conveniente. Em termos simples, um banco de dados é um armário gigante que armazena informações sobre tudo, desde os nomes de clientes até informações de produtos, registros financeiros e muito mais.

### Utilidade de um banco de dados
Um banco de dados é como um grande armário de arquivos, mas em vez de papel, ele armazena informações digitais. Ele é projetado para armazenar e gerenciar grandes quantidades de dados de maneira organizada e eficiente. Assim como um armário de arquivos é útil para manter documentos organizados e fáceis de encontrar, um banco de dados é útil para armazenar e acessar informações de maneira rápida e eficiente.

 Com um banco de dados, você pode armazenar todas essas informações em uma única fonte confiável e organizada. Você pode facilmente acessar e atualizar informações sobre seus produtos, clientes e pedidos em tempo real, em vez de ter que procurar em vários arquivos ou documentos. Você pode gerar relatórios e análises para ajudar a entender melhor seu negócio e tomar decisões informadas com base nos dados.

### PostgreSQL

O PostgreSQL é conhecido por sua confiabilidade, escalabilidade e desempenho. Ele foi projetado para suportar cargas de trabalho pesadas e é altamente personalizável, permitindo que os usuários ajustem o sistema de acordo com suas necessidades específicas. Além disso, ele é altamente compatível com padrões do setor e oferece suporte a muitos recursos avançados, como transações ACID, índices em texto completo, integridade referencial e muito mais. Ele é uma das ferramentas de banco de dados mais populares do mercado, oferecendo recursos avançados de segurança, confiabilidade e escalabilidade.

### Tipos de banco de dados:
#### 1 - Banco de dados relacionais

Os bancos de dados relacionais são baseados em uma estrutura de tabelas inter-relacionadas. Os dados são organizados em tabelas, cada uma com uma coluna para um tipo específico de dado e cada linha contendo uma entrada individual. As tabelas são inter-relacionadas por meio de chaves primárias e estrangeiras, que são usadas para vincular os dados em diferentes tabelas. O SQL (Structured Query Language) é a linguagem de programação mais comumente usada para manipular bancos de dados relacionais.

#### 2 - Banco de dados não-relacionais

Os bancos de dados não relacionais são projetados para armazenar dados sem a estrutura rígida de tabelas e esquemas relacionais. Eles são mais flexíveis em termos de como os dados são organizados e podem ser mais escaláveis e tolerantes a falhas do que os bancos de dados relacionais. Eles também podem ser usados para armazenar tipos de dados mais complexos, como documentos, gráficos e dados de séries temporais. Exemplos de bancos de dados não relacionais incluem bancos de dados de documentos, bancos de dados de grafos e bancos de dados de séries temporais.

### Instalação PostgreSQL

A maneira mais fácil de instalar o PostgreSQL no Windows é através do instalador disponível no site oficial.

[O link para download](https://www.postgresql.org/download/windows/).

Basta baixar o arquivo de instalação correspondente à versão desejada, executá-lo e seguir as instruções na tela. É importante lembrar que durante a instalação é possível selecionar os componentes que deseja instalar, como a ferramenta gráfica **pgAdmin**. Além disso, também é possível escolher o local de instalação e a senha do usuário admin. Após a instalação, o PostgreSQL estará pronto para uso.

Para mais informações sobre a instalação do PostgreSQL no Windows, consulte a [documentação oficial](https://www.postgresql.org/docs/current/tutorial-install.html).

### DDL e DML

DDL significa *Data Definition Language*, que é uma linguagem utilizada para definir a estrutura e as características dos dados em um banco de dados. DDL é usado para criar, modificar e excluir objetos no banco de dados, como tabelas, índices, views e outros objetos.

[Documentação](https://www.postgresql.org/docs/current/ddl.html).

Já o DML significa *Data Manipulation Language*, que é uma linguagem usada para manipular os dados dentro de um banco de dados. DML é usado para inserir, atualizar, excluir e recuperar dados em um banco de dados. Isso significa que o DML é usado para fazer operações de leitura e escrita nos dados armazenados em um banco de dados.

[Documentação](https://www.postgresql.org/docs/current/dml.html).

### Databases

#### Criando um banco de dados com o comando createdb:

Para criar um banco de dados usando o createdb, basta executar o seguinte comando no terminal:
```
createdb <nome_do_banco_de_dados>
```

Substitua ``<nome_do_banco_de_dados>`` pelo nome desejado para o banco de dados. Por exemplo:

#### Criando um banco de dados utilizando linguagem SQL:

O comando CREATE DATABASE é usado para criar um banco de dados no PostgreSQL. Ele pode ser executado tanto no utilitário de linha de comando psql quanto em outras ferramentas que suportam a execução de comandos SQL.

```
CREATE DATABASE nome_do_banco_de_dados;
```

É possível especificar outras opções ao criar um banco de dados, como o proprietário do banco de dados, a codificação de caracteres e a localização do banco de dados. Algumas opções comuns incluem:

- **OWNER** para definir o proprietário do banco de dados.
- **ENCODING** para definir a codificação de caracteres do banco de dados.
- **LC_COLLATE** e **LC_CTYPE** para definir as configurações de localização do banco de dados.

Por exemplo, o seguinte comando cria um banco de dados chamado "minha_base_de_dados" com o proprietário "meu_usuario" e codificação de caracteres "UTF8":

```
CREATE DATABASE minha_base_de_dados
WITH    OWNER meu_usuario
        ENCODING 'UTF8'
        LC_COLLATE 'pt_BR.UTF-8'
        LC_CTYPE 'pt_BR.UTF-8';
```

#### Removendo um banco de dados com o comando dropdb

Para remover um banco de dados usando o dropdb, basta executar o seguinte comando no terminal:
```
dropdb <nome_do_banco_de_dados>
```
#### Removendo um banco de dados utilizando linguagem SQL

Para remover um banco de dados existente utilizando linguagem SQL, basta executar o comando:
```
DROP DATABASE nome_do_banco_de_dados;
```

Além disso, podemos adicionar o parâmetro **IF EXISTS**, ele funciona como um validador para quando o banco de dados mencionado não existir, o PostgreSQL somente ignorar ao invés de retornar um erro.
```
DROP DATABASE IF EXISTS meu_banco_bonito;
```
### Criação de tabelas

Para criar uma tabela no PostgreSQL, você precisa usar a linguagem DDL (*Data Definition Language*) e a sintaxe é a seguinte:

```
CREATE TABLE nome_da_tabela (
  nome_do_campo1 tipo_do_campo1,
  nome_do_campo2 tipo_do_campo2,
  ...,
  nome_do_campoN tipo_do_campoN
);
```
Por exemplo, para criar uma tabela chamada "clientes" com dois campos, "id" e "nome", o comando seria o seguinte:
````
CREATE TABLE clientes (
  id SERIAL PRIMARY KEY,
  nome VARCHAR(50)
);

````
Este comando cria uma tabela "clientes" com um campo "id" que é um número serial (ou seja, um número sequencial gerado automaticamente pelo PostgreSQL) e um campo "nome" que é uma *string* de até 50 caracteres.

### Edição de Tabela

Para editar uma tabela existente no PostgreSQL, você pode usar o comando **ALTER TABLE**. Por exemplo, se você quiser adicionar um novo campo "email" à tabela "clientes", o comando seria o seguinte:
````
ALTER TABLE clientes ADD COLUMN email VARCHAR(50);
````
Este comando adiciona um novo campo chamado "email" à tabela "clientes" com um comprimento máximo de 50 caracteres.

#### Exclusão de tabelas
Para excluir uma tabela no PostgreSQL, você pode usar o comando **DROP TABLE**. Por exemplo, se você quiser excluir a tabela "clientes", o comando seria o seguinte:

```
DROP TABLE clientes;
```

Este comando exclui a tabela "clientes" e todos os dados armazenados nela.


## Aula 2

### Tipos de dados mais comuns
Nos exemplos acima, falamos dos tipos ``int`` e ``varchar``, porém, existem alguns outros tipos de dados que são possíveis de serem utilizados, que nos auxiliam para situações específicas.

- Tipos numéricos:

    ``INTEGER``: armazena números inteiros com sinal. O tamanho padrão é de 4 bytes, mas pode ser especificado um tamanho maior ou menor. É usado para armazenar dados numéricos que representam quantidades inteiras, como a quantidade de itens em um pedido.

    ``BIGINT``: armazena números inteiros com sinal de 8 bytes. É usado para armazenar dados numéricos que representam quantidades maiores que o INTEGER, como o número de habitantes de uma cidade ou país.

    ``NUMERIC``: armazena números decimais com precisão arbitrária. É usado para armazenar valores monetários ou outros dados numéricos que requerem alta precisão.

    ``DOUBLE PRECISION``: armazena números de ponto flutuante de dupla precisão. É usado para armazenar dados numéricos que requerem alta precisão e uma grande faixa de valores, como as coordenadas geográficas de um local.

- Tipos de texto

    ``VARCHAR``: armazena *strings* de comprimento variável. É usado para armazenar dados de texto de comprimento variável, como nomes de pessoas ou endereços de e-mail.

    ``CHAR``: armazena strings de comprimento fixo. É usado para armazenar dados de texto de comprimento fixo, como códigos postais ou números de identificação.

    ``TEXT``: armazena strings de comprimento variável sem limite. É usado para armazenar grandes volumes de dados de texto, como descrições de produtos ou comentários em um *site*.


- Tipos de data e hora

    ``DATE``: armazena datas (ano, mês, dia). É usado para armazenar informações de datas, como datas de nascimento ou datas de eventos.

    ``TIME``: armazena horas do dia. É usado para armazenar informações de hora, como horários de início ou fim de eventos.

    ``TIMESTAMP``: armazena datas e horas com precisão de milissegundos. É usado para armazenar informações de datas e horas precisas, como timestamps de criação ou modificação de registros.

- Tipos booleanos

    ``BOOLEAN``: armazena valores verdadeiro ou falso. É usado para armazenar dados booleanos, como se um usuário está conectado ou desconectado.

- Tipos de array

    ``ARRAY``: armazena uma lista de valores de um tipo de dado específico. É usado para armazenar coleções de dados, como uma lista de itens em um pedido ou as cores favoritas de um usuário.

- Tipos especiais

    ``JSON`` e ``JSONB``: armazena dados em formato JSON (*JavaScript Object Notation*), usado para armazenar dados semiestruturados que podem ser facilmente lidos por outras aplicações ou sistemas.

    ``UUID``: armazena identificadores únicos universais (UUIDs), que são frequentemente usados em sistemas distribuídos para identificar de forma única recursos em um cluster.

- ***Default values***

Em PostgreSQL, um valor padrão (ou "*default value*") é um valor que é automaticamente atribuído a uma coluna se nenhum valor é especificado para ela durante a inserção de dados.

Aqui está um exemplo de como definir um valor padrão em PostgreSQL:

````
CREATE TABLE clientes (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(100),
    email VARCHAR(100),
    data_de_cadastro TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
````

Neste exemplo, a coluna "data_de_cadastro" é definida com um valor padrão de "``CURRENT_TIMESTAMP``", que é uma função que retorna a data e hora atual do sistema. Isso significa que, se nenhum valor for especificado para essa coluna durante a inserção de dados, o PostgreSQL irá automaticamente inserir a data e hora atual.

Outro exemplo pode ser de uma tabela de pedidos, onde a coluna "*status*" pode ter um valor padrão "pendente" para todos os novos pedidos:

````
CREATE TABLE pedidos (
    id SERIAL PRIMARY KEY,
    descricao VARCHAR(100),
    valor DECIMAL(10,2),
    status VARCHAR(20) DEFAULT 'pendente'
);
````

Neste exemplo, a coluna "status" é definida com um valor padrão "pendente", que será automaticamente inserido se nenhum valor for especificado durante a inserção de dados.

Além disso, é importante observar que um valor padrão pode ser definido para qualquer tipo de coluna, incluindo texto, números, datas, booleanos etc. É uma ferramenta útil para garantir a consistência dos dados em uma tabela e simplificar a inserção de dados.

### Chave Primária (*Primary Keys ou PKs*)

No PostgreSQL, uma Primary Key é uma restrição que define uma coluna ou conjunto de colunas em uma tabela como uma chave primária. A Primary Key é usada para identificar de forma exclusiva cada linha da tabela. Cada tabela pode ter apenas uma Primary Key.

Uma analogia para entender a importância de uma Primary Key seria como uma identidade para uma pessoa. Assim como cada pessoa tem um CPF exclusivo, cada linha em uma tabela precisa ter um identificador exclusivo para ser identificado corretamente.

> Primary Key é uma restrição importante no PostgreSQL que garante que cada linha de uma tabela tenha um identificador exclusivo e ajuda a melhorar o desempenho das consultas.

Para criar uma Primary Key em uma tabela no PostgreSQL, você pode usar a seguinte sintaxe:


```
ALTER TABLE tabela
ADD CONSTRAINT nome_da_pk PRIMARY KEY (coluna);
```

Onde "``tabela``" é o nome da tabela em que você deseja criar a Primary Key, "``nome_da_pk``" é um nome de sua escolha para a Primary Key e "``coluna``" é o nome da coluna que você deseja definir como a chave primária.


### Chaves estrangeiras (*Foreign Keys ou FKs*)


*Foreign Keys*, ou chaves estrangeiras, são uma ferramenta importante para estabelecer relacionamentos entre tabelas em um banco de dados. Uma *Foreign Key* é uma coluna (ou um conjunto de colunas) em uma tabela que se refere a uma *Primary Key* em outra tabela. A *Foreign Key* é usada para garantir que os dados em uma tabela estejam relacionados aos dados em outra tabela, mantendo a integridade referencial do banco de dados.

Suponha que você tem uma tabela de ``produtos`` e outra tabela de ``categorias``. Cada produto pode estar associado a uma única categoria. Para estabelecer esse relacionamento, você pode adicionar uma coluna chamada "``id_categoria``" na tabela de produtos e definir essa coluna como uma *Foreign Key* que referencia a *Primary Key* da tabela de categorias.

```
CREATE TABLE categorias (
  id SERIAL PRIMARY KEY,
  nome VARCHAR(50)
);

CREATE TABLE produtos (
  id SERIAL PRIMARY KEY,
  id_categoria INTEGER,
  nome VARCHAR(50),
  preco NUMERIC(10,2),
  FOREIGN KEY (id_categoria) REFERENCES categorias(id)
);
```

## Aula 3

### MER - Modelo Entidade-Relacionamento

O MER (Modelo Entidade Relacionamento) é utilizado para descrever os objetos do mundo real através de entidades, com suas propriedades que são os atributos e os seus relacionamentos.

As entidades representam um objeto do mundo real e que possuem uma existência independente, como: pessoas, empresa, carro, casa, entre outras coisas que podem ser representadas por uma entidade. Podemos considerar que existem três tipos de entidades:
- As entidades fortes, que não dependem de outras entidades para existirem;
- As entidades fracas, dependem de outras entidades para existir, ou seja, elas não possuem existência própria ou não possuem atributos próprios para identificação, dependendo assim, dos atributos chave das entidades fortes;
- As entidades associativas, que são utilizadas quando existe a necessidade de associar uma entidade a um relacionamento.

### DER - Diagrama Entidade-Relacionemento

O DER (Diagrama Entidade-Relacionamento) é utilizado para representar em forma gráfica o que foi descrito no MER (Modelo Entidade Relacionamento).

### O que são entidades?

Entidades são formas gráficas que representam objetos do mundo real e que possuem existência independente, podemos dizer que representam por exemplo pessoas, empresas, automóveis, casa, departamentos, produtos e muitas outras coisas.

De forma simples podemos dizer que existem três tipos de entidades, as entidades fortes, as entidades fracas e as entidades associativas.

#### Entidades fortes:

São entidades que não dependem de outras entidades para existirem. Um exemplo seria em um sistema de recursos humanos (RH), onde a entidade cargos, por exemplo, independe de quaisquer outras para existir.

#### Entidades fracas:

As entidades fracas seguem o lado oposto das fortes, elas dependem de outras entidades para existirem. Utilizando o exemplo anterior do sistema de recursos humanos, uma entidade de colaborador dependeria da entidade cargo, pois um colaborador sem cargo não faria sentido.

#### Entidades associativas:
As entidades associativas são utilizadas quando temos a necessidade de associar o relacionamento entre duas ou mais entidades, neste caso um exemplo que podemos utilizar é com base no sistema de recursos humanos anteriores, se pensarmos que temos uma entidade chamada cargo e uma entidade chamada área que pode ter valores como gestão, tecnologia da informação, recrutador etc. Podemos pensar no seguinte cenário: Um cargo pode estar em várias áreas ao mesmo tempo, por exemplo, um cargo de gestor pode administrar várias áreas, da mesma forma que várias áreas são administradas pelo cargo de gestor, mais um exemplo seria no caso de um recrutador que pode recrutar para várias áreas, ao mesmo tempo que várias áreas têm recrutamento pelo cargo recrutador, neste caso estabelecemos um relacionamento que chamamos de muitos para muitos que veremos mais especificamente no tópico de Relacionamentos logo abaixo. Levando em consideração estes exemplos, devemos criar uma entidade associativa que terá como atributo as chaves primárias das tabelas que fazem parte do relacionamento.

### O que são atributos?

Atributos são representações de características de uma entidade, podemos utilizar como exemplo os atributos definidos para as entidades abaixo:

Os atributos podem ser definidos em algumas categorias, e elas são:

#### Atributos Simples:

São atributos indivisíveis, ou seja, é composto por uma característica que não tem como dividir/destrinchar em outros atributos, um exemplo seria o atributo RG, ele não pode ser dividido em partes menores para formar outros atributos, o que o torna indivisível;

#### Atributos Compostos:

São atributos que podem ser divididos em uma ou mais partes que o representam, como o atributo Endereço, ele pode ser subdividido em atributos menores, como, por exemplo, cidade, estado, rua, cep, número e bairro. Também temos o atributo Nome na entidade de pessoas, pois podemos dividir ele em dois atributos menores que seriam Primeiro Nome e Sobrenome;

#### Atributos Monovalorados:

São atributos que possuem um único valor para a entidade, como por exemplo, o campo nome relacionado a entidade automóvel;

#### Atributos Multivalorados:

São atributos que possuem mais de um valor. Por exemplo, o caso da categoria associada à entidade produtos, pois é possível não ter nenhuma categoria ou ter várias.

#### Atributos Referenciais:

São atributos que representam a ligação de uma entidade com outra em um relacionamento e são chamados de Chave Estrangeira (FK(*Foreign Key*)), ou seja, eles são ligados a chave primária de outra entidade. Um exemplo seria em um banco de dados de *e-commerce* onde temos uma entidade categoria que tem um atributo que armazenará o código de identificação dela no sistema que é sua chave primária (PK), e uma entidade de produto que possui uma categoria, então temos o relacionamento da entidade de produto com a de categoria.

Existem alguns atributos que representam valores únicos que identificam a entidade, podemos utilizar como exemplo um cadastro de clientes, onde temos um atributo que é o CPF, um CPF é um documento único que representa cada cliente, então chamamos ele de chave primária ou utilizamos a sigla PK(*Primary Key*) para identificá-lo.

### Relacionamentos
A partir do momento que as entidades são identificadas, devemos definir como será o relacionamento entre elas. Os tipos de relacionamentos entre as entidades são três:

#### Relacionamento 1 para 1 (1:1):
É quando temos duas entidades envolvidas e elas referenciam obrigatoriamente apenas uma a outra. Um exemplo seria em um banco de dados de gestão de clientes, e cada cliente tem seu único endereço, assim como um endereço pertence somente a um cliente.

#### Relacionamento 1 para muitos (1:N):
É quando uma das entidades envolvidas, que vamos chamar de X pode referenciar várias unidades da outra que podemos nomear de Y, porém, a outra entidade Y só pode referenciar uma unidade da entidade X. Um exemplo seria em um banco de dados de gestão de clientes, onde cada cliente pode ter vários endereços, assim como vários endereços pertencem a um único cliente.

## Aula 4

### Formas normais

As formas normais são um conjunto de regras para garantir que um banco de dados relacional esteja organizado de maneira coerente e sem redundâncias desnecessárias. As formas normais são importantes porque elas ajudam a evitar problemas como inconsistências de dados, dificuldade de manutenção e desempenho ruim do banco de dados.

Existem várias formas normais, sendo as mais comuns:

- **Primeira Forma Normal (1FN)** A 1FN exige que todas as tabelas em um banco de dados relacional tenham dados atômicos, ou seja, que não haja campos que contenham mais de um valor. Além disso, cada campo em uma tabela deve ter um nome único e cada registro deve ter um identificador exclusivo (chave primária).

- **Segunda Forma Normal (2FN)** A 2FN exige que todas as tabelas em um banco de dados relacional estejam na 1FN e que cada campo em uma tabela dependa totalmente da chave primária da tabela. Isso significa que não deve haver campos que dependam apenas de parte da chave primária.

- **Terceira Forma Normal (3FN)** A 3FN exige que todas as tabelas em um banco de dados relacional estejam na 2FN e que não haja dependências transitivas entre os campos de uma tabela. Isso significa que um campo deve depender apenas da chave primária da tabela e não de outros campos.

- **Forma Normal de Boyce-Codd (BCNF)** A BCNF é uma forma normal mais rigorosa do que a 3FN. Ela exige que cada dependência funcional em uma tabela seja uma chave candidata da tabela. Isso garante que não haja redundância de dados em uma tabela.

Além dessas formas normais, existem outras, como a **Quarta Forma Normal (4FN)**, a **Quinta Forma Normal (5FN)** e a **Forma Normal de Domínio/Elementar (DKNF)**. Essas formas normais são usadas em situações específicas e são menos comuns do que as quatro primeiras.

Para exemplificar, faremos um caso de uso.

Vamos supor que temos uma tabela chamada "Pedidos" que contém informações sobre os pedidos que os clientes fizeram em uma loja virtual:

| Pedido | Cliente | Endereço | Cidade         | Estado | CEP       | Produto  | Quantidade | Preço |
|:------:|:-------:|:--------:|:--------------:|:------:|:---------:|:--------:|:----------:|:-----:|
|      1 |     Ana |    Rua A |      São Paulo |     SP | 01000-000 | Camiseta |          2 | 50,00 |
|      2 |   Bruno |    Rua B | Rio de Janeiro |     RJ | 02000-000 | Camiseta |          1 | 50,00 |
|      3 |   Carla |    Rua C |      São Paulo |     SP | 01000-000 |    Calça |          3 | 80,00 |

Nesta tabela, temos informações que não estão atomicamente armazenadas, como o "Endereço", "Cidade", "Estado" e "CEP". Além disso, há uma dependência transitiva entre "Produto", "Quantidade" e "Preço", já que o preço pode ser calculado a partir do produto e da quantidade.

Para normalizar essa tabela, podemos dividir em três tabelas: "Pedidos", "Clientes" e "Produtos".

Tabela Pedidos: 

| Pedido | ClienteID | ProdutoID | Quantidade |
|:------:|:---------:|:---------:|:----------:|
| 1      |         1 |         1 |          2 |
| 2      |         2 |         1 |          1 |
| 3      |         3 |         2 |          3 |

Tabela Clientes:

| ClienteID | Nome  | Endereço | Cidade         | Estado |       CEP |
|:---------:|:-----:|:--------:|:--------------:|:------:|:---------:|
|         1 | Ana   |    Rua A | São Paulo      |     SP | 01000-000 |
|         2 | Bruno |    Rua B | Rio de Janeiro |     RJ | 02000-000 |
|         3 | Carla |    Rua C | São Paulo      |     SP | 01000-000 |

Tabela Produtos:

| ProdutoID | Nome     | Preço |
|:---------:|:--------:|:-----:|
| 1         | Camiseta | 50,00 |
| 2         | Calça    | 80,00 |

Na tabela "Pedidos", a chave primária é a combinação de "Pedido", "ClienteID" e "ProdutoID". Na tabela "Clientes", a chave primária é "ClienteID" e na tabela "Produtos", a chave primária é "ProdutoID". Com essa estrutura, todas as informações estão atomicamente armazenadas, e não há dependência transitiva entre os campos de cada tabela.

Com isso, temos uma estrutura normalizada que está na **3NF**, e que nos permite gerenciar os dados de forma mais eficiente e segura. Note que este exemplo é apenas ilustrativo e que o processo de normalização pode ser mais complexo em casos reais.

## Aula 5

### Views

Em PostgreSQL, uma *view* é uma representação virtual de uma tabela que é criada usando uma consulta SQL. É basicamente uma consulta armazenada que é definida como um objeto de banco de dados e pode ser tratada como uma tabela física em muitos casos. Uma *view* é uma tabela virtual que não é armazenada fisicamente em disco, mas que é tratada como se fosse uma tabela real.

As views são usadas principalmente para simplificar consultas complexas e reduzir a quantidade de código SQL que precisamos escrever. Elas também podem ser usadas para limitar o acesso a certas informações, permitindo que os usuários vejam apenas as informações relevantes para eles.

As views podem ser criadas usando a seguinte sintaxe:

````
CREATE VIEW nome_da_view AS
SELECT coluna1, coluna2, ...
FROM tabela
WHERE condição
````
Após criar a view, podemos consultá-la usando a sintaxe básica de SELECT:

```
SELECT * FROM nome_da_view;
```
Também é possível executar consultas mais complexas em cima da view, incluindo *joins*, subconsultas e funções de agregação.

Algumas características importantes das views em PostgreSQL incluem:

- As *views* podem ser atualizáveis ou somente leitura, dependendo da definição da consulta subjacente.
- As *views* são armazenadas no banco de dados, permitindo que outros usuários ou aplicativos acessem a mesma definição.
- As *views* podem ser usadas para abstrair a complexidade da consulta subjacente e fornecer uma interface mais simples para os usuários.
- As *views* podem ser usadas para proteger dados sensíveis, permitindo que os usuários vejam apenas as informações relevantes para eles.

Suponha que temos duas tabelas: "clientes" e "pedidos". A tabela "clientes" tem informações sobre os clientes da loja, enquanto a tabela "pedidos" tem informações sobre os pedidos que os clientes fizeram.


````
CREATE TABLE pedidos (
    id SERIAL PRIMARY KEY,
    cliente_id INTEGER REFERENCES clientes(id),
    data_pedido DATE NOT NULL,
    total DECIMAL(10, 2) NOT NULL
);
````
Agora, vamos supor que queremos criar uma *view* que mostre o nome do cliente, o número de pedidos que ele fez e o valor total desses pedidos. Podemos fazer isso com o seguinte código SQL:
```
CREATE VIEW resumo_pedidos AS
    SELECT  c.nome,
            COUNT(p.*) AS num_pedidos,
            SUM(p.total) AS valor_total
        FROM clientes c
            INNER JOIN pedidos p 
                ON c.id = p.cliente_id
        GROUP BY c.nome;

```
Aqui, estamos usando uma cláusula ``INNER JOIN`` para juntar as tabelas "clientes" e "pedidos" com base no campo "cliente_id". Em seguida, estamos usando uma cláusula ``GROUP BY`` para agrupar os resultados pelo nome do cliente. Finalmente, estamos usando a função ``COUNT`` para contar o número de pedidos e a função ``SUM`` para calcular o valor total dos pedidos para cada cliente.

Agora que temos a *view* "resumo_pedidos", podemos usá-la para obter informações resumidas sobre os pedidos de cada cliente com o seguinte código SQL:

```
SELECT * FROM resumo_pedidos;
```

Isso irá nos retornar um conjunto de resultados com o nome de cada cliente, o número de pedidos que ele fez e o valor total desses pedidos. Podemos usar essa view sempre que precisarmos dessas informações resumidas, sem precisar escrever a consulta SQL complexa toda vez.

## Aula 6

### Union

``UNION`` e ``UNION ALL`` são operadores em SQL que permitem combinar os resultados de duas ou mais consultas SELECT em uma única tabela de resultados. Ambos os operadores são usados para combinar as linhas retornadas pelas consultas SELECT, mas há uma diferença importante entre eles.

O operador ``UNION`` remove automaticamente quaisquer linhas duplicadas do resultado, enquanto o operador ``UNION ALL`` **não** as remove e simplesmente une todas as linhas resultantes.

Aqui está um exemplo de como usar o UNION:

````
SELECT coluna1, coluna2 FROM tabela1
UNION
SELECT coluna1, coluna2 FROM tabela2;
````
Neste exemplo, o ``UNION`` é usado para combinar os resultados de duas consultas ``SELECT``, que selecionam as mesmas colunas de duas tabelas diferentes, e o operador ``UNION`` é usado para remover automaticamente quaisquer linhas duplicadas.

E aqui está um exemplo de como usar o ``UNION ALL``:

```
SELECT coluna1, coluna2 FROM tabela1
UNION ALL
SELECT coluna1, coluna2 FROM tabela2;
```

Neste exemplo, o ``UNION ALL`` é usado para combinar os resultados de duas consultas ``SELECT``, que selecionam as mesmas colunas de duas tabelas diferentes, mas o operador ``UNION ALL`` não remove quaisquer linhas duplicadas.

O uso do ``UNION`` pode ser útil quando queremos combinar os resultados de duas ou mais consultas ``SELECT`` e remover automaticamente quaisquer linhas duplicadas. No entanto, o uso do ``UNION ALL`` pode ser útil quando desejamos combinar os resultados de duas ou mais consultas ``SELECT`` sem remover as linhas duplicadas. É importante notar que o uso do ``UNION ALL`` pode ser mais rápido do que o uso do ``UNION``, já que não há o custo extra de se verificar quais linhas são duplicadas.

Suponha que temos duas tabelas, ``clientes`` e ``fornecedores``, que têm a mesma estrutura de colunas:

clientes:
| id | primeiro | ultimo   | email            | 
|:--:|:--------:|:--------:|------------------| 
|  1 | Joao     | Silva    | joao@email.com   | 
|  2 | Maria    | Santos   | maria@email.com  | 
|  3 | Jose     | Oliveira | jose.o@email.com | 
|  4 | Ana      | Souza    | ana@email.com    |

fornecedores:
| id | primeiro | ultimo  | email             |
|:--:|:--------:|:-------:|:-----------------:|
| 4  | Ana      | Souza   | ana@email.com     |
| 5  | Carlos   | Lima    | carlima@email.com |
| 6  | Renata   | Pereira | renata@email.com  |

Veja que temos nas duas tabelas, um registro idêntico, poderia ser uma pessoa que é cliente e fornecedor.

Podemos usar o operador ``UNION`` para combinar as duas tabelas e obter uma lista completa de contatos:
```
SELECT id, primeiro, ultimo, email FROM clientes
UNION
SELECT id, primeiro, ultimo, email FROM fornecedores;
```

Resultando em:

| id | primeiro | ultimo    | email             |
|:--:|:--------:|:---------:|:-----------------:|
| 1  | Joao     | Silva     | joao@email.com    |
| 2  | Maria    | Santos    | maria@email.com   |
| 3  | Jose     | Oliveira  | jose.o@email.com  |
| 4  | Ana      | Souza     | ana@email.com     |
| 5  | Carlos   | Lima      | carlima@email.com |
| 6  | Renata   | Pereira   | renata@email.com  |

No entanto, se quisermos obter uma lista completa de todos os contatos, incluindo aqueles que podem aparecer em ambas as tabelas, podemos usar o operador ``UNION ALL``:

```
SELECT id, primeiro, ultimo, email FROM clientes
UNION ALL
SELECT id, primeiro, ultimo, email FROM fornecedores;
```
Resultando em:

| id | primeiro | ultimo   | email             |
|:--:|:--------:|:--------:|:-----------------:|
| 1  | Joao     | Silva    | joao@email.com    |
| 2  | Maria    | Santos   | maria@email.com   |
| 3  | Jose     | Oliveira | jose.o@email.com  |
| 4  | Ana      | Souza    | ana@email.com     |
| 4  | Ana      | Souza    | ana@email.com     | 
| 5  | Carlos   | Lima     | carlima@email.com |
| 6  | Renata   | Pereira  | renata@email.com  | 

Observe que o operador ``UNION ALL`` simplesmente une todas as linhas resultantes, incluindo quaisquer linhas duplicadas.

Pensando em performance, quando sabemos que nas duas tabelas não terão registros duplicados, prefira utilizar o ``UNION ALL``.

Além do ``UNION``, que une registros, ainda temos outras operações similares entre tabelas:

``INTERSECT``: Retorna apenas dados que são **iguais** nas duas tabelas;

``EXCEPT``: Retorna apenas dados da **primeira tabela** que não existem na segunda tabela.

### Agregação

As funções de agregação em SQL permitem que você calcule valores agregados para um conjunto de registros em uma tabela. Existem várias funções de agregação disponíveis em SQL, incluindo ``SUM``, ``AVG``, ``COUNT``, ``MAX`` e ``MIN``.

A função ``SUM`` é usada para **somar** os valores de uma coluna em uma tabela.
```
SELECT SUM(preco) FROM produtos;
```

A função ``AVG`` é usada para calcular a **média** dos valores de uma coluna em uma tabela.
```
SELECT AVG(preco) FROM produtos;
```

A função ``COUNT`` é usada para **contar** o número de registros em uma tabela ou o número de valores distintos em uma coluna.
```
SELECT COUNT(*) FROM produtos;
```

A função ``MAX`` é usada para encontrar o maior valor em uma coluna em uma tabela.
```
SELECT MAX(preco) FROM produtos;
```

A função ``MIN`` é usada para encontrar o **menor** valor em uma coluna em uma tabela.
```
SELECT MIN(preco) FROM produtos;
```

#### Group By
A cláusula ``GROUP BY`` é usada em conjunto com as funções de agregação para agrupar registros com base em uma ou mais colunas e, em seguida, calcular valores agregados para cada grupo. Aqui estão alguns exemplos de uso da cláusula ``GROUP BY`` com funções de agregação:

- **Exemplo 1:** contar o número de produtos em cada categoria:

Suponha que temos uma tabela "produtos" com as colunas "id_produto", "nome", "categoria" e "preco". Podemos usar a cláusula ``GROUP BY`` para agrupar os produtos por categoria e, em seguida, usar a função ``COUNT`` para contar o número de produtos em cada categoria. O comando SQL ficaria assim:
```
SELECT categoria, COUNT(*) AS num_produtos
FROM produtos
GROUP BY categoria;
```

Este comando SQL retornará uma tabela com duas colunas: "categoria" e "num_produtos". A coluna "categoria" contém os nomes das categorias distintas presentes na tabela "produtos" e a coluna "num_produtos" contém o número de produtos em cada categoria.

- **Exemplo 2:** calcular o preço médio dos produtos em cada categoria:

Podemos usar a mesma tabela "produtos" do exemplo anterior para calcular o preço médio dos produtos em cada categoria. O comando SQL ficaria assim:

```
SELECT categoria, AVG(preco) AS preco_medio
FROM produtos
GROUP BY categoria;
```

Este comando SQL retornará uma tabela com duas colunas: "categoria" e "preco_medio". A coluna "categoria" contém os nomes das categorias distintas presentes na tabela "produtos" e a coluna "preco_medio" contém o preço médio dos produtos em cada categoria.

- **Exemplo 3:** encontrar a categoria com o preço máximo:

Podemos usar a tabela "produtos" novamente para encontrar a categoria com o preço máximo. O comando SQL ficaria assim:

```
SELECT categoria, MAX(preco) AS preco_maximo
FROM produtos
GROUP BY categoria
ORDER BY preco_maximo DESC
LIMIT 1;
```

Este comando SQL retornará uma tabela com duas colunas: "categoria" e "preco_maximo". A cláusula ``ORDER BY`` é usada para ordenar os resultados pelo preço máximo em ordem decrescente e a cláusula ``LIMIT`` é usada para limitar o número de resultados a 1 (ou seja, a categoria com o preço máximo).

### Cast

A função ``CAST`` em SQL é usada para converter um valor de um tipo de dados em outro tipo de dados. Isso é útil quando precisamos comparar ou manipular valores em diferentes tipos de dados, ou quando precisamos armazenar valores em um tipo de dados diferente.

O funcionamento da função ``CAST`` é simples: ela recebe dois argumentos, o valor a ser convertido e o tipo de dados para o qual ele deve ser convertido. A sintaxe básica da função ``CAST`` é a seguinte:

```
CAST(valor AS tipo_de_dados)
```

O primeiro argumento "valor" é o valor a ser convertido e o segundo argumento "tipo_de_dados" é o tipo de dados para o qual o valor deve ser convertido.

Aqui estão alguns exemplos de diferentes tipos de ``CAST``:

```
CAST de texto para número
SELECT CAST('10' AS INT);
```

Este comando SQL converterá a string "10" em um número inteiro e retornará o valor 10.

```
CAST de número para texto
SELECT CAST(10 AS VARCHAR);
```

Este comando SQL converterá o número 10 em uma string e retornará o valor "10".

```
CAST de data para texto
SELECT CAST(CURRENT_DATE AS VARCHAR);
```

Este comando SQL converterá a data atual em uma string e retornará o valor no formato "YYYY-MM-DD".

CAST de texto para data

```
SELECT CAST('2023-03-12' AS DATE);
```

Este comando SQL converterá a string "2023-03-12" em uma data e retornará o valor em formato de ``data``.

```
CAST de número para booleano
SELECT CAST(0 AS BOOLEAN);
Este comando SQL converterá o número 0 em um valor booleano e retornará o valor FALSE.
```