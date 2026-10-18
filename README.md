# Arrows

Jogo de quebra-cabeça no estilo *Arrows – Puzzle Escape*, feito em um único arquivo `index.html`.

## Como jogar

Abra o `index.html` no navegador. Toque numa seta para ela sair do tabuleiro na direção em que aponta.
Ela só sai se não houver outra seta no caminho. Tocar numa seta bloqueada custa uma vida (são 3 por fase).
Cada fase tem 2 dicas, que destacam uma seta que já pode sair.

## Como a dificuldade sobe

As fases são geradas automaticamente, de trás para frente: cada seta é colocada num lugar de onde
conseguiria sair naquele momento. Assim, tirar as setas na ordem inversa sempre resolve a fase, ou seja,
toda fase tem solução.

A cada fase:
- o tabuleiro cresce (de 4x4 até 9x9);
- mais casas ficam ocupadas;
- o gerador prefere colocar setas no caminho de outras, o que cria cadeias longas de dependência
  (A só sai depois de B, que só sai depois de C...).
