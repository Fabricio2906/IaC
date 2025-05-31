
# LabirintoRobo

Projeto em C# que simula um robô que percorre uma matriz 10x10 desviando de obstáculos e buscando pontos de energia, com movimentação em 4 direções.

## Como executar

1. Certifique-se de ter o .NET SDK instalado (8.0 ou superior).
2. Execute no terminal:
3- Qualquer coisa no terminal digite dotnet run --:(Caminho da sua máquina que está esse arquivo\LabirintoRobo.csproj 
```
dotnet restore
dotnet run
```
**Models/TipoDePosicao.cs**  
 Lista que simboliza os diversos tipos de células que podem existir no labirinto:
  - `Normal`
  - `Obstaculo`
  - `Energia5` (ganha 5 de energia)
  - `Energia10` (ganha 10 de energia)
  - `PosicaoNaoVisitavel` (bloqueada)

- **Util/ClasseDeUtilidade.cs**  
A lógica para:
- Construir o labirinto a partir de posições aleatórias.
O labirinto deve ser impresso no console.

- Determinar a rota viável para o robô chegar ao destino final, de acordo com o consumo ou ganho de energia das células.

##  Lógica do Labirinto

Inicialmente, a matriz 10x10 é preenchida com células do tipo 'Normal'.
São acrescentadas:
- 5 células identificadas como 'Energia5`

- 3 utilizando `Energia10`
- Variáveis aleatórias de 15 a 34 obstáculos (`Obstáculo`)
Sempre há espaço entre as posições (0,0) e (9,9).

##  Movimentação do Robô

- A energia inicial do robô é de 50.
O algoritmo de pesquisa emprega uma **fila (BFS)** na tentativa de descobrir a rota mais curta até (9,9).

- A cada passo:
- Cada célula normal consome 1 energia.
- Barreiras e posições interditadas não podem ser transpostas.
- Células energéticas diminuem o custo do deslocamento.
