# Heatmap de Maturidade Individual

Aplicação web estática para autoavaliação de maturidade em conteúdos de Processos, Sistemas e Dados.

## Estrutura do projeto

```
heatmap-maturidade/
├── index.html        ← aplicação principal
├── conteudos.xlsx    ← fonte de dados (editável)
└── README.md
```

## Como atualizar os conteúdos

Edite o arquivo `conteudos.xlsx` diretamente no Excel. Mantenha as colunas na ordem:

| Coluna | Descrição |
|--------|-----------|
| Área de Atuação | Processos, Sistemas ou Dados |
| Categoria | Agrupamento dentro da área |
| Tópico | Nome do conteúdo |
| Nível | Iniciante / Intermediário / Avançado / Especialista |

Você pode adicionar novas linhas, novas áreas ou novas categorias — a aplicação lê tudo dinamicamente.

---

## Deploy no GitHub Pages (passo a passo)

### 1. Criar conta no GitHub
Acesse https://github.com e crie uma conta gratuita caso não tenha.

### 2. Criar repositório
- Clique em **New repository**
- Nome sugerido: `heatmap-maturidade`
- Marque como **Public** (necessário para GitHub Pages gratuito)
- Clique em **Create repository**

### 3. Fazer upload dos arquivos
Na página do repositório recém-criado:
- Clique em **Add file → Upload files**
- Arraste os três arquivos: `index.html`, `conteudos.xlsx`, `README.md`
- Clique em **Commit changes**

### 4. Ativar GitHub Pages
- Vá em **Settings** (aba do repositório)
- No menu lateral, clique em **Pages**
- Em **Source**, selecione `Deploy from a branch`
- Em **Branch**, selecione `main` e pasta `/ (root)`
- Clique em **Save**

### 5. Acessar a aplicação
Após 1–2 minutos, a URL estará disponível no formato:
```
https://SEU-USUARIO.github.io/heatmap-maturidade/
```

Essa URL pode ser compartilhada com qualquer membro do time.

---

## Como funciona o salvamento

- As notas são salvas **automaticamente** no `localStorage` do navegador a cada clique
- Cada pessoa tem suas próprias notas — os dados **não são compartilhados entre dispositivos**
- Se a pessoa limpar os dados do navegador ou usar outro computador, as notas são perdidas
- Para backup: use o botão **Exportar CSV** que gera um arquivo com todas as notas

## Escala de maturidade (Dreyfus adaptado)

| Nível | Nome | Critério |
|-------|------|----------|
| N0 | Nunca vi | Não conheço o conceito |
| N1 | Novice | Já ouvi/li, sei o que é, nunca apliquei |
| N2 | Iniciante avançado | Já experimentei ao menos uma vez |
| N3 | Competente | Uso com autonomia no trabalho real |
| N4 | Expert | Já ensinei alguém sobre isso |

---

## Atualizando o Excel depois do deploy

Quando atualizar o `conteudos.xlsx`:
1. Faça o upload do novo arquivo no repositório (sobrescreva o antigo)
2. GitHub Pages atualiza automaticamente em poucos minutos
3. As notas salvas no `localStorage` dos usuários são preservadas — apenas novos conteúdos aparecerão sem nota

## Próximos passos possíveis

- [ ] Adicionar gráfico radar por categoria
- [ ] Migrar para Supabase para salvar notas em banco de dados (multiusuário)
- [ ] Adicionar tela de resultado/diagnóstico com recomendações de estudo
