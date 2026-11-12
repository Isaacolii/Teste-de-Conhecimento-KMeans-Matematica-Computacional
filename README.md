# Trabalho: implementação manual do K-means

**Matemática Computacional** · Prof. Dr. Alexsandro O. A. · Aluno: Isaac Oliveira

K-means feito do zero com NumPy, seguindo o [enunciado](https://github.com/alexsandro-fap/test-kmeans).

```bash
python kmeans_template.py
```

## Resultados

| Dataset | Atualizações | J final | Grupos | Silhueta |
| --- | --- | --- | --- | --- |
| 1 · entregas (k = 3) | 8 | 230,11 | 20, 22, 18 | 0,756 |
| 2 · vendas (k = 4) | 5 | 34,30 | 28, 30, 30, 32 | 0,717 |
| 3 · banco (k = 4) | 7 | 48,21 | 60, 45, 25, 30 | 0,732 |

Os 13 testes do dataset 1 passam. Nos datasets 2 e 3, o cotovelo e a maior silhueta ficam em k = 4.
