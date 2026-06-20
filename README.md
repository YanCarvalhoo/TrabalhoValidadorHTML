# TrabalhoValidadorHTML

Projeto desenvolvido para análise estrutural de arquivos HTML, com validação de tags, detecção de erros, geração de estatísticas e visualização hierárquica do documento.

---

## 📌 Objetivo

Este sistema analisa arquivos HTML (.html ou .txt) e verifica:

- Se as tags estão corretamente balanceadas
- Se a estrutura HTML está válida
- Se há erros estruturais
- Frequência de tags
- Hierarquia do documento

Além disso, gera um relatório completo da análise.

---

## ⚙️ Funcionalidades

### ✔ Validação de HTML
- Uso obrigatório de **pilha (Stack)**
- Verificação de tags de abertura e fechamento
- Suporte a tags singleton (ex: `img`, `br`, `meta`, etc.)
- Ignora maiúsculas/minúsculas

### ❌ Detecção de erros
- Tag final inesperada
- Tag final sem abertura
- Tags não finalizadas
- Tags malformadas

### 📊 Estatísticas
- Frequência de tags
- Tipo da tag (normal ou singleton)
- Primeira ocorrência

### 🌳 Hierarquia HTML
- Exibição em formato de árvore com indentação
- Apenas exibida se o HTML for válido

### 🖥 Interface gráfica
- Seleção de arquivo
- Exibição de relatório
- Interface amigável

---

## 🧠 Estruturas de Dados Utilizadas

- Pilha (Stack) → validação de tags
- Fila (Queue) → armazenamento de erros
- Árvore → hierarquia HTML
- Lista → frequência de tags
- MergeSort → ordenação obrigatória

---

## 🏗 Arquitetura do Projeto

O projeto é dividido em módulos:

- `parser/` → leitura e interpretação do HTML
- `structure/` → estruturas de dados
- `analyzer/` → análise e estatísticas
- `sort/` → algoritmos de ordenação
- `ui/` → interface gráfica
- `report/` → geração de relatórios

---

## 🚀 Como executar

1. Clone o repositório:
```bash
git clone https://github.com/sua-equipe/html-validator
