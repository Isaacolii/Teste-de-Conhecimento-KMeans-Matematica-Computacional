# Trabalho: implementação manual do K-means

**Matemática Computacional** · Prof. Dr. Alexsandro O. A.
Aluno: Isaac Oliveira

Implementação do K-means do zero, só com NumPy e pandas, seguindo o pseudocódigo e as convenções do
[enunciado](https://github.com/alexsandro-fap/test-kmeans).

## Como rodar

Com os quatro arquivos na mesma pasta:

```bash
pip install numpy pandas matplotlib
python kmeans_template.py
```

O script roda os testes do dataset 1 e imprime o relatório dos datasets 2 e 3.

## Funções implementadas

| Função | O que faz |
| --- | --- |
| `padronizar` | z-score coluna por coluna, com média e desvio-padrão populacional (`ddof=0`) |
| `centroides_iniciais` | pega as linhas cujos ids estão na lista de inicialização, na ordem da lista |
| `matriz_distancias` | matriz D (n × k) das distâncias ao quadrado, por broadcasting |
| `atribuir` | `np.argmin` em cada linha de D (empate fica com o menor índice) |
| `atualizar_centroides` | média dos dados de cada grupo; grupo vazio mantém o centroide |
| `calcular_J` | soma das distâncias ao quadrado de cada dado ao seu centroide |
| `kmeans` | atribui, para se nada mudou, atualiza e guarda J a cada iteração |
| `silhueta` | a(i), b(i) e s(i) com distância euclidiana; grupo de um elemento tem s(i) = 0 |

## Resultados

**Dataset 1 (entregas dos Correios):** os 13 testes do template passam (8 atualizações, J final = 230,11,
grupos com 20, 22 e 18 entregas, silhueta média = 0,756).

**Dataset 2 (vendas esportivas), k = 4:** 5 atualizações, J final = 34,30, grupos com 28, 30, 30 e 32 clientes,
silhueta média = 0,717.

| Grupo | Idade | Compras/ano | Ticket médio | % on-line |
| --- | --- | --- | --- | --- |
| 1 | 41,4 | 6,1 | R$ 378,87 | 40,6% |
| 2 | 30,8 | 25,7 | R$ 174,11 | 24,2% |
| 3 | 52,3 | 3,9 | R$ 1.365,99 | 71,5% |
| 4 | 22,0 | 11,6 | R$ 98,89 | 89,3% |

**Dataset 3 (produtos bancários), k = 4:** 7 atualizações, J final = 48,21, grupos com 60, 45, 25 e 30 clientes,
silhueta média = 0,732.

| Grupo | Idade | Renda | Saldo médio | Produtos | % do limite |
| --- | --- | --- | --- | --- | --- |
| 1 | 38,2 | R$ 6.004,14 | R$ 4.743,24 | 3,9 | 42,8% |
| 2 | 21,0 | R$ 1.747,57 | R$ 705,79 | 1,4 | 74,6% |
| 3 | 67,6 | R$ 3.198,90 | R$ 27.394,37 | 2,6 | 8,1% |
| 4 | 48,0 | R$ 17.816,24 | R$ 57.395,26 | 6,9 | 22,2% |

Nos dois datasets o cotovelo e a maior silhueta ficam em k = 4.
