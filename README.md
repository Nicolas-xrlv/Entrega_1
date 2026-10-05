# Entrega_1
- Nicolas Souza Silva 48061875, Bruno Henrique Caballero Cayola 48134970, Guilherme Lucas Molina Ribeiro 48143413

## 1. Caracterização da Organização

Nome e natureza da organização: Adega LB

Contexto e porte: A Adega LB é uma organização com fins lucrativos que possui três estabelecimentos. Atualmente, a organização conta com 9 funcionários e 1 patrão, sendo três funcionários responsáveis pelas atividades de cada estabelecimento.

O funcionamento da organização ocorre de forma local em cada unidade. Entretanto, a gestão é centralizada pelo proprietário, que realiza o direcionamento das atividades de forma remota. A comunicação entre o proprietário e os três estabelecimentos ocorre por meio de aplicativos de mensagens instantâneas, como o WhatsApp.

Cada estabelecimento possui autonomia para organizar o atendimento e as atividades locais com seus respectivos funcionários, além de repassar à administração central as demandas do dia e informações relacionadas ao andamento das vendas. Dessa forma, existe uma divisão entre a operação local das unidades e o direcionamento centralizado realizado pelo proprietário.

Problemas e necessidades identificados: Durante a pesquisa de campo, foi identificada principalmente a falta de controle adequado do estoque e a ausência de um banco de dados para auxiliar na organização das informações da empresa.

Atualmente, parte da comunicação e do direcionamento das atividades entre a administração central e os estabelecimentos ocorre de forma remota por meio de aplicativos de mensagens instantâneas. Embora esse meio seja utilizado para a comunicação das demandas e do andamento das vendas, a organização não possui um banco de dados estruturado para centralizar e organizar suas informações.

Diante disso, identifica-se a necessidade de uma solução que possibilite uma melhor organização das informações relacionadas às operações da Adega LB, principalmente no que diz respeito ao controle de estoque e à centralização dos dados.

Justificativa da escolha: A Adega LB foi escolhida para o desenvolvimento do projeto principalmente pela facilidade de acesso à organização, o que possibilita a realização da pesquisa de campo e a observação de seu funcionamento real.

Além disso, a organização apresenta planos futuros de expansão, tornando relevante a análise de sua estrutura atual e a proposição de uma modelagem de banco de dados que possa contribuir para uma melhor organização das informações. A existência de três estabelecimentos e de uma administração centralizada também torna a organização um caso adequado para estudar a necessidade de centralização e organização dos dados.

Link endereço:https://maps.app.goo.gl/VWwuUbpVrpduc8Wv6

Endereço: Av. Domingos de Mendonça, 204 - Jardim Maria Lidia, São Paulo - SP, 08370-420

Forma de contato: Responsável pela organização

---

## 2. Processos de Negócio

Cadastro de produtos: processo responsável pelo registro das informações dos produtos comercializados pela distribuidora, incluindo nome, categoria, preço e quantidade disponível.

Controle de estoque: processo utilizado para acompanhar as entradas e saídas de produtos, permitindo identificar a quantidade disponível e a necessidade de reposição.

Compra de mercadorias: processo iniciado quando é identificada a necessidade de reposição de produtos.

Realização de vendas: processo iniciado pela solicitação de produtos pelo cliente. O funcionário verifica a disponibilidade, registra os produtos, calcula o valor da compra, registra o pagamento e finaliza a venda.

Atualização do estoque: após a realização de uma venda ou recebimento de mercadorias, as quantidades disponíveis são atualizadas de acordo com a movimentação realizada.

---

## 3. Requisitos do Sistema

### 3.1 Requisitos Funcionais

1- O sistema deve permitir o cadastro de produtos

2- O sistema deve permitir a alterar as informações cadastradas de um produto

3- O sistema deve permitir consultar os produtos cadastrados e suas informações

4- O sistema deve permitir registrar entradas e saídas de produtos no estoque

5- O sistema deve permitir registrar compras realizadas para o estoque

6- O sistema deve permitir o registro de vendas realizadas para o cliente

7- O sistema deve permitir consultar as vendas realizadas


### 3.2 Requisitos Não Funcionais
Usabilidade, desempenho, disponibilidade, integridade e segurança

---

## 4.Regras de Negócio

Regras operacionais
Cada estabelecimento realiza suas atividades de forma autônoma, com seus respectivos funcionários.
As demandas e o andamento das vendas de cada estabelecimento são repassados à administração centralizada.
O proprietário realiza o direcionamento das atividades dos três estabelecimentos de forma remota, utilizando aplicativos de mensagens instantâneas.
O controle de estoque é uma necessidade identificada na organização, porém as regras específicas utilizadas atualmente para entrada, saída e reposição de produtos precisam ser confirmadas com a organização.
Restrições organizacionais
A administração é centralizada no proprietário: o proprietário realiza o direcionamento remoto das atividades dos três estabelecimentos. Isso importa para o modelo de dados porque pode ser necessário representar a relação entre a administração central e cada estabelecimento.
Cada estabelecimento possui operação local própria: os estabelecimentos possuem autonomia para organizar o atendimento e as atividades locais com seus respectivos funcionários. Isso importa para o modelo de dados porque as informações das operações podem precisar ser associadas ao estabelecimento em que ocorreram.
A comunicação entre os estabelecimentos e a administração ocorre remotamente por aplicativos de mensagens instantâneas: essa é a forma atualmente utilizada para o direcionamento e o repasse das demandas. Isso importa para o modelo de dados porque evidencia a necessidade de avaliar quais informações atualmente comunicadas de forma descentralizada deverão ser estruturadas e centralizadas no sistema.
A organização não possui atualmente um banco de dados estruturado: essa condição foi identificada durante a pesquisa de campo. Isso importa para o modelo porque o sistema deverá organizar as informações que atualmente não estão centralizadas em uma estrutura de dados.


---

## 5. Dicionário de Dados Conceitual (Preliminar)

Entidade: Cliente
| Atributo   | Descrição                                             | Regra de negócio associada                                                  |
| ---------- | ----------------------------------------------------- | --------------------------------------------------------------------------- |
| ID_CLIENTE | Identificador único do cliente                        | Deve ser único e obrigatório                                                |
| NOME       | Nome ou razão social do cliente                       | Deve ser informado no cadastro                                              |
| CPF_CNPJ   | Documento de identificação do cliente                 | Deve ser informado de acordo com o tipo de cliente e não deve ser duplicado |
| TIPO       | Indica se o cliente é pessoa física ou jurídica       | Deve assumir valores previamente definidos, como PF ou PJ                   |
| TELEFONE   | Número de telefone para contato com o cliente         | Deve ser armazenado em formato adequado para contato                        |
| EMAIL      | Endereço de e-mail do cliente                         | Quando informado, deve possuir formato válido                               |
| ENDERECO   | Endereço cadastrado do cliente                        | Deve ser informado quando necessário para as operações da distribuidora     |
| STATUS     | Indica se o cadastro do cliente está ativo ou inativo | Deve permitir identificar clientes ativos e inativos                        |

Entidade: Produto
| Atributo     | Descrição                                                | Regra de negócio associada                                                          |
| ------------ | -------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| ID_PRODUTO   | Identificador único do produto                           | Deve ser único e obrigatório                                                        |
| NOME_PRODUTO | Nome comercial do produto                                | Deve ser informado e permitir identificar o produto de forma clara                  |
| DESCRICAO    | Informações complementares sobre o produto               | Pode conter características como marca, tipo ou outras informações relevantes       |
| ID_CATEGORIA | Identificador da categoria à qual o produto pertence     | Deve referenciar uma categoria existente                                            |
| PRECO_VENDA  | Preço de venda do produto ao cliente                     | Não pode ser negativo e deve representar o preço praticado pela distribuidora/adega |
| ATIVO        | Indica se o produto está disponível para comercialização | Deve permitir identificar produtos ativos e inativos                                |


Entidade: Categoria
| Atributo       | Descrição                                   | Regra de negócio associada                                                      |
| -------------- | ------------------------------------------- | ------------------------------------------------------------------------------- |
| ID_CATEGORIA   | Identificador único da categoria            | Deve ser único e obrigatório                                                    |
| NOME_CATEGORIA | Nome da categoria de produtos               | Deve ser informado e não deve gerar categorias duplicadas com o mesmo propósito |
| DESCRICAO      | Descrição da categoria                      | Pode apresentar informações sobre os produtos que pertencem à categoria         |
| STATUS         | Indica se a categoria está ativa ou inativa | Categorias inativas não devem ser utilizadas para novos cadastros de produtos   |


Entidade: Fornecedor
| Atributo        | Descrição                                          | Regra de negócio associada                                                                     |
| --------------- | -------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| ID_FORNECEDOR   | Identificador único do fornecedor                  | Deve ser único e obrigatório                                                                   |
| NOME_FORNECEDOR | Nome ou razão social do fornecedor                 | Deve ser informado no cadastro                                                                 |
| CNPJ            | Cadastro Nacional da Pessoa Jurídica do fornecedor | Deve identificar o fornecedor de forma única e ser informado para fornecedores pessoa jurídica |
| TELEFONE        | Número de telefone para contato com o fornecedor   | Deve ser armazenado em formato adequado para contato                                           |
| EMAIL           | Endereço de e-mail do fornecedor                   | Quando informado, deve possuir formato válido                                                  |
| ENDERECO        | Endereço do fornecedor                             | Deve ser registrado para fins cadastrais e operacionais                                        |
| STATUS          | Indica se o fornecedor está ativo ou inativo       | Fornecedores inativos não devem ser utilizados em novas compras                                |


Entidade: Funcionário
| Atributo       | Descrição                                     | Regra de negócio associada                                    |
| -------------- | --------------------------------------------- | ------------------------------------------------------------- |
| ID_FUNCIONARIO | Identificador único do funcionário            | Deve ser único e obrigatório                                  |
| NOME           | Nome do funcionário                           | Deve ser informado no cadastro                                |
| CPF            | Cadastro de Pessoa Física do funcionário      | Deve identificar o funcionário de forma única                 |
| CARGO          | Cargo ou função exercida pelo funcionário     | Deve representar a função desempenhada na distribuidora/adega |
| DATA_ADMISSAO  | Data de admissão do funcionário               | Deve representar uma data válida de contratação               |
| TELEFONE       | Número de telefone do funcionário             | Deve ser armazenado em formato adequado para contato          |
| STATUS         | Indica se o funcionário está ativo ou inativo | Funcionários inativos não devem registrar novas vendas        |

Entidade: Venda
| Atributo        | Descrição                                                       | Regra de negócio associada                                                      |
| --------------- | --------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| ID_VENDA        | Identificador único da venda                                    | Deve ser único e obrigatório                                                    |
| ID_CLIENTE      | Identificador do cliente relacionado à venda                    | Deve referenciar um cliente existente                                           |
| ID_FUNCIONARIO  | Identificador do funcionário responsável pelo registro da venda | Deve referenciar um funcionário existente e ativo                               |
| DATA_VENDA      | Data em que a venda foi realizada                               | Deve representar uma data válida da operação                                    |
| FORMA_PAGAMENTO | Forma de pagamento utilizada na venda                           | Deve utilizar formas de pagamento aceitas pela distribuidora/adega              |
| VALOR_TOTAL     | Valor total da venda                                            | Deve corresponder à soma dos valores dos itens da venda e não pode ser negativo |

Entidade: Item_Venda
| Atributo       | Descrição                                                          | Regra de negócio associada                                                        |
| -------------- | ------------------------------------------------------------------ | --------------------------------------------------------------------------------- |
| ID_ITEM_VENDA  | Identificador único do item da venda                               | Deve ser único e obrigatório                                                      |
| ID_VENDA       | Identificador da venda à qual o item pertence                      | Deve referenciar uma venda existente                                              |
| ID_PRODUTO     | Identificador do produto vendido                                   | Deve referenciar um produto existente e ativo                                     |
| QUANTIDADE     | Quantidade do produto incluída na venda                            | Deve ser maior que zero e não pode ultrapassar a quantidade disponível no estoque |
| PRECO_UNITARIO | Preço unitário do produto no momento da venda                      | Não pode ser negativo e deve representar o preço aplicado na operação             |
| SUBTOTAL       | Valor correspondente à quantidade multiplicada pelo preço unitário | Deve ser calculado de acordo com a quantidade e o preço unitário do item          |

Entidade: Compra
| Atributo        | Descrição                                           | Regra de negócio associada                                                       |
| --------------- | --------------------------------------------------- | -------------------------------------------------------------------------------- |
| ID_COMPRA       | Identificador único da compra                       | Deve ser único e obrigatório                                                     |
| ID_FORNECEDOR   | Identificador do fornecedor relacionado à compra    | Deve referenciar um fornecedor existente e ativo                                 |
| DATA_COMPRA     | Data em que a compra foi realizada                  | Deve representar uma data válida da operação                                     |
| VALOR_TOTAL     | Valor total da compra realizada junto ao fornecedor | Deve corresponder à soma dos valores dos itens da compra e não pode ser negativo |
| FORMA_PAGAMENTO | Forma de pagamento utilizada na compra              | Deve representar uma forma de pagamento aceita pela empresa                      |

Entidade: Item_Compra
| Atributo       | Descrição                                                          | Regra de negócio associada                                               |
| -------------- | ------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| ID_ITEM_COMPRA | Identificador único do item da compra                              | Deve ser único e obrigatório                                             |
| ID_COMPRA      | Identificador da compra à qual o item pertence                     | Deve referenciar uma compra existente                                    |
| ID_PRODUTO     | Identificador do produto adquirido                                 | Deve referenciar um produto existente                                    |
| QUANTIDADE     | Quantidade do produto adquirida na compra                          | Deve ser maior que zero                                                  |
| PRECO_UNITARIO | Preço unitário pago pelo produto na compra                         | Não pode ser negativo                                                    |
| SUBTOTAL       | Valor correspondente à quantidade multiplicada pelo preço unitário | Deve ser calculado de acordo com a quantidade e o preço unitário do item |

Entidade: Estoque
| Atributo         | Descrição                                             | Regra de negócio associada                                                                     |
| ---------------- | ----------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| ID_ESTOQUE       | Identificador único do registro de estoque            | Deve ser único e obrigatório                                                                   |
| ID_PRODUTO       | Identificador do produto associado ao estoque         | Deve referenciar um produto existente e cada produto deve possuir um único registro de estoque |
| QUANTIDADE_ATUAL | Quantidade disponível do produto em estoque           | Não pode ser negativa e deve ser atualizada após compras e vendas                              |
| LOCALIZACAO      | Local onde o produto está armazenado                  | Deve identificar a localização utilizada para controle do estoque                              |
| DATA_ATUALIZACAO | Data da última atualização das informações do estoque | Deve ser atualizada sempre que houver alteração na quantidade ou nas informações de estoque    |

Informações levantadas a partir da pesquisa de campo:

A análise da empresa teve como foco as atividades de compra, armazenamento e venda de bebidas, considerando tanto o atendimento aos clientes quanto o abastecimento do estoque. A partir da observação dessas atividades, foram identificadas as principais informações necessárias para representar o funcionamento da empresa no banco de dados.

No processo de cadastro de produtos, é necessário registrar informações como nome do produto, descrição, categoria e preço de venda. A utilização de categorias permite organizar produtos com características semelhantes, como vinhos, cervejas, destilados e bebidas não alcoólicas, facilitando sua identificação e comercialização.

No controle de estoque, é necessário acompanhar a quantidade disponível de cada produto e a data da última atualização. As entradas de produtos ocorrem principalmente por meio das compras realizadas com fornecedores, enquanto as saídas ocorrem durante as vendas realizadas aos clientes. Dessa forma, uma compra aumenta a quantidade disponível em estoque e uma venda reduz essa quantidade.

No processo de compra, são registradas informações referentes ao fornecedor, à data da operação, à forma de pagamento e aos produtos adquiridos. Como uma mesma compra pode conter vários produtos, foi criada a entidade Item_Compra, responsável por registrar o produto, a quantidade adquirida, o preço unitário e o subtotal de cada item.

No processo de venda, são registrados o cliente, o funcionário responsável pelo atendimento ou registro da operação, a data da venda, a forma de pagamento e os produtos comercializados. Como uma venda também pode conter vários produtos diferentes, foi criada a entidade Item_Venda, permitindo registrar individualmente a quantidade, o preço unitário e o subtotal de cada produto vendido.

A separação entre Venda e Item_Venda e entre Compra e Item_Compra foi adotada para evitar que uma mesma operação precise armazenar vários produtos em um único registro. Dessa forma, o modelo consegue representar, por exemplo, uma venda contendo diferentes tipos de bebidas, cada uma com sua respectiva quantidade e preço.

Também foi considerada a necessidade de manter o cadastro de clientes, fornecedores e funcionários, pois esses dados estão diretamente relacionados às operações da empresa. Clientes são associados às vendas, fornecedores às compras e funcionários às vendas realizadas ou registradas.


## 6. Modelagem Conceitual (Entidades, Atributos e Relacionamentos)

### Entidades reconhecidas e justificativas

| Entidade        | Justificativa                                                                                                                 |
| --------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| **Cliente**     | Representa as pessoas físicas ou jurídicas que realizam compras na distribuidora.                                             |
| **Produto**     | Representa as bebidas e os demais produtos comercializados pela distribuidora.                                                |
| **Categoria**   | Organiza os produtos em grupos, facilitando sua classificação e consulta.                                                     |
| **Fornecedor**  | Representa as empresas responsáveis pelo fornecimento dos produtos.                                                           |
| **Funcionário** | Representa os funcionários responsáveis pelas atividades da distribuidora, incluindo o registro das vendas.                   |
| **Venda**       | Registra as vendas realizadas pela distribuidora, identificando o cliente, o funcionário responsável e os valores envolvidos. |
| **Item_Venda**  | Registra os produtos e as respectivas quantidades e preços que compõem cada venda.                                            |
| **Compra**      | Registra as compras realizadas junto aos fornecedores.                                                                        |
| **Item_Compra** | Registra os produtos, as quantidades e os preços que compõem cada compra.                                                     |
| **Estoque**     | Controla a quantidade disponível de cada produto na distribuidora, permitindo acompanhar sua movimentação.                    |

### Atributos e classificações

Os atributos representam as informações armazenadas em cada entidade. Os identificadores são utilizados como chaves primárias (PK), enquanto os campos que estabelecem vínculos entre entidades são chaves estrangeiras (FK).

* **Cliente:** id_cliente (PK), nome, cpf_cnpj, tipo, telefone, email, endereco, status.
* **Produto:** id_produto (PK), nome_produto, descricao, id_categoria (FK), preco_venda, ativo.
* **Categoria:** id_categoria (PK), nome_categoria, descricao, status.
* **Fornecedor:** id_fornecedor (PK), nome_fornecedor, cnpj, telefone, email, endereco, status.
* **Funcionário:** id_funcionario (PK), nome, cpf, cargo, data_admissao, telefone, status.
* **Venda:** id_venda (PK), id_cliente (FK), id_funcionario (FK), data_venda, forma_pagamento, valor_total.
* **Item_Venda:** id_item_venda (PK), id_venda (FK), id_produto (FK), quantidade, preco_unitario, subtotal.
* **Compra:** id_compra (PK), id_fornecedor (FK), data_compra, valor_total, forma_pagamento.
* **Item_Compra:** id_item_compra (PK), id_compra (FK), id_produto (FK), quantidade, preco_unitario, subtotal.
* **Estoque:** id_estoque (PK), id_produto (FK), quantidade_atual, localizacao, data_atualizacao.

### Relacionamentos e cardinalidades

Os relacionamentos representam as associações entre as entidades do sistema. As cardinalidades indicam quantas ocorrências de uma entidade podem estar associadas a uma ocorrência da outra.

| Relacionamento            | Cardinalidade | Descrição                                                                                                            |
| ------------------------- | ------------- | -------------------------------------------------------------------------------------------------------------------- |
| **Categoria — Produto**   | 1:N           | Uma categoria pode possuir vários produtos, enquanto cada produto pertence a uma única categoria.                    |
| **Produto — Estoque**     | 1:1           | Cada produto possui um registro de estoque, e cada registro de estoque está associado a um único produto.            |
| **Cliente — Venda**       | 1:N           | Um cliente pode realizar várias vendas ao longo do tempo, enquanto cada venda está vinculada a um único cliente.     |
| **Funcionário — Venda**   | 1:N           | Um funcionário pode registrar várias vendas, enquanto cada venda é registrada por um único funcionário.              |
| **Venda — Item_Venda**    | 1:N           | Uma venda deve possuir um ou mais itens, enquanto cada item de venda pertence a uma única venda.                     |
| **Produto — Item_Venda**  | 1:N           | Um produto pode aparecer em vários itens de venda, enquanto cada item de venda se refere a um único produto.         |
| **Fornecedor — Compra**   | 1:N           | Um fornecedor pode estar relacionado a várias compras, enquanto cada compra é realizada junto a um único fornecedor. |
| **Compra — Item_Compra**  | 1:N           | Uma compra deve possuir um ou mais itens, enquanto cada item de compra pertence a uma única compra.                  |
| **Produto — Item_Compra** | 1:N           | Um produto pode aparecer em vários itens de compra, enquanto cada item de compra se refere a um único produto.       |

Os relacionamentos entre **Venda e Produto** e entre **Compra e Produto** são representados pelas entidades associativas **Item_Venda** e **Item_Compra**, respectivamente. Dessa forma, uma venda ou compra pode conter vários produtos, e um mesmo produto pode participar de várias vendas e compras.

O vínculo entre **Fornecedor e Produto** também pode ser identificado por meio dos registros de compra e seus itens. Assim, não é necessário criar um relacionamento direto adicional entre essas entidades no DER apresentado.

### Restrições e políticas organizacionais

* Cada entidade possui um identificador único, utilizado como chave primária.
* As chaves estrangeiras devem referenciar registros existentes nas entidades relacionadas.
* Uma venda deve possuir pelo menos um item, e uma compra também deve possuir pelo menos um item.
* A quantidade de produtos vendidos ou comprados deve ser maior que zero.
* Preços e valores monetários não podem ser negativos.
* O registro de uma venda deve reduzir a quantidade disponível dos produtos correspondentes no estoque.
* O registro de uma compra deve aumentar a quantidade disponível dos produtos correspondentes no estoque.
* Todo produto deve estar vinculado a uma categoria.
* Cada produto deve possuir um registro de estoque, conforme o relacionamento 1:1 definido no modelo.
* Os itens de venda e de compra devem estar vinculados a um produto existente.
* Os valores de subtotal e total devem corresponder às quantidades e aos preços registrados nos respectivos itens.
* Clientes, fornecedores, funcionários, produtos e categorias podem possuir um status para indicar se estão ativos ou inativos.
* Dados pessoais e cadastrais devem ser armazenados somente quando necessários para as operações da distribuidora.
* Os exemplos utilizados no projeto devem ser fictícios e não devem representar dados reais de clientes, funcionários ou fornecedores.

  

## 7. Diagrama Entidade-Relacionamento (DER)

<img width="1835" height="1634" alt="Untitled" src="https://github.com/user-attachments/assets/2c0cbd8c-ed4a-4a46-917c-48c58a8705b0" />


## 8. Justificativa Técnica

A modelagem conceitual foi desenvolvida a partir dos processos observados na Adega LB, considerando principalmente o cadastro de produtos, o controle de estoque, a compra de mercadorias, a realização de vendas e a atualização do estoque.

A entidade **Produto** foi definida por representar os produtos comercializados pela organização. A entidade **Estabelecimento** foi considerada necessária para diferenciar as três unidades da Adega LB e permitir associar as operações ao local em que são realizadas.

A entidade **Estoque** foi incluída devido à necessidade identificada de melhorar o controle das quantidades disponíveis de produtos. Essa estrutura permite representar o acompanhamento das movimentações de entrada e saída de mercadorias.

As entidades **Compra** e **Fornecedor** foram utilizadas para representar o processo de aquisição de mercadorias para reposição do estoque. A inclusão de **Item_Compra** permite representar os diferentes produtos que podem fazer parte de uma mesma compra.

Da mesma forma, a entidade **Venda** representa as operações realizadas pelos estabelecimentos, enquanto **Item_Venda** permite representar os produtos pertencentes a cada venda. Essa separação evita associar uma única venda diretamente a apenas um produto e permite representar vendas que contenham diferentes produtos.

A entidade **Cliente** deverá ser mantida no modelo caso o cadastro de clientes seja confirmado como parte efetiva das operações da Adega LB.

Os relacionamentos foram definidos de acordo com os processos levantados, buscando representar a relação entre estabelecimentos, produtos, estoque, compras, fornecedores e vendas. As cardinalidades do DER deverão refletir as regras observadas na organização e deverão ser confirmadas quando houver informações ainda não levantadas.

A modelagem também considera a necessidade de centralização das informações, uma vez que a Adega LB possui três estabelecimentos e uma administração centralizada. Dessa forma, a estrutura proposta busca organizar os dados das diferentes unidades em um modelo único, mantendo a identificação do estabelecimento responsável por cada operação.

## 9. Uso de Inteligência Artificial

Se o grupo usou alguma ferramenta de IA (ChatGPT, Claude, Gemini, Perplexity etc.) em qualquer parte do trabalho, registre **para cada uso relevante**:

| Item | O que registrar |
|------|------------------|
| **Ferramenta e etapa** | ChatGPT, apoio à organização da Entrega 1, análise da estrutura do dicionário de dados, discussão das entidades, atributos, relacionamentos e cardinalidades e revisão da documentação. |
| **Motivação** | Utilizar a IA como apoio para compreender a estrutura exigida pela atividade, organizar as informações já levantadas pelo grupo e identificar possíveis inconsistências na modelagem. |
| **Prompt(s) utilizados** | Exemplos: “Use esse arquivo como base e me diga exatamente o que já está pronto, o que falta na Entrega 1 e o que precisa ser corrigido”. |
| **Resposta recebida** | A IA analisou o material fornecido pelo grupo, identificou as partes já existentes e as partes ausentes e auxiliou na organização da Entrega 1. |
| **Fontes consultadas e verificadas** | A IA não citou fontes/dados. |
| **Trechos rejeitados ou corrigidos** | Sugestões que não correspondiam a realidade observada na organização foram descartadas pelo grupo. |
| **Justificativa da escolha final** | As decisões finais de modelagem foram tomadas pelo grupo com base na coerência entre requisitos, regras de negócio, dicionário de dados e DER que a IA sugeriu. |
| **Reflexão crítica** | A IA foi utilizada como ferramenta de apoio e não como substituta da pesquisa de campo, ocorreram vários erros e alucinações e percebemos que todo cuidado é pouco ao utilizar a Inteligência Artificial em documentos importantes como esse, todo o processo deve ser monitorado e verificado ponta a ponta, evitando ao máximo possível os problemas causados pela mesma  |

---

**Entrega final:** README.md completo + DER + Dicionário de Dados em HTML (com exceção dos cursos GTI) anexado no repositório GitHub do grupo.
