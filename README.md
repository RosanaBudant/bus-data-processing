# 🚌 Tratamento de Horários de Ônibus com Python

Este projeto realiza a limpeza e padronização de horários de uma tabela de ônibus, corrigindo valores inconsistentes como horários acima de 24h (ex: `25:30`, `26:15`), convertendo-os para o formato válido `HH:MM`.

---

## 📌 Problema

Em algumas bases de dados de transporte público, horários podem ultrapassar 24h para representar viagens após a meia-noite (por exemplo, `25:00` ao invés de `01:00`).

Isso pode causar problemas em:

* Análises de dados
* Visualizações
* Integrações com sistemas que esperam horários válidos

---

## ⚙️ Solução

O script:

* Lê um arquivo `.csv` com separador `;` e encoding `latin-1`
* Identifica horários inválidos
* Converte automaticamente horários acima de 24h usando módulo 24
* Salva um novo arquivo corrigido

---

## 🧠 Lógica utilizada

A correção dos horários é feita com base na operação de módulo:

```
hora_corrigida = hora % 24
```

Exemplos:

* `24:00` → `00:00`
* `25:30` → `01:30`
* `26:15` → `02:15`

---

## 🛠️ Tecnologias

* Python 3
* pandas

---

## ▶️ Como executar

1. Instale as dependências:

```
pip install pandas
```

2. Coloque o arquivo `tabela_horaria_onibus.csv` na mesma pasta do script

3. Execute o script:

```
python script.py
```

---

## 📁 Entrada esperada

Arquivo CSV com estrutura semelhante a:

```
horario_largada
23:30
24:15
25:45
```

---

## 📤 Saída

Um novo arquivo será gerado:

```
arquivo_corrigido.csv
```

Com os horários normalizados:

```
horario_largada
23:30
00:15
01:45
```

---

## 💡 Possíveis melhorias

* Validação de formato de horário
* Suporte a múltiplas colunas
* Interface de linha de comando (CLI)
* Testes automatizados

---

## 👩‍💻 Autora

Projeto desenvolvido por Rosana como prática de tratamento de dados com Python.
