# 🤝 Guia de Contribuição

Obrigado por considerar contribuir com o Manual MVP Antigravity! Este documento fornece diretrizes para contribuições.

## 🎯 Objetivo do Projeto

Criar e manter documentação **clara, acessível e prática** para pessoas com baixo conhecimento técnico desenvolverem MVPs usando Antigravity.

## 📋 Tipos de Contribuições Aceitas

### 1. Correções de Erros
- Erros de digitação
- Links quebrados
- Informações desatualizadas
- Erros técnicos

### 2. Melhorias de Conteúdo
- Clarificação de instruções confusas
- Adição de exemplos práticos
- Melhoria de explicações técnicas
- Adição de diagramas ou imagens ilustrativas

### 3. Novos Conteúdos
- Casos de uso práticos
- Tutoriais complementares
- Seções de FAQ
- Guias de troubleshooting

### 4. Traduções
- Tradução para outros idiomas
- Manutenção de traduções existentes

## 🔄 Processo de Contribuição

### Passo 1: Fork e Clone
```bash
# Fork este repositório no GitHub
# Clone seu fork
git clone https://github.com/SEU-USUARIO/manual-mvp-antigravity.git
cd manual-mvp-antigravity
```

### Passo 2: Crie uma Branch
```bash
git checkout -b tipo/descricao-curta
```

**Tipos de branch:**
- `correcao/` - Para correções de erros
- `melhoria/` - Para melhorias de conteúdo
- `novo/` - Para novos conteúdos
- `traducao/` - Para traduções

**Exemplos:**
- `correcao/link-quebrado-passo-8`
- `melhoria/exemplos-requisitos`
- `novo/tutorial-deploy-vercel`
- `traducao/ingles`

### Passo 3: Faça suas Alterações

**Diretrizes de Estilo:**

1. **Clareza acima de tudo** - Escreva como se estivesse explicando para alguém sem conhecimento técnico
2. **Use exemplos práticos** - Exemplos concretos são mais úteis que explicações abstratas
3. **Seja conciso** - Evite textos muito longos; use listas e tópicos
4. **Formatação consistente** - Siga o padrão dos documentos existentes
5. **Português claro** - Use linguagem simples e direta

**Formatação Markdown:**
- Use `**negrito**` para termos importantes
- Use `código` para comandos, nomes de arquivos e código
- Use `> [!NOTE]`, `> [!TIP]`, `> [!IMPORTANT]` para alertas
- Use emojis para melhorar a escaneabilidade (mas com moderação)

### Passo 4: Teste suas Alterações

Antes de enviar:
- [ ] Leia o documento completo para verificar fluidez
- [ ] Verifique todos os links
- [ ] Confirme que a formatação está correta
- [ ] Peça para alguém não-técnico revisar (se possível)

### Passo 5: Commit
```bash
git add .
git commit -m "Tipo: Descrição clara da mudança"
```

**Exemplos de mensagens de commit:**
- `Correção: Atualiza link quebrado no passo 8`
- `Melhoria: Adiciona exemplo de requisitos para sistema de estoque`
- `Novo: Adiciona seção de troubleshooting para erros de deploy`
- `Tradução: Adiciona versão em inglês do README`

### Passo 6: Push e Pull Request
```bash
git push origin sua-branch
```

Depois:
1. Vá até o GitHub e abra um Pull Request
2. Preencha o template do PR com detalhes
3. Aguarde a revisão

## ✅ Checklist do Pull Request

Antes de enviar seu PR, confirme:

- [ ] Segui as diretrizes de estilo
- [ ] Testei todos os links
- [ ] A formatação está correta
- [ ] A mensagem de commit é clara
- [ ] Adicionei exemplos quando apropriado
- [ ] O conteúdo é acessível para não-técnicos

## 🔍 Processo de Revisão

1. **Revisão inicial** - Verificação de qualidade e alinhamento com objetivos
2. **Feedback** - Sugestões de melhorias (se necessário)
3. **Aprovação** - Merge após aprovação do moderador
4. **Agradecimento** - Você será creditado como contribuidor!

## 📝 Diretrizes Específicas

### Para Exemplos de Código
```markdown
**Exemplo de requisitos.md:**

\`\`\`markdown
# Requisitos do Sistema de Vendas

## Objetivo
Registrar vendas e controlar estoque

## Funcionalidades
1. Cadastrar produtos
2. Registrar vendas
3. Atualizar estoque automaticamente
\`\`\`
```

### Para Capturas de Tela
- Use imagens em formato PNG ou JPG
- Adicione na pasta `images/`
- Use nomes descritivos: `passo-8-antigravity-interface.png`
- Adicione texto alternativo: `![Interface do Antigravity](images/passo-8-antigravity-interface.png)`

### Para Links
- Prefira links relativos para arquivos no repositório
- Use links absolutos para recursos externos
- Sempre teste os links antes de enviar

## ❌ O que NÃO Fazer

- ❌ Adicionar conteúdo muito técnico sem explicação
- ❌ Usar jargões sem definição
- ❌ Fazer mudanças massivas sem discussão prévia
- ❌ Copiar conteúdo de outras fontes sem atribuição
- ❌ Adicionar propaganda ou links promocionais

## 💬 Dúvidas?

Se tiver dúvidas sobre como contribuir:

1. Abra uma [Issue](../../issues) com a tag `dúvida`
2. Participe das [Discussions](../../discussions)
3. Veja exemplos de PRs anteriores

## 🌟 Reconhecimento

Todos os contribuidores serão:
- Listados no README (se desejarem)
- Creditados nos commits
- Muito agradecidos pela comunidade! 🙏

---

**Obrigado por contribuir para democratizar o desenvolvimento de software!** ❤️
