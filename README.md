# README - Projeto K-Means Paralelizado com OpenMP e CUDA

## Descrição Geral

Este projeto implementa o algoritmo de agrupamento **K-Means** em C/C++, com três versões paralelas:

1. **Versão sequencial**: `KMeans_Serial.c`
2. **Versão paralela OpenMP (CPU)**: `KMeans_CPU.c`
3. **Versão paralela OpenMP com atomics (simulação GPU)**: `KMeans_GPU.c`
4. **Versão paralela CUDA**: `KMeans_CUDA.cu`

As versões utilizam uma base de 100.000 pontos aleatórios em distribuição circular, agrupados em 5 clusters.

---

## Compilação

### 1. Versão Sequencial

```bash
gcc -O3 -o KMeans_Serial KMeans_Serial.c -lm
```

### 2. OpenMP CPU

```bash
gcc -O3 -fopenmp -o KMeans_CPU KMeans_CPU.c -lm
```

### 3. OpenMP (simulação de GPU)

```bash
gcc -O3 -fopenmp -o KMeans_GPU KMeans_GPU.c -lm
```

### 4. CUDA

```bash
nvcc -O3 -o KMeans_CUDA KMeans_CUDA.cu
```

---

## Execução

### 1. Visualizar o resultado

Cada versão imprime uma coordenada contendo a visualização dos clusters.

Execute redirecionando a saída para um arquivo:

```bash
./KMeans_Serial > Resultado_Serial.txt
./KMeans_CPU > Resultado_CPU.txt
./KMeans_GPU > Resultado_GPU.txt
./KMeans_CUDA > Resultado_CUDA.txt
```

### 2. Ver tempo de execução

As versões paralelas mostram o tempo total em segundos no final da execução.

---

## Requisitos

* GCC com suporte a OpenMP (versão 8+ recomendada)
* CUDA Toolkit (versão 11+)
* `make` (opcional)

---

## Observações

* Para resultados consistentes, execute em máquinas com múltiplos núcleos ou GPUs dedicadas.
* As versões foram testadas com `k=5` e `100000` pontos.

---

## Autores

* Base original: [https://github.com/Lakhan-Nad/KMeans-C](https://github.com/Lakhan-Nad/KMeans-C)
* Adaptações e paralelização realizadas pelo grupo de Sistemas Paralelos e Distribuídos (PUC Minas - 2025)