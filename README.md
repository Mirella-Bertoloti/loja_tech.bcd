# Loja Tech – Banco de Dados

## Sobre o Projeto

O **Loja Tech** é um projeto de banco de dados relacional desenvolvido para simular o gerenciamento de uma loja de produtos tecnológicos. O sistema foi construído utilizando MySQL e tem como objetivo organizar as principais informações de uma loja virtual, incluindo categorias, produtos, clientes, pedidos e operações realizadas no banco de dados.

O projeto também aborda a utilização de **Stored Procedures**, permitindo implementar funcionalidades, automatizar processos e aplicar regras de negócio diretamente no banco de dados.

A proposta é demonstrar, na prática, conceitos de modelagem relacional, integridade referencial, manipulação de dados, consultas SQL e programação no banco de dados.

## Objetivos

- Desenvolver um banco de dados relacional para uma loja de tecnologia.
- Organizar informações de produtos, categorias, clientes e pedidos.
- Implementar relacionamentos utilizando chaves primárias e estrangeiras.
- Trabalhar com comandos SQL para criação e manipulação de tabelas.
- Desenvolver Stored Procedures para automatizar operações.
- Aplicar estruturas condicionais, variáveis e parâmetros em procedimentos armazenados.
- Implementar validações e regras de negócio.
- Registrar operações realizadas para fins de auditoria.

## Tecnologias Utilizadas

- **MySQL:** Sistema de gerenciamento de banco de dados relacional utilizado para desenvolver e executar o projeto.
- **SQL:** Linguagem utilizada para criação, consulta, atualização e exclusão de dados.
- **Stored Procedures:** Recursos utilizados para armazenar e executar procedimentos diretamente no banco de dados.
- **MySQL Workbench:** Ferramenta para desenvolvimento, execução e gerenciamento dos scripts SQL.

## Estrutura do Banco de Dados

O banco de dados é composto por tabelas responsáveis por organizar as informações e estabelecer os relacionamentos necessários para o funcionamento da loja.

### Tabelas Principais

| Tabela | Descrição |
|---|---|
| `categorias` | Armazena as categorias dos produtos comercializados pela loja. |
| `produtos` | Contém os produtos disponíveis, seus preços, descrições e informações de estoque. |
| `clientes` | Armazena os dados cadastrais dos clientes. |
| `pedidos` | Registra os pedidos realizados pelos clientes. |
| `itens_pedido` | Armazena os produtos e as respectivas quantidades de cada pedido. |
| `log_operacoes` | Registra operações realizadas por procedimentos armazenados. |
| `cupons_desconto` | Armazena códigos promocionais e seus respectivos percentuais de desconto. |

### Relacionamentos

O banco de dados utiliza chaves primárias (Primary Keys) e chaves estrangeiras (Foreign Keys) para garantir a integridade e a consistência das informações.

Os principais relacionamentos são:

- **Categorias e Produtos:** Uma categoria pode possuir vários produtos, enquanto cada produto pertence a uma categoria.
- **Clientes e Pedidos:** Um cliente pode realizar vários pedidos, mas cada pedido pertence a um único cliente.
- **Pedidos e Itens do Pedido:** Um pedido pode possuir vários itens, e cada item está associado a um pedido.
- **Produtos e Itens do Pedido:** Um produto pode aparecer em diferentes pedidos, enquanto cada item referencia um produto específico.

Essa estrutura permite organizar as informações sem duplicar desnecessariamente os dados e facilita a realização de consultas envolvendo diferentes tabelas.

## Funcionalidades Implementadas

O projeto apresenta diferentes funcionalidades desenvolvidas por meio de comandos SQL e Stored Procedures.

### Gerenciamento de Produtos

- Cadastro de produtos.
- Consulta de produtos ativos.
- Busca de produtos por categoria.
- Atualização de preços.
- Controle de quantidade em estoque.
- Identificação de produtos com estoque baixo.
- Validação de informações durante o cadastro.

### Gerenciamento de Clientes

- Cadastro e armazenamento de informações dos clientes.
- Consulta de dados cadastrais.
- Identificação de clientes por seus identificadores.
- Consulta do histórico de pedidos.
- Cálculo de informações relacionadas às compras.

### Gerenciamento de Pedidos

- Registro de pedidos.
- Associação de pedidos aos respectivos clientes.
- Inclusão de produtos nos pedidos.
- Cálculo do valor total das compras.
- Controle dos diferentes status dos pedidos.
- Cancelamento de pedidos.
- Restauração automática do estoque após o cancelamento, conforme as regras implementadas.

### Controle de Estoque

- Consulta da quantidade disponível de produtos.
- Identificação de produtos com estoque reduzido.
- Cálculo do valor total armazenado em estoque.
- Atualização automática das quantidades durante as operações de pedidos.

### Cupons de Desconto

- Geração automática de códigos promocionais.
- Definição de percentuais de desconto.
- Armazenamento dos cupons no banco de dados.
- Controle de utilização dos códigos.

## Stored Procedures

Uma das principais partes do projeto é a implementação de Stored Procedures.

As Stored Procedures são procedimentos armazenados diretamente no banco de dados, permitindo executar conjuntos de instruções SQL por meio de uma única chamada.

Elas ajudam a centralizar regras de negócio, evitar a repetição de comandos e facilitar a execução de operações.

Entre os procedimentos desenvolvidos estão:

| Stored Procedure | Funcionalidade |
|---|---|
| `ola_mundo` | Demonstra a criação e execução de uma Stored Procedure simples. |
| `listar_produtos_ativos` | Lista os produtos ativos e apresenta informações sobre o estoque. |
| `resumo_estoque` | Apresenta informações estatísticas sobre os produtos e o estoque. |
| `buscar_produtos_por_categoria` | Consulta produtos de uma categoria específica. |
| `contar_pedidos_cliente` | Conta os pedidos de um cliente e determina sua classificação. |
| `aplicar_desconto` | Aplica um percentual de desconto sobre um preço. |
| `calcular_frete` | Calcula o valor do frete de acordo com o valor do pedido. |
| `descrever_status_pedido` | Retorna uma descrição correspondente ao status de um pedido. |
| `gerar_cupons` | Gera códigos promocionais automaticamente. |
| `cadastrar_produto` | Realiza o cadastro de produtos com validações. |
| `registrar_pedido` | Registra pedidos e processa seus itens. |
| `cancelar_pedido` | Cancela pedidos conforme as regras definidas e restaura o estoque. |

## Exercícios Práticos

O repositório também contém um arquivo específico com a resolução de exercícios sobre Stored Procedures.

As atividades trabalham situações práticas relacionadas ao gerenciamento da loja.

### Exercício 1 – Atualização de Preços por Categoria

Implementação da procedure `atualizar_preco_categoria`, responsável por atualizar os preços dos produtos de uma categoria específica.

A funcionalidade recebe o identificador da categoria e um percentual de ajuste, permitindo aumentos ou reduções de preços.

Também realiza validações, contabiliza os produtos modificados e registra a operação na tabela de logs.

### Exercício 2 – Extrato do Cliente

Implementação da procedure `consultar_extrato_cliente`, responsável por apresentar informações completas sobre as compras de um cliente.

A consulta retorna três conjuntos de resultados:

1. Dados cadastrais do cliente.
2. Histórico de pedidos realizados.
3. Resumo das compras, incluindo quantidade de pedidos, valor total gasto, ticket médio e data do último pedido.

O procedimento também verifica se o cliente informado existe antes de realizar as consultas.

## Estrutura de Arquivos

O repositório está organizado da seguinte maneira:

```text
loja_tech.bcd/
│
├── Banco de dados Loja Tech.sql
│
└── Resolução dos exercicios Loja Tech.sql
```

### Descrição dos Arquivos

**Banco de dados Loja Tech.sql**

Arquivo principal do projeto, responsável pela estruturação do banco de dados. Contém a criação das tabelas, relacionamentos, inserção de dados e exemplos de Stored Procedures utilizados para demonstrar as funcionalidades do sistema.

**Resolução dos exercicios Loja Tech.sql**

Arquivo destinado à resolução das atividades práticas. Contém as Stored Procedures desenvolvidas para atender aos requisitos dos exercícios propostos, incluindo atualização de preços por categoria e consulta de extrato de clientes.

## Como Executar o Projeto

Para executar o projeto, é necessário possuir o MySQL instalado e uma ferramenta de gerenciamento de banco de dados, como o MySQL Workbench.

### 1. Clonar o Repositório

Abra o terminal e execute:

```bash
git clone https://github.com/Mirella-Bertoloti/loja_tech.bcd.git
```

### 2. Acessar a Pasta

```bash
cd loja_tech.bcd
```

### 3. Abrir o MySQL Workbench

Abra o MySQL Workbench e conecte-se à sua instância do servidor MySQL.

### 4. Executar o Banco de Dados

Abra o arquivo:

```text
Banco de dados Loja Tech.sql
```

Execute o script para criar o banco de dados, suas tabelas, relacionamentos e demais estruturas.

### 5. Executar os Exercícios

Após a criação do banco de dados e das tabelas necessárias, abra o arquivo:

```text
Resolução dos exercicios Loja Tech.sql
```

Execute os procedimentos armazenados e os comandos de chamada para verificar os resultados.

**Observação:** O script principal utiliza `DROP DATABASE IF EXISTS`, portanto, sua execução recria o banco de dados e apaga uma versão anterior com o mesmo nome. Tenha cuidado caso já possua dados que deseja preservar.

## Conceitos de Banco de Dados Aplicados

Durante o desenvolvimento do projeto, foram trabalhados os seguintes conceitos:

- Banco de dados relacional.
- Criação e utilização de tabelas.
- Tipos de dados SQL.
- Chaves primárias e estrangeiras.
- Relacionamentos entre tabelas.
- Integridade referencial.
- Inserção, atualização e exclusão de registros.
- Consultas SQL.
- Junções entre tabelas (JOIN).
- Funções de agregação.
- Variáveis locais.
- Parâmetros `IN`, `OUT` e `INOUT`.
- Estruturas condicionais `IF`, `ELSEIF` e `ELSE`.
- Estrutura de repetição `WHILE`.
- Estrutura `CASE`.
- Tratamento de erros com `HANDLER`.
- Emissão de erros personalizados com `SIGNAL`.
- Auditoria de operações.
- Stored Procedures.
## Repositório

[Loja Tech – Banco de Dados](https://github.com/Mirella-Bertoloti/loja_tech.bcd)
