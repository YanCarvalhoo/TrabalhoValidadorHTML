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
│   └── util/
│       ├── UtilTags.java
│       └── Constantes.java
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
└── .gitignore

---


## 🚀 Como executar

1. Clone o repositório:
```bash
git clone https://github.com/sua-equipe/html-validador
