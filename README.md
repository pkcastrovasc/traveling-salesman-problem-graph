<img src="imgs/UNIFOR_logo1b.png" width="400">

# 🗺️ Trabalho Prático 4 - Problema do Caixeiro Viajante (TSP)

**Disciplina:** Resolução de Problemas com Grafos  
**Orientador:** Prof. Me Ricardo Carubbi  
**Instituição:** Universidade de Fortaleza (UNIFOR)  
**Autor:** Pedro Kauã Vasconcelos e Eduardo Suaki

---

## 📌 Sobre o Projeto

Este projeto implementa e compara duas heurísticas de construção de circuitos para o **Traveling Salesman Problem (TSP)**, ou Problema do Caixeiro Viajante. O objetivo principal não é encontrar a rota ótima (solução exata), mas sim construir soluções aproximadas de forma incremental e comparar a eficiência estrutural e o custo total de duas abordagens clássicas.

As cidades foram modeladas como pontos 2D no plano cartesiano, utilizando o cálculo de distância euclidiana para determinar o peso das arestas formadas. A base da implementação utiliza a biblioteca acadêmica `algs4` (Algorithms, 4th Edition).

## 🧠 Heurísticas Implementadas

Foram implementadas na classe `Tour` duas estratégias clássicas de inserção:

1. **Nearest Insertion (Inserção do Vizinho Mais Próximo):**
    * **Como funciona:** O algoritmo seleciona o ponto fora do circuito que possui a **menor distância física (euclidiana)** em relação a qualquer ponto já pertencente ao circuito atual. Em seguida, esse ponto é inserido imediatamente após o seu vizinho mais próximo.
    * **Foco:** Proximidade espacial do próximo nó.

2. **Smallest Insertion (Menor Inserção / Cheapest Insertion):**
    * **Como funciona:** O algoritmo testa a inserção do novo ponto entre todos os pares de cidades já conectadas no circuito. Ele escolhe a posição de inserção que gera o **menor aumento no comprimento total** da rota (variação $\Delta$).
    * **Foco:** Impacto global no custo do trajeto. Costuma gerar circuitos mais limpos e curtos do que a *Nearest Insertion*.
---
## 📁 Estrutura do Repositório

```text
t4-tsp/
├── README.md                 # Documentação do projeto
├── dados/                    # Bases de dados (pontos 2D)
│   ├── tsp10.txt             # Arquivo de depuração (10 cidades)
│   └── usa13509.txt          # Instância final (13.509 cidades dos EUA)
└── src/
    ├── Main.java             # Ponto de entrada e leitura de dados
    ├── Point.java            # Estrutura geométrica (Pontos 2D)
    ├── Tour.java             # [MODIFICADO] Lógica das Heurísticas
    └── TSPVisualizer.java    # Visualizador do circuito (via StdDraw)
```
---
## 🚀 Como Executar
**Pré-requisitos:**

* Java JDK instalado (versão 8 ou superior).

* Biblioteca algs4.jar configurada no classpath.

**Passo a passo (via Terminal/Linha de Comando):**

1. **Clone o repositório:**

```bash
git clone [https://github.com/](https://github.com/)[seu-usuario]/[nome-do-repositorio].git
cd [nome-do-repositorio]/src
```

2. **Execute o programa passando um arquivo de dados como entrada (<):**

- Para teste final:
    * No diretorio src, execute:
```bash
javac Main.java Point.java Tour.java TSPVisualizer.java In.java StdIn.java StdOut.java StdDraw.java
java Main ../dados/usa13509.txt
```

## 📊 Resultados e Observações
Durante a execução com a base usa13509.txt (13.509 cidades estadunidenses), é possível observar de forma clara via terminal a superioridade da heurística Smallest Insertion, que entrega um comprimento de circuito consistentemente menor do que a Nearest Insertion.

```text
(Nota: O funcionamento da interface gráfica TSPVisualizer pode depender de configurações específicas 
do ambiente (X11, dependências de UI do OS). 
Em caso de falha na renderização gráfica, os cálculos heurísticos e numéricos continuarão sendo 
exibidos com sucesso pelo terminal).
```

## 🎥 Apresentação em Vídeo
Uma explicação detalhada do código desenvolvido e a demonstração da execução deste projeto podem ser vistas no vídeo abaixo:

▶️ [Clique aqui para assistir ao vídeo de apresentação]([https://youtu.be/bMtidkV2A80])
