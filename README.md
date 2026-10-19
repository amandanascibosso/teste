# Arrows

Jogo de quebra-cabeça no estilo *Arrows – Puzzle Escape*, feito em um único arquivo `index.html`.

## Como jogar

Abra o `index.html` no navegador. As setas são linhas compridas, às vezes com curvas. Toque numa seta para ela
deslizar para fora do tabuleiro, com o corpo seguindo a ponta. Ela só sai se não houver outra seta à frente da ponta. Tocar numa seta bloqueada custa uma vida (são 3 por fase).
Cada fase tem 2 dicas, que destacam uma seta que já pode sair.

## Telas, controle e acessibilidade

- O tabuleiro cresce até ocupar a tela: no celular e no tablet em pé fica em uma coluna; com a tela
  deitada (tablet, computador, TV), o tabuleiro fica à esquerda e as informações numa coluna ao lado.
- Teclado: as setas movem um cursor pelo tabuleiro, `Enter` toca na seta e `D` pede dica.
- Controle de videogame: direcional (ou alavanca) move o cursor, `A` toca, `Y` pede dica e `Start`
  confirma as telas de vitória e derrota.
- Menu **Acessibilidade**: texto e selos maiores, setas mais grossas, alto contraste e tema (automático,
  claro ou escuro). As escolhas ficam salvas no aparelho.
- O zoom por toque duplo e por pinça fica bloqueado, para não ampliar a tela sem querer durante o jogo.
- Leitores de tela anunciam a casa sob o cursor (por exemplo, "Seta apontando para baixo, número 2").

## Como a dificuldade sobe

As fases são geradas automaticamente e o tabuleiro fica sempre cheio, sem casas vazias. Primeiro o
tabuleiro inteiro é dividido em caminhos (o corpo das setas). Depois o gerador escolhe para que lado cada
seta aponta, tirando uma por vez só quando o caminho à frente da ponta já está vazio. Assim, toda fase
tem solução.

A cada fase:
- o tabuleiro cresce uma casa de lado a cada 4 fases (de 9x9 até 15x15);
- as setas ficam mais compridas e com mais curvas;
- o gerador prefere as escolhas que criam cadeias longas de dependência
  (A só sai depois de B, que só sai depois de C...).

## Empecilhos

Cada empecilho aparece primeiro sozinho, numa fase de apresentação que explica a regra. Depois ele volta
misturado com os outros, com no máximo 3 por fase (na maioria das vezes 1 ou 2). Na primeira vez que um
empecilho aparece, uma tela explica a regra. A lista de regras da fase fica embaixo do tabuleiro.

| Fase | Empecilho | Regra |
| ---: | --- | --- |
| 3 | Buraco | Casa vazia no meio do tabuleiro; as setas passam por ela. |
| 5 | Parede | Bloco fixo que nunca sai e bloqueia o caminho. |
| 7 | Rastro | Quando sai, a seta deixa uma parede na casa logo à frente da ponta. |
| 9 | Borda fechada | Nenhuma seta sai pelo lado com a barra. |
| 11 | Setas numeradas | Saem em ordem: 1, 2, 3... |
| 13 | Interruptor e porta | A seta com interruptor abre ou fecha as portas da mesma cor quando sai. |
| 15 | Seta teimosa | Precisa de vários toques (×2, ×3). |
| 17 | Cadeado e chave | A seta com cadeado só sai depois da seta com a chave da mesma cor. |
| 19 | Seta de duas pontas | Sai pela ponta mais perto do toque. |
| 21 | Seta congelada | Só sai quando nenhuma outra seta estiver encostada nela. |
| 23 | Grupos de cores | As laranja saem antes das verdes. |
| 25 | Bomba-relógio | Diminui a cada jogada; se chegar a zero, você perde. |
| 27 | Limite de toques | Número máximo de toques, contando os erros. |
| 29 | Portal | A seta entra num portal e continua pelo outro da mesma cor. |
| 31 | Ponta escondida | A ponta só aparece quando a casa à frente dela fica vazia. |
| 33 | Seta giratória | Gira um quarto de volta a cada jogada. |
| 35 | Seta fantasma | Aparece e some a cada jogada; apagada, não bloqueia nem pode ser tocada. |
| 37 | Neblina | Só dá para ver as bordas e o que fica perto das setas que já saíram. |

## Armadilhas e estrelas

Sem armadilhas, tirar uma seta livre nunca atrapalha, então basta ir achando setas livres. O rastro e o
interruptor mudam isso: tirar a seta na hora errada pode deixar a fase sem solução. Para cada fase, o
gerador cria vários tabuleiros, joga dezenas de partidas tocando em setas livres ao acaso e, nas fases mais
avançadas, fica com o tabuleiro em que mais partidas assim terminam sem saída.

A dica mostra uma jogada que ainda leva à vitória. Se a ordem escolhida já travou a fase, ela avisa e não
gasta a dica.

Ao vencer, você ganha 3 estrelas sem nenhum erro, 2 com um erro e 1 com mais. O total fica no topo da tela.

Todo tabuleiro é conferido antes de aparecer: o gerador joga a solução com todas as regras e só aceita
a fase se ela puder ser vencida.
