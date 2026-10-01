# Problema do Caixeiro Viajante (TSP)

Implementação em C de duas abordagens para o TSP:

- `src/exactly.c`: algoritmo exato por Branch and Bound (backtracking com poda), com limite de tempo.
- `src/approximate.c`: algoritmo aproximativo da árvore (2-aproximativo), com MST pelo algoritmo de Prim O(n²) e percurso em pré-ordem.

## Requisitos

- Compilador C (GCC) e `make`.

Não há dependências externas.

## Compilação

Na pasta `TSP/`:

```bash
make
```

Isso gera os executáveis `approximate` e `exactly`. Sem `make`:

```bash
gcc -O2 -o approximate src/approximate.c
gcc -O2 -o exactly src/exactly.c
```

## Execução

Uma instância:

```bash
./approximate data/tsp1_253.txt
./exactly data/tsp1_253.txt         # limite padrão: 600 s
./exactly data/tsp5_27603.txt 60    # limite de 60 s
```

Todas as instâncias:

```bash
make rodar-aproximativo
make rodar-exato                    # limite padrão: 600 s por instância
make rodar-exato LIMITE_TEMPO=60    # limite de 60 s por instância
```