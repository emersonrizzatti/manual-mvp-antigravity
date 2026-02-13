
  # **Guia de Interface: Onde e Como o Sistema Será Usado?**

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

   