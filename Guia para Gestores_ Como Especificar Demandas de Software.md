# **Guia para Gestores: Como Especificar Demandas de Software**

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

Para facilitar, use este modelo ao abrir uma nova solicitação:

**Título da Demanda:** \[Nome curto\]

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

### **Dica de Ouro para Gestores**

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


  

  # **Guia de Interface para Gestores: Onde e Como o Sistema Será Usado?**

Desenvolvedores testam o sistema em monitores grandes, sentados em cadeiras confortáveis, com internet rápida. O mundo real é diferente. Para que a interface funcione para sua equipe, precisamos saber **quem**, **onde** e **em qual aparelho** o trabalho será feito.

Preencha os tópicos abaixo para cada módulo do sistema:

### **1\. Definição do Dispositivo Principal (Responsividade)**

Não diga apenas "tem que funcionar no celular". Seja específico sobre a prioridade.

* **Cenário A: "Desktop First" (Foco no Escritório)**  
  * **Quem usa:** Financeiro, Compras, RH.  
  * **Necessidade:** Telas densas. Querem ver 50 linhas de uma tabela de uma vez sem ter que rolar a página. O mouse permite cliques precisos em botões pequenos.  
  * **Exemplo de Requisito:** "A tela de Pedidos deve exibir colunas de Data, Cliente, Valor, Status e Vendedor lado a lado. O gestor usa um monitor de 24 polegadas."  
* **Cenário B: "Mobile First" (Foco na Operação/Campo)**  
  * **Quem usa:** Estoquista, Entregador, Vendedor de Salão.  
  * **Necessidade:** Botões grandes (para dedos grossos ou luvas), pouco texto, foco em uma ação por vez.  
  * **Exemplo de Requisito:** "O estoquista usa um smartphone Android simples. A tela de separação não pode ter tabelas. Deve mostrar um *card* grande com o nome do produto e um botão gigante de 'Confirmar'. Ele vai usar isso em pé, segurando o celular com uma mão."

  ### **2\. Contexto Ambiental (Luz e Barulho)**

O ambiente muda como desenhamos as cores e os alertas sonoros.

* **Iluminação:**  
  * **Ambiente Escuro (Adega/Estoque):** "O estoque é meio escuro. O fundo do aplicativo deve ser claro com letras pretas de alto contraste, ou ter um 'Modo Noturno' para não ofuscar a visão."  
  * **Luz do Sol (Venda Externa/Entrega):** "O motorista usa o app na rua. Evite fundos cinza-escuro, pois o sol reflete na tela e não dá para ler nada. Use alto contraste."  
* **Som e Alertas:**  
  * "O armazém é barulhento. O alerta de erro (bip) tem que ser estridente ou o celular deve vibrar. Apenas mostrar uma mensagem vermelha na tela não é suficiente."

  ### **3\. Método de Entrada (Input)**

Como a informação entra no sistema?

* **Teclado e Mouse:** Padrão para escritórios. Aceita atalhos (F5, Enter, Tab).  
* **Toque (Touch):** Padrão para tablets/celulares.  
  * *Regra de Ouro:* "Nenhum botão pode ter menos de 44 pixels de altura. Espaço entre botões deve ser grande para evitar 'clique gordo' (apertar o botão errado sem querer)."  
* **Leitores Externos:**  
  * "Vamos usar pistola de código de barras bluetooth? Se sim, o campo de busca deve estar sempre 'focado' (cursor piscando) para não precisar clicar na tela antes de bipar."

  ---

  ### **Check-list de Casos de Uso (Para o Gestor preencher)**

Copie e cole estas perguntas para o gestor responder antes de iniciar o desenvolvimento das telas:

#### **1\. Prioridade de Informação (O que é vital?)**

*"Em uma tela de celular, não cabe tudo. Se tivermos que esconder informações da lista de produtos, o que **NÃO** pode sumir de jeito nenhum?"*

* ( ) Preço  
* ( ) Código SKU  
* ( ) Foto do Produto  
* ( ) Quantidade em Estoque  
* **Resposta do Gestor:** "No celular, só preciso da Foto e da Quantidade. O preço é irrelevante para o estoquista."

  #### **2\. Densidade de Dados**

*"O usuário prefere ver poucos itens com muitos detalhes (Visão Cartão/Card) ou muitos itens com poucos detalhes (Visão Excel/Compacta)?"*

#### **3\. Conectividade (Modo Offline)**

*"Existe chance do usuário entrar em áreas sem internet (câmara fria, subsolo, estrada)? Se sim, o sistema deve permitir salvar dados para sincronizar depois?"*

#### **4\. Uso de Mãos/Luvas**

*"O usuário estará segurando pranchetas ou caixas enquanto usa o sistema? Ele usa luvas de proteção?"*

* (Isso define se usaremos gestos de "deslizar para excluir" ou botões fixos).

  ---

  ### **Exemplo de Requisito de Interface (Como escrever)**

Aqui está um exemplo de como transformar um desejo vago em uma regra técnica de UX:

**Ruim (Vago):** "Quero que o sistema seja fácil de usar no celular do estoquista."

**Bom (Orientado a Contexto):** "**Módulo:** Conferência de Recebimento. **Dispositivo:** Tablet Samsung Tab A (8 polegadas). **Usuário:** Conferente (trabalha em pé, ambiente com poeira). **Regras de Interface:**

1. Os botões de ação ('Aprovar', 'Rejeitar') devem ocupar toda a largura inferior da tela para facilitar o toque com o polegar.  
2. Não usar rolagem horizontal (tabelas largas). Transformar as linhas da nota fiscal em 'Cards' verticais.  
3. As cores de status devem ser redundantes com ícones (Verde \+ 'V' de check) para ajudar daltônicos ou leitura rápida.  
4. Ao clicar em 'Salvar', deve aparecer uma animação de carregamento (spinner) bloqueando a tela inteira para evitar cliques duplos acidentais."

   