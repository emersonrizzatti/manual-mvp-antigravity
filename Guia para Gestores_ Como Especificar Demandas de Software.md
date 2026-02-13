# **Como Especificar Demandas de Software**

**Objetivo deste documento:** Ajudar você a transformar sua necessidade de negócio em instruções claras para a equipe de desenvolvimento, minimizando erros e garantias de que o software entregue resolva o problema real.

Não esperamos que você escreva código, mas precisamos entender **o quê** deve ser feito e **por que**. O **como** (a parte técnica) deixe com a gente.

---

### **Passo 1: Defina o "Porquê" (A Visão Macro)**

Antes de pedir um botão ou uma tela, descreva o problema. Desenvolvedores criam soluções melhores quando entendem a dor do usuário.

* **Qual é o problema atual?** (Ex: "O cálculo de impostos na nota fiscal demora muito e gera erros manuais.")  
* **Qual o resultado esperado?** (Ex: "Automatizar o cálculo para eliminar erros e reduzir o tempo de emissão em 50%.")  
* **Quem vai usar?** (Ex: "O analista financeiro e o gerente de compras.")

**Dica:** Tente usar o formato de "História de Usuário": *"Como \[Cargo/Usuário\], eu quero \[Ação no sistema\], para que \[Benefício/Valor\]."*

---

### **Passo 2: Desenhe o Fluxo (O Caminho do Usuário)**

Descreva o passo a passo do processo como ele deve acontecer. Não se preocupe com termos técnicos, foque na lógica do dia a dia.

**Perguntas para guiar o desenho do fluxo:**

1. **Gatilho:** O que inicia esse processo? (Ex: O cliente faz um pedido).  
2. **Caminho Feliz:** Se tudo der certo, qual a sequência de etapas?  
   * *Ex: Pedido entra \-\> Sistema verifica estoque \-\> Sistema bloqueia item \-\> Financeiro aprova \-\> Nota emitida.*  
3. **Caminho de Exceção (Muito Importante):** E se der errado?  
   * *Ex: E se não tiver estoque? O sistema avisa quem? O pedido fica pendente ou é cancelado?*

**Ferramenta sugerida:** Você pode usar ferramentas como Miro, Draw.io, ou até mesmo desenhar em um papel e tirar foto (ou usar o quadro branco). O importante são as caixas e as setas indicando a direção.

---

### **Passo 3: Regras de Negócio (As Leis do Sistema)**

Aqui é onde mora a complexidade. Regras de negócio são as restrições e lógicas que o sistema deve obedecer obrigatoriamente. Seja específico.

**Exemplos de como escrever:**

* **Ruim:** "O sistema deve calcular o imposto corretamente."  
* **Bom:** "Se o fornecedor for de São Paulo e o produto for 'Serviço', a alíquota de ISS deve ser 5%. Se for de fora do estado, a alíquota é 2%."  
* **Ruim:** "A senha tem que ser segura."  
* **Bom:** "A senha deve ter no mínimo 8 caracteres, uma letra maiúscula e um caractere especial."

Liste todas as validações, cálculos obrigatórios e permissões de acesso (quem pode ver ou editar o quê).

---

### **Passo 4: Critérios de Aceite (A Definição de "Pronto")**

Como saberemos que o trabalho acabou e está correto? Liste os critérios objetivos que você usará para aprovar a entrega.

* Exemplo 1: "Consigo cadastrar um fornecedor sem CPF e o sistema impede o salvamento mostrando mensagem de erro em vermelho."  
* Exemplo 2: "Ao exportar o relatório em PDF, o logotipo da empresa deve aparecer no cabeçalho."

  ---

### **Passo 5: Protótipo (Opcional, mas recomendado)**

Se você tem uma ideia visual, faça um "rabiscoframe" (wireframe feito à mão).

* Onde você imagina que ficam os filtros?  
* Quais colunas devem aparecer na tabela?  
* O que deve ter destaque na tela?

  ---

### **Modelo de Documentação (Template para Copiar e Colar)**

Para facilitar, use este modelo:

**Título do Projeto:** \[Nome curto\]

**1\. Contexto e Objetivo:** \[Explique brevemente por que precisamos disso\]

**2\. Fluxo do Processo:**

1. Usuário clica em...  
2. Sistema exibe...  
3. Se usuário escolher X, acontece Y...

**3\. Regras de Negócio Obrigatórias:**

* \[Regra 1\]  
* \[Regra 2\]  
* \[Cálculo específico\]

**4\. Critérios de Aceite:**

* \[ \] O sistema deve bloquear X quando Y...  
* \[ \] O cálculo final deve bater com a planilha em anexo...

**Anexos:** \[Prints de telas atuais, planilhas de exemplo, leis ou normas\]

---

### **Dica de Ouro**

**Evite dizer "É simples, é só um botão".** Um botão visível na tela pode disparar 15 verificações no banco de dados, enviar 2 emails e integrar com a Receita Federal. Foque em descrever a **necessidade**, e deixe a equipe técnica estimar a **complexidade**.

### **Exemplo Prático Preenchido: Módulo de Estoque (Adega)**

**Título da Demanda:** Sincronização de Estoque (Loja Física vs. Site)

**1\. Contexto e Objetivo:** Hoje, temos o problema de vender um vinho raro no site que acabou de ser vendido no balcão, gerando cancelamento de pedidos e frustração do cliente. O objetivo é que o estoque seja unificado em tempo real. Se passar no caixa, sai do site imediatamente.

**2\. Fluxo do Processo (Cenário: Venda de um Kit de Gin):**

1. O caixa bipa o código de barras de um "Kit Gin Tônica" (1 Garrafa de Gin \+ 4 Águas Tônicas) no PDV da loja física.  
2. O sistema identifica os componentes do Kit.  
3. O sistema dá baixa de 1 unidade de Gin e 4 unidades de Tônica no estoque geral.  
4. O sistema envia um sinal imediato para o E-commerce atualizando a quantidade disponível desses itens individuais.  
5. Se o estoque do Gin chegar a zero, o E-commerce marca o produto como "Esgotado" e impede a compra.

**3\. Regras de Negócio Obrigatórias:**

* **Regra do "Kit":** O estoque não é do Kit fechado, mas sim dos itens individuais. Ao vender um kit, deve-se descontar os insumos.  
* **Reserva de Carrinho (Site):** Se um cliente online colocar a última garrafa no carrinho, o sistema deve reservar esse item por 15 minutos. Nesse tempo, o caixa da loja física deve receber um alerta se tentar vender a mesma garrafa ("Item em negociação online").  
* **Alerta de Estoque Mínimo:** Quando a cerveja marca X chegar a 5 caixas, o sistema deve enviar um e-mail para o gerente de compras e destacar a linha em vermelho no painel.  
* **Quebra/Consumo Interno:** Deve haver um botão de "Baixa por Quebra" (garrafa quebrada) ou "Degustação", que desconta do estoque mas não entra como receita financeira, entrando como "Despesa de Marketing" ou "Perda".

**4\. Critérios de Aceite (Como vou testar se funcionou):**

* \[ \] Vender a última unidade de um vinho no caixa e verificar se, em menos de 10 segundos, ele aparece como "Esgotado" no site.  
* \[ \] Tentar vender um produto com saldo zero no caixa; o sistema deve pedir uma senha de gerente para autorizar (venda negativa/furo de estoque).  
* \[ \] Ao vender um Kit, conferir no relatório se descontou os itens individuais corretamente.

  ---

  ### **O "Interrogatório" do P.O. (Perguntas Cruciais)**

Muitas vezes o gestor não sabe escrever as regras acima espontaneamente. Você deve guiá-lo com estas perguntas para "fechar as pontas soltas":

#### **1\. Sobre Conflitos e Concorrência (Race Conditions)**

*"Se o Zé pegar a última garrafa na prateleira e estiver na fila do caixa, e ao mesmo tempo a Maria comprar essa garrafa no site, quem ganha? O sistema prioriza a venda online ou bloqueia o site?"*

* **Por que perguntar:** Define a hierarquia de canais de venda.

  #### **2\. Sobre Unidades de Medida e Conversão**

*"Vocês compram em caixas de 12 unidades, mas vendem a garrafa avulsa. O sistema deve dar entrada automática de 12 unidades ao ler a nota fiscal da caixa, ou vocês vão cadastrar manualmente? E se venderem a caixa fechada para um cliente, tem desconto?"*

* **Por que perguntar:** Evita erros matemáticos no inventário e define a complexidade do cadastro de produtos.

  #### **3\. Sobre a "Venda Negativa"**

*"O sistema deve permitir vender algo que, na teoria, não tem no estoque (ex: o estoque está errado no computador, mas o produto está na mão do cliente)? Se permitir, o estoque fica negativo (-1) ou zera?"*

* **Por que perguntar:** Define a rigidez do sistema. Bloquear a venda irrita o cliente; permitir a venda gera furo no controle.

  #### **4\. Sobre Preços Diferenciados**

*"O preço do site é o mesmo da loja física? Se eu alterar o preço no sistema principal, ele deve replicar para o site e para o iFood automaticamente, ou o iFood tem uma margem de \+10% automática?"*

* **Por que perguntar:** Define regras de integração e precificação dinâmica.

  #### **5\. Sobre Devolução e Troca (O "Caminho Infeliz")**

*"Se o cliente comprou online e veio trocar na loja física por um produto mais caro, como o sistema lida com essa diferença financeira e com a volta do item para a prateleira?"*

* **Por que perguntar:** É onde a maioria dos sistemas falha. O fluxo reverso é complexo.

  #### **6\. Consignado e Bonificação**

*"Vocês recebem bebidas em consignação (só paga o que vender) ou ganham bonificação (brindes) dos fornecedores? Como isso entra no estoque? Tem custo zero?"*

* **Por que perguntar:** Afeta o cálculo de lucro e o valuation do estoque.

