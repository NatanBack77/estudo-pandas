# Estudo de Pandas

Projeto de estudo de **pandas** usando um conjunto de dados de vendas de produtos de tecnologia. O notebook cobre leitura, inspeção e limpeza de dados, com todo o código comentado em português.

## Conteúdo do repositório

| Arquivo | Descrição |
|---|---|
| `pandas.ipynb` | Notebook com o estudo (leitura, inspeção e tratamento dos dados) |
| `vendas_tech.csv` | Base de vendas (100.100 linhas x 8 colunas) |
| `gerentes_lojas.xlsx` | Planilha com os gerentes de cada loja (ainda não utilizada no notebook) |

## Dados

Colunas de `vendas_tech.csv`:

| Coluna | Descrição |
|---|---|
| `ID_Pedido` | Identificador do pedido |
| `Data` | Data da venda (`AAAA-MM-DD`) |
| `Loja` | Loja onde a venda ocorreu (pode estar nula) |
| `Produto` | Produto vendido |
| `Preco_Unitario` | Preço de uma unidade |
| `Qtd` | Quantidade vendida |
| `Cliente` | Identificador do cliente |
| `Data_Base` | Preenchida em apenas uma linha; descartada na análise |

## O que o notebook faz

1. **Leitura**: carrega o CSV com `pd.read_csv` (UTF-8, separador `,`).
2. **Inspeção**: usa `shape`, `columns`, `info()` e `describe()` para entender o formato, os tipos e os valores nulos.
3. **Tratamento**:
   - remove a coluna `Data_Base`;
   - preenche as lojas nulas com `"online"`;
   - converte `Data` para `datetime`;
   - padroniza os nomes das lojas (remove espaços e aplica `str.title()`);
   - remove duplicatas por `ID_Pedido` + `Loja` (100.100 para 100.000 linhas).
4. **Criação de colunas**: seção reservada para as próximas etapas (por exemplo, o valor total da venda).

## Como executar

Requisitos: Python 3.10+, `pandas`, `numpy` e `openpyxl` (para ler o `.xlsx`), além do Jupyter.

```bash
git clone https://github.com/NatanBack77/estudo-pandas.git
cd estudo-pandas
pip install pandas numpy openpyxl notebook
jupyter notebook pandas.ipynb
```

Abra o notebook a partir da pasta do projeto, pois os arquivos de dados são lidos por caminho relativo.
