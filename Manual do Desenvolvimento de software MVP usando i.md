# Manual do Desenvolvimento de Software MVP usando Inteligência Artificial

## 📋 Pré-requisitos (O que você precisa antes de começar)

Antes de iniciar o desenvolvimento do seu MVP, você precisará:

- **Computador com Windows, Mac ou Linux** (com pelo menos 8GB de RAM recomendado)
- **Conexão com a internet** (estável, para downloads e sincronização)
- **Conta Google** (gratuita - você pode usar seu Gmail)
- **Tempo estimado**: 2-4 horas para configuração inicial

> [!NOTE]
> **MVP** significa "Minimum Viable Product" (Produto Mínimo Viável) - uma versão básica do seu sistema que já pode ser testada por usuários reais.

---

## 🚀 Passo a Passo Completo

### **1. Criar sua conta no GitHub**

O GitHub é onde o código do seu sistema ficará armazenado de forma segura e organizada.

1. Acesse [github.com](https://github.com)
2. Clique em "Sign up" (Cadastrar-se)
3. Preencha com seu email, crie uma senha forte
4. Confirme seu email
5. **Guarde suas credenciais** (usuário e senha) em local seguro

> [!TIP]
> O GitHub é gratuito e permite criar repositórios ilimitados. É como um "Google Drive" para código.

---

### **2. Criar a pasta do projeto no seu PC**

Organize seus arquivos em uma pasta dedicada ao projeto:

1. Crie uma pasta em um local de fácil acesso, exemplo:
   - Windows: `C:\Projetos\MeuSistema`
   - Mac/Linux: `~/Projetos/MeuSistema`
2. **Use nomes sem espaços e sem acentos** (exemplo: `SistemaEstoque` ao invés de `Sistema de Estoque`)
3. Esta pasta será o "lar" de todo o código do seu projeto

---

### **3. Preparar os arquivos de referência**

**Este é o passo mais importante!** A qualidade do sistema depende da clareza das suas instruções.

Crie arquivos de texto (`.txt` ou `.md`) dentro da pasta do projeto com:

- **`requisitos.md`** - O que o sistema precisa fazer
- **`regras-de-negocio.md`** - As regras que o sistema deve seguir
- **`casos-de-uso.md`** - Como os usuários vão usar o sistema

> [!IMPORTANT]
> **Não sabe como escrever esses arquivos?** Consulte o [Guia para Gestores: Como Especificar Demandas de Software](Guia%20para%20Gestores_%20Como%20Especificar%20Demandas%20de%20Software.md) que está nesta mesma pasta. Ele ensina passo a passo como transformar sua ideia em instruções claras.

**Exemplo de conteúdo básico:**

```markdown
# Requisitos do Sistema de Estoque

## Objetivo
Controlar entrada e saída de produtos do estoque

## Funcionalidades Principais
1. Cadastrar produtos (nome, código, quantidade)
2. Registrar entrada de mercadorias
3. Registrar saída de mercadorias
4. Consultar estoque atual
5. Gerar relatório de movimentações
```

---

### **4. Baixar e instalar o Google Antigravity**

O Antigravity é a ferramenta de IA que vai desenvolver o sistema para você.

1. Acesse [https://antigravity.google/](https://antigravity.google/)
2. Clique em "Download" ou "Get Started"
3. Escolha a versão para seu sistema operacional (Windows/Mac/Linux)
4. Execute o instalador e siga as instruções na tela
5. Aguarde a instalação completa (pode levar alguns minutos)

> [!NOTE]
> O Antigravity é uma ferramenta oficial do Google, segura e gratuita para uso.

---

### **5. Fazer login com sua conta Google**

1. Abra o Antigravity
2. Clique em "Sign in" ou "Login"
3. Escolha sua conta Google
4. Autorize as permissões solicitadas
5. Aguarde o carregamento da interface

---

### **6. Abrir a pasta do projeto no Antigravity**

1. No Antigravity, procure a opção "Open Folder" ou "Abrir Pasta"
2. Navegue até a pasta que você criou no Passo 2
3. Selecione a pasta e clique em "Abrir"
4. Você verá os arquivos da pasta aparecerem na barra lateral

> [!TIP]
> Você pode trabalhar em vários projetos diferentes. Basta abrir a pasta de outro projeto quando quiser trocar.

---

### **7. Conectar ao GitHub e criar o repositório**

Agora vamos conectar o projeto ao GitHub para versionar o código.

**Digite a seguinte mensagem no Antigravity:**

```
Faça login na minha conta do GitHub e crie um repositório para este projeto.
```

O Antigravity vai:
- Solicitar suas credenciais do GitHub (usuário e senha ou token)
- Criar um repositório novo com o nome da pasta
- Conectar a pasta local ao repositório online

> [!CAUTION]
> Quando o Antigravity pedir suas credenciais do GitHub, **nunca compartilhe sua senha com outras pessoas**. O Antigravity é seguro, mas mantenha suas credenciais privadas.

---

### **8. Iniciar o desenvolvimento do sistema**

Agora é a hora da mágica! O Antigravity vai ler seus arquivos e criar o sistema.

**Digite a seguinte mensagem no Antigravity:**

```
Analise os arquivos de referência que foram carregados para a pasta (requisitos.md, regras-de-negocio.md, casos-de-uso.md) e comece o desenvolvimento de um software que atenda a todos os requisitos, regras de negócio e casos de uso especificados.

O software deve ser desenvolvido usando as seguintes tecnologias:

**Backend:**
- Node.js
- Express
- PostgreSQL
- Sequelize

**Frontend:** (Veja mais detalhes no guia "Como desenvolver a Interface do sistema.md")
- React
- Vite
- React Router
- Lucide React
- React-Bootstrap (UI/UX Mobile-First)

> [!TIP]
> **Está em dúvida sobre quais tecnologias usar?** (Ex: Python, Java, No-Code)
> Consulte o [Guia de Escolha de Tecnologias](Guia%20de%20Escolha%20de%20Tecnologias.md) para ver alternativas e decidir o que é melhor para seu projeto.


**Configurações adicionais:**
- Configurar meu PC local para aceitar acessos via rede local
- Preparar o sistema para ser publicado online no serviço Blueprint do Render.com (plano gratuito)
```

> [!IMPORTANT]
> **Não sabe como escrever os arquivos de requisitos, regras de negócio e casos de uso?**  
> Consulte o [Guia para Gestores: Como Especificar Demandas de Software](Guia%20para%20Gestores_%20Como%20Especificar%20Demandas%20de%20Software.md) que está nesta mesma pasta. Ele contém exemplos práticos e templates prontos para você copiar e adaptar.

**O que vai acontecer:**
- O Antigravity vai ler e entender seus requisitos
- Vai criar a estrutura do banco de dados
- Vai desenvolver o backend (servidor)
- Vai criar as telas do frontend (interface)
- Vai configurar tudo para funcionar junto

**Tempo estimado:** 30 minutos a 2 horas (dependendo da complexidade)

---

### **9. Testar o sistema localmente**

Antes de colocar online, vamos testar no seu próprio computador.

**Digite a seguinte mensagem no Antigravity:**

```
Inicie o servidor local e realize testes de:
1. Cadastros de dados
2. Uso de todas as funcionalidades do sistema
3. Corrija automaticamente os erros encontrados

Mostre-me como acessar o sistema no navegador.
```

**O que vai acontecer:**
- O Antigravity vai iniciar o servidor no seu PC
- Vai abrir o sistema no navegador (geralmente em `http://localhost:3000`)
- Vai testar automaticamente as funcionalidades
- Vai corrigir erros que encontrar

**Seu papel:**
- Navegue pelo sistema
- Teste cadastrar, editar, excluir dados
- Anote qualquer comportamento estranho
- Informe ao Antigravity se encontrar problemas

> [!TIP]
> Se algo não funcionar como esperado, simplesmente descreva o problema ao Antigravity. Exemplo: "Quando clico em Salvar, nada acontece" ou "O relatório não está mostrando os dados corretos".

---

### **10. Publicar o sistema online no Render.com**

Agora vamos colocar o sistema na internet para que outras pessoas possam acessar!

**Primeiro, crie sua conta no Render.com:**
1. Acesse [render.com](https://render.com)
2. Clique em "Get Started" ou "Sign Up"
3. Você pode fazer login com sua conta do GitHub (mais fácil)
4. Confirme seu email

**Depois, digite a seguinte mensagem no Antigravity:**

```
Publique o sistema no Render.com usando o serviço Blueprint, configurado com:
- type: web
- env: node
- plan: free

Crie todos os arquivos de configuração necessários e me guie no processo de deploy.
```

**O que vai acontecer:**
- O Antigravity vai criar os arquivos de configuração (`render.yaml`)
- Vai fazer o upload do código para o GitHub
- Vai conectar o GitHub ao Render.com
- Vai iniciar o processo de publicação

**Tempo estimado:** 10-20 minutos

> [!NOTE]
> O plano gratuito do Render.com tem algumas limitações:
> - O sistema "dorme" após 15 minutos sem uso (demora ~30 segundos para "acordar")
> - Banco de dados gratuito expira após 90 dias (mas você pode renovar)
> - Suficiente para testes e MVPs com poucos usuários

---

## ✅ Checklist de Conclusão

Você terminou quando conseguir marcar todos esses itens:

- [ ] Conta do GitHub criada e ativa
- [ ] Pasta do projeto criada com arquivos de referência
- [ ] Antigravity instalado e conectado à conta Google
- [ ] Repositório GitHub criado e conectado
- [ ] Sistema desenvolvido e funcionando localmente
- [ ] Testes realizados sem erros críticos
- [ ] Sistema publicado no Render.com
- [ ] URL pública funcionando (exemplo: `https://meusistema.onrender.com`)

---

## 🆘 Problemas Comuns e Soluções

### **"O Antigravity não está entendendo meus requisitos"**
- **Solução:** Seja mais específico. Use exemplos práticos. Consulte o [Guia para Gestores](Guia%20para%20Gestores_%20Como%20Especificar%20Demandas%20de%20Software.md) para aprender a escrever requisitos claros.

### **"O sistema não inicia localmente"**
- **Solução:** Pergunte ao Antigravity: "Por que o servidor não está iniciando? Mostre os logs de erro."

### **"O deploy no Render.com falhou"**
- **Solução:** Peça ao Antigravity: "Analise os logs de erro do Render e corrija os problemas de configuração."

### **"Quero adicionar uma nova funcionalidade"**
- **Solução:** Crie um novo arquivo `nova-funcionalidade.md` na pasta do projeto, descreva o que quer, e peça ao Antigravity para implementar.

### **"O sistema está lento no Render.com"**
- **Solução:** Isso é normal no plano gratuito. O sistema "acorda" após o primeiro acesso. Para melhor performance, considere o plano pago ($7/mês).

---

## 📚 Próximos Passos

Depois que seu MVP estiver funcionando:

1. **Colete feedback** de usuários reais
2. **Documente melhorias** em um arquivo `melhorias.md`
3. **Peça ao Antigravity** para implementar as melhorias prioritárias
4. **Repita o ciclo** de teste → feedback → melhoria

---

## 💡 Dicas Finais

- **Comunique-se claramente** com o Antigravity, como se estivesse falando com um desenvolvedor júnior
- **Teste sempre** antes de publicar mudanças
- **Faça backups** regulares (o GitHub já faz isso automaticamente)
- **Documente tudo** - seu "eu do futuro" vai agradecer
- **Comece simples** - é melhor um sistema básico funcionando do que um complexo pela metade

---

> [!TIP]
> **Lembre-se:** O Antigravity é uma ferramenta poderosa, mas a qualidade do sistema depende da claridade das suas instruções. Quanto mais específico você for nos requisitos, melhor será o resultado!

**Boa sorte com seu MVP! 🚀**
