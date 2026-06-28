# DATA2 — Inteligência de Mercado e Benchmarking para o Nur Mah Museum

## Objetivo
Análise do IMLS Museum Directory Dataset para apoiar decisões de
captação de recursos e parcerias do Nur Mah Museum (museu fictício de
arte moderna), respondendo a perguntas de negócio sobre receita,
geografia e discrepâncias de mercado.

## Como rodar
1. `pip install -r requirements.txt`
2. Abrir `notebooks/<nome_do_notebook>.ipynb`
3. Rodar células em ordem (Colab ou Jupyter)

## Decisões principais
- Receita oficial: coluna `Revenue` (não `Income`) — ver RN07.
- Localização: `Administrative Location` (não `Physical Location`,
  ~72% nula) — ver RN07.
- Linhas com `Revenue` nulo excluídas apenas da análise financeira
  (RF01), mantidas para análises de tipo/geografia.
- Duplicados Padrão 1 (54 casos) removidos por critério de
  completude + Revenue + Tax Period (RN08).
- Duplicação institucional Padrão 2 (905 grupos, 1.125 linhas —
  ex. Harvard, Yale) tratada zerando Revenue duplicado, mantendo a
  linha para contagem de museus.

## Limitações conhecidas
- Padrão 4 (duplicados por sufixo textual, ex. "INC") identificado
  mas não tratado por restrição de tempo — melhoria futura.
- Base de dados de 2014, não reflete o mercado atual.
- Outliers extremos legítimos (museus grandes reais) permanecem nos
  dados — não são erro, mas afetam a média (por isso o uso de mediana).

## Estrutura
- `notebooks/` — notebook principal com toda a análise
- `requirements.txt` — dependências (pandas, matplotlib, seaborn)
