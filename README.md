# 🔎 TrabalhoValidadorHTML

Projeto desenvolvido para análise estrutural de arquivos HTML, com validação de tags, detecção de erros, cálculo de estatísticas e visualização da hierarquia do documento.

---

## 🎯 Objetivo

Desenvolver um sistema capaz de:

- Validar a estrutura de arquivos HTML
- Verificar se as tags estão corretamente balanceadas
- Identificar erros estruturais
- Gerar estatísticas de uso de tags
- Exibir a hierarquia do documento HTML
- Produzir um relatório completo da análise

---

## ⚙️ Funcionalidades

### ✔ Validação de HTML
- Uso obrigatório de **Pilha**
- Verificação de abertura e fechamento de tags
- Suporte a tags singleton (ex: `img`, `br`, `meta`, etc.)
- Ignora diferenças entre maiúsculas e minúsculas
- Ignora atributos das tags

---

### ❌ Identificação de erros

O sistema deve identificar:

- Tag final inesperada  
- Tag final sem abertura  
- Tags não finalizadas  
- Tag malformada  

---

### 📊 Estatísticas de tags

- Frequência de cada tag
- Tipo da tag (normal ou singleton)
- Linha da primeira ocorrência
- Ordenação alfabética obrigatória (MergeSort)

---

### 🌳 Hierarquia do HTML

- Exibição da estrutura em forma de árvore
- Representação com indentação
- Só exibida se o HTML estiver válido

---

### 🖥 Interface gráfica

- Seleção de arquivo (.html ou .txt)
- Exibição do relatório
- Interface amigável para o usuário

---

## 🧠 Estruturas de Dados utilizadas

- **Pilha** → validação de tags
- **Fila** → armazenamento de erros
- **Árvore** → hierarquia HTML
- **Lista** → estatísticas
- **MergeSort** → ordenação obrigatória

---

## 🏗 Arquitetura do Projeto

O sistema foi dividido em módulos:

- `interface` → interface gráfica
- `leitura` → leitura e parsing do HTML
- `estruturas` → pilha, fila e nós
- `analise` → validação, erros e hierarquia
- `ordenacao` → algoritmo MergeSort
- `relatorio` → geração de relatório
- `util` → utilitários e constantes

- html-validador/
│
├── src/
│   ├── principal/
│   │   ├── Main.java
│   │
│   ├── interface/
│   │   ├── JanelaPrincipal.java        # Interface gráfica (Swing/JavaFX)
│   │   ├── SeletorArquivo.java        # Seleção de arquivos HTML/TXT
│   │   └── VisualizadorRelatorio.java # Exibição do relatório final
│   │
│   ├── modelo/
│   │   ├── Tag.java                   # Representação de uma tag HTML
│   │   ├── FrequenciaTag.java        # Dados da tabela de frequência
│   │   └── NoHTML.java               # Nó da hierarquia (árvore)
│   │
│   ├── estruturas/
│   │   ├── Pilha.java                # Pilha para validação
│   │   ├── Fila.java                 # Fila para erros estruturais
│   │   └── No.java                   # Nó genérico (se necessário)
│   │
│   ├── leitura/
│   │   ├── LeitorHTML.java          # Leitura do arquivo linha a linha
│   │   ├── ParserTags.java          # Identificação de tags e atributos
│   │   └── ValidadorHTML.java       # Regras de validação
│   │
│   ├── analise/
│   │   ├── AnalisadorTags.java      # Frequência de tags
│   │   ├── ConstrutorHierarquia.java# Monta árvore HTML
│   │   └── AnalisadorErros.java     # Geração de erros estruturais
│   │
│   ├── ordenacao/
│   │   └── MergeSort.java          # Algoritmo obrigatório
│   │
│   ├── relatorio/
│   │   └── GeradorRelatorio.java    # Geração do relatório final
│   │
│   └── util/
│       ├── UtilTags.java            # limpeza, lowercase, etc
│       └── Constantes.java          # tags singleton e mensagens
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

---


## 🚀 Como executar

1. Clone o repositório:
```bash
git clone https://github.com/sua-equipe/html-validador
