
# Guess The Number

<p>Um jogo de adivinhação binária para dois jogadores baseado em conceitos de circuitos digitais.</p>


## Sobre o Jogo

<p>O "Guess The Number" é um desafio onde dois jogadores competem para adivinhar um número de 4 bits escolhido aleatoriamente. Cada jogador terá a oportunidade de fazer um palpite em formato binário, e o jogo fornecerá feedback sobre se o número chutado é maior, menor ou se o jogador acertou o número correto. O jogador que adivinhar o número primeiro é o vencedor.</p>


## Como Funciona

- [x] **Alternar Jogadores:** Um botão alterna entre os jogadores. Quando estiver em 0, é a vez do jogador 1. Quando mudar para 1, é a vez do jogador 2.

- [x] **Fazer Chutes:** O jogador ativo fará um chute pressionando quatro botões para inserir um número binário (0s e 1s).

- [x] **Confirmação:** Após fazer o chute, o jogador pressiona um botão para confirmar sua escolha.

- [x] **Dicas Visuais:** Três luzes LED mostram se o chute foi maior ou menor que o número secreto, caso seja igual o jogador vence.


## Screenshots

![image](https://github.com/israelrodrigues01/Guess_The_Number/assets/106749169/8dc82ba3-ce7c-4acd-a157-c39bda62d417)


## Como Jogar

  <p>1. Inicie o jogo. O jogador 1 começa.</p>
  <p>2. Pressione o botão de alternância para definir o jogador ativo (0 para jogador 1, 1 para jogador 2).</p>
  <p>3. O jogador ativo pressiona quatro botões para fazer um chute binário.</p>
  <p>4. Depois, pressiona o botão de confirmação.</p>
  <p>5. O número é mostrado em um display e as luzes LED indicam se o chute foi maior, igual ou menor que o número secreto.</p>
  <p>6. Caso o número digitado seja maior ou menor, passa a vez para o próximo jogador.</p>
  <p>7. Repita os passos 2 a 6 até que um jogador acerte o número.</p>
  <p>8. O jogador que acertar primeiro, ganha.</p>

## Funções (Componentes)
- **mux:**
<p>O componente mux (multiplexador), trata qual será a vez a do jogador, controlando por meio dos bits 0 (jogador 1) e o 1 (jogador 2). 
Então este componente é uma função que indica qual número será comparado.</p>

- **igualdade:**
<p>O componente igualdade terá a função de identificar se o número passado pelo a função mux é igual ao número secreto, onde será 1 quando forem iguais e 0 caso contrário.
</p>

- **maiorque:**
<p>O componente maiorque terá a função de informar qual dos dois números é maior, A ou B. Então ele recebe quatro entradas (4 bits) do número A e quatro entradas de B e retorna 1 se A > B (A maior que B) e 0 caso contrário.</p>

- **menorque:**
<p>Para o componente menorque usamos o componente maiorque e invertemos as entradas, pois onde era o número A colocamos B e onde era B colocamos A, logo retorna 1 se B > A e 0 caso contrário.</p>

- **comparador:**
<p>O componente comparador agrupa os três componentes anteriores (igualdade, maiorque e menorque), e retornar três saídas: Se o número entrada (E) é maior que o número secreto (S), então E > S retorna maior, se não se E < S retorna menor, se não retorna igual (S == E).</p>

- **game:**
<p>O componente game é o que faz a junção de todos os outros componentes anteriores e tem toda a mágica do projeto. Ele tem 10 entradas e 3 saídas, 8 entradas são dos números do jogador A e B, já as outras duas são para identificar qual número entrar (função do mux), A ou B, e qual momento jogar, quando for 1 indica que o jogador da vez quer ver seu palpite. As três saídas são as mesmas do comparador: maior, menor e igualdade. Dentro mesmo do componente, tem o número secreto, onde por ele vão ser feitas as comparações anteriores.</p>

- **decode:**
<p>O componente decode é o responsável por fazer todo o display de sete segmentos funcionar, ele é a junção de outros componentes que indica qual segmento do display ligar e mostrar qual número em quatro bits em hexadecimal. Então ele faz com que o display mostre valores de 0 ao 9 e de A ao F.</p>


## Documentação

<p>Disponível em: https://docs.google.com/document/d/10vjvVhAi29uzvd6Dxgp9YEu7-l8RR0a8fC_9Anu2z3I/edit?usp=sharing</p>

