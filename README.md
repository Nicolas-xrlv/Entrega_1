# Entrega_1
- Nicolas Souza Silva 48061875, Bruno Henrique, Guilherme Lucas

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
*(vale 10% — Dimensão Procedimental - Segue o modelo do arquivo 02-03g_Exemplo_Dicionario_Dados.pdf)*

Para cada entidade identificada, liste:

| Atributo | Descrição | Regra de negócio associada |
|----------|-----------|------------------------------|
| *nome do atributo* | *o que ele representa* | *se houver alguma regra (obrigatoriedade, valores possíveis, etc.)* |
| Atributo | Descrição | Regra de negócio associada |

Entidade: Produto
| Atributo     |           Descrição            | Regra de negócio associada |
|--------------|--------------------------------|----------------------------|
| ID_PRODUTO   | Identificador único do produto |Deve ser único e obrigatório|
| NM_PRODUTO   |         Nome do produto        | Regra de negócio associada |
| DESC_PRODUTO |       Descrição do produto     | Regra de negócio associada |
| PRECO        |     Preço de venda do produto  | Regra de negócio associada |

Entidade: Estoque
| Atributo       |                Descrição                        | Regra de negócio associada |
|----------------|-------------------------------------------------|----------------------------|
| ID_ESTOQUE     | Identificador único do registro de estoque      |Deve ser único e obrigatório|
| QNT_ESTOQUE    |  Quantidade disponível do produto em estoque    | Regra de negócio associada |
| DT_ATUALIZACAO |     Data da última atualização do estoque       | Regra de negócio associada |

Entidade: Fornecedor
| Atributo      |           Descrição                 | Regra de negócio associada |
|---------------|-------------------------------------|----------------------------|
| ID_FORNECEDOR |  Identificador único do fornecedor  |Deve ser único e obrigatório|
| NM_FORNECEDOR |  Nome ou razão social do fornecedor | Regra de negócio associada |
| TELEFONE      |  Telefone de contato do fornecedor  | Regra de negócio associada |
| EMAIL         |   E-mail de contato do fornecedor   | Regra de negócio associada |

Entidade: Venda
| Atributo     |           Descrição            | Regra de negócio associada |
|--------------|--------------------------------|----------------------------|
| ID_VENDA     | Identificador único da venda   |Deve ser único e obrigatório|
| DT_VENDA     |  Quanto a venda foi realizada  | Regra de negócio associada |
| VALOR_TOTAL  |     Valor total da venda       | Regra de negócio associada |
| PAGAMENTO    |  Forma de pagamento utilizada  | Regra de negócio associada |

Entidade: Compra
| Atributo      |           Descrição                   | Regra de negócio associada |
|---------------|---------------------------------------|----------------------------|
| ID_COMPRA     |    Identificador único da compra      |Deve ser único e obrigatório|
| DT_COMPRA     |  Data em que a compra foi realizada   | Regra de negócio associada |
| VALOR_COMPRA  |       Valor total da compra           | Regra de negócio associada |
| QUANTIDADE    |  Quantidade de produtos adquiridos    | Regra de negócio associada |




*Mantenha o dicionário organizado e padronizado (mesmo formato de tabela para todas as entidades).*

**Atenção à privacidade:** se forem usados exemplos de valores para ilustrar os atributos, esses exemplos devem ser **fictícios** — não utilize dados reais de clientes, fiéis, beneficiários, doadores ou funcionários da organização (nomes, CPFs, contatos etc.), mesmo que tenham sido observados durante a pesquisa de campo. Os exemplos devem apenas ser **coerentes com as operações reais** observadas.

---

## 6. Modelagem Conceitual (Entidades, Atributos, Relacionamentos)
*(vale 7,5% na dimensão conceitual)*

- **Entidades reconhecidas:** *liste e justifique brevemente cada uma.*
- **Atributos e classificações:** *quais atributos pertencem a cada entidade.*
- **Relacionamentos pertinentes:** *como as entidades se conectam.*
- **Restrições e políticas organizacionais aplicadas ao modelo.**

---

## 7. Diagrama Entidade-Relacionamento (DER)
*(vale 20% — é o item de maior peso da entrega)*

- Anexe o DER (em imagem).
- O diagrama deve representar corretamente:
  - Entidades
  - Atributos
  - Relacionamentos
  - **Cardinalidades**
- O modelo deve ser **consistente** e já demonstrar potencial de **escalabilidade e integração** (pensando nas próximas etapas do projeto).

---

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
