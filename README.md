# 🔎 Validador e Analisador de HTML

Projeto acadêmico desenvolvido para análise estrutural de arquivos HTML, com foco em validação de tags, detecção de erros, geração de estatísticas, visualização hierárquica e interface gráfica.

---

## 🎯 Objetivo

O sistema tem como objetivo analisar arquivos HTML e verificar:

- Se as tags estão corretamente balanceadas
- Se a estrutura do HTML é válida
- Se existem erros estruturais
- A frequência de cada tag
- A hierarquia do documento HTML
- Geração de um relatório completo da análise

---

## ⚙️ Funcionalidades

### ✔ Validação de HTML
- Uso obrigatório de **Pilha (Stack)**
- Verificação de tags de abertura e fechamento
- Suporte a tags singleton (ex: `img`, `br`, `meta`, `hr`, etc.)
- Ignora diferenças entre maiúsculas e minúsculas
- Ignora atributos das tags (ex: `<a href="">` → considera apenas `a`)

---

### ❌ Identificação de erros

O sistema identifica obrigatoriamente:

- Tag final inesperada  
  Ex: `</body>` quando era esperado `</p>`

- Tag final sem abertura  
  Ex: `</p>` sem `<p>` correspondente

- Tags não finalizadas  
  Ex: `<div>` sem `</div>`

- Tag malformada  
  Ex: `< div>` ou `<a href`

---

### 📊 Estatísticas de tags

- Frequência de cada tag (sem contar fechamentos)
- Tipo da tag:
  - normal
  - singleton
- Linha da primeira ocorrência
- Ordenação obrigatória por **MergeSort**

---

### 🌳 Hierarquia do HTML

- Representação em formato de árvore
- Exibição com indentação
- Só é exibida se o HTML estiver válido

---

### 🖥 Interface gráfica

- Seleção de arquivo `.html` ou `.txt`
- Execução da análise
- Exibição de:
  - erros
  - estatísticas
  - hierarquia
- Interface amigável (Swing ou JavaFX)

---

## 🧠 Estruturas de Dados Utilizadas

Este projeto utiliza obrigatoriamente as seguintes estruturas:

- **Pilha (Stack)** → validação de tags HTML
- **Fila (Queue)** → armazenamento de erros estruturais
- **Árvore (Tree)** → hierarquia do HTML
- **Lista** → controle de frequência de tags
- **MergeSort** → ordenação da tabela de saída

---

## 🏗 Arquitetura do Projeto

O sistema foi organizado em módulos para melhor manutenção e separação de responsabilidades:

- `principal` → ponto de entrada do sistema
- `interface` → interface gráfica (UI)
- `leitura` → leitura e interpretação do arquivo HTML
- `estruturas` → pilha, fila e nós
- `analise` → validação, erros e hierarquia
- `ordenacao` → algoritmo MergeSort
- `relatorio` → geração de relatórios finais
- `modelo` → classes de domínio (Tag, Nó, etc.)
- `util` → funções auxiliares e constantes

---

## 📁 Estrutura do Projeto

```txt
html-validador/
│
├── src/
│   ├── principal/
│   │   └── Main.java
│
│   ├── interface/
│   │   ├── JanelaPrincipal.java
│   │   ├── SeletorArquivo.java
│   │   └── VisualizadorRelatorio.java
│
│   ├── modelo/
│   │   ├── Tag.java
│   │   ├── FrequenciaTag.java
│   │   └── NoHTML.java
│
│   ├── estruturas/
│   │   ├── Pilha.java
│   │   ├── Fila.java
│   │   └── No.java
│
│   ├── leitura/
│   │   ├── LeitorHTML.java
│   │   ├── ParserTags.java
│   │   └── ValidadorHTML.java
│
│   ├── analise/
│   │   ├── AnalisadorTags.java
│   │   ├── ConstrutorHierarquia.java
│   │   └── AnalisadorErros.java
│
│   ├── ordenacao/
│   │   └── MergeSort.java
│
│   ├── relatorio/
│   │   └── GeradorRelatorio.java
│
│   ├── util/
│   │   ├── UtilTags.java
│   │   └── Constantes.java
│
├── recursos/
│   ├── exemplos/
│   │   ├── valido.html
│   │   ├── invalido.html
│   │   └── teste.txt
│
├── testes/
│   ├── TestePilha.java
│   ├── TesteParser.java
│   └── TesteValidador.java
│
├── docs/
│   ├── diagrama-classes.png
│   └── fluxo-validacao.png
│
├── README.md
├── .gitignore
└── LICENSE

```

## 🚀 Como executar

1. Clone o repositório:
```bash
git clone https://github.com/sua-equipe/html-validador

