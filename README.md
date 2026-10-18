# Arrows

Jogo de quebra-cabeça no estilo *Arrows – Puzzle Escape*, feito em um único arquivo `index.html`.

## Como jogar

Abra o `index.html` no navegador. As setas são linhas compridas, às vezes com curvas. Toque numa seta para ela
deslizar para fora do tabuleiro, com o corpo seguindo a ponta. Ela só sai se não houver outra seta à frente da ponta. Tocar numa seta bloqueada custa uma vida (são 3 por fase).
Cada fase tem 2 dicas, que destacam uma seta que já pode sair.

## Como a dificuldade sobe

As fases são geradas automaticamente, de trás para frente: cada seta é colocada num lugar de onde
conseguiria sair naquele momento. Assim, tirar as setas na ordem inversa sempre resolve a fase, ou seja,
toda fase tem solução.

A cada fase:
- o tabuleiro cresce (de 5x5 até 10x10);
- mais casas ficam ocupadas;
- as setas ficam mais compridas e com mais curvas;
- o gerador prefere colocar setas no caminho de outras, o que cria cadeias longas de dependência
  (A só sai depois de B, que só sai depois de C...).
