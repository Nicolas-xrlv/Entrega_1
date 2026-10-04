# Entrega_1
- Nicolas Souza Silva 48061875, Bruno Henrique, Guilherme Lucas

## 1. Caracterização da Organização

- **Nome e natureza da organização:** *qual organização real o grupo escolheu (com acesso garantido para pesquisa de campo) — pode ser uma empresa (livraria, lanchonete, pet shop), uma ONG, uma associação comunitária ou outra instituição.*
- **Contexto e porte:** *com ou sem fins lucrativos; tamanho da operação; número de pessoas envolvidas (funcionários, voluntários, membros, fiéis); volume de atividades (vendas, atendimentos, doações, rituais, eventos).*
- **Problemas e necessidades identificados:** *qual é a "crise operacional" — o que está desorganizado hoje (planilhas soltas, papel, falta de controle de estoque/doações/cadastros, etc.)?*
- **Justificativa da escolha:** *por que essa organização foi escolhida e por que ela é um bom caso para o projeto?*
- **Evidências da organização:** *comprove que a organização existe e que o grupo teve acesso a ela — ex.: fotos do local/da visita, link da organização no Google (Google Maps/Google Meu Negócio, site, rede social), endereço completo e forma de contato (telefone, e-mail, responsável pela organização).*

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

## 4. Regras de Negócio
*(esta seção DIVIDE com a Seção 3 "Requisitos do Sistema" os mesmos 7,5% da dimensão conceitual — juntas valem 7,5%, não 7,5% cada — + 4% exclusivos desta seção na documentação. "Regras de negócio" é o termo técnico usado em modelagem de dados para as regras de funcionamento de qualquer organização, com ou sem fins lucrativos)*

- **Regras operacionais:** *condições que a organização impõe (ex.: "um pedido só pode ser fechado se houver estoque disponível", "uma doação só pode ser registrada com identificação do doador", "um ritual só pode ser agendado se o espaço estiver disponível").*
- **Restrições organizacionais:** *limitações que afetam o modelo (ex.: políticas internas, prazos, exigências legais, normas religiosas ou estatutárias) — e por que elas importam.*

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
*(vale 7,5% — sozinho, é o subcritério de maior peso dentro da Dimensão Conceitual)*

*Explique e defenda as decisões de abstração e modelagem tomadas: por que essas entidades, esses atributos, esses relacionamentos e essas cardinalidades — e não outras alternativas possíveis?*

---

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
