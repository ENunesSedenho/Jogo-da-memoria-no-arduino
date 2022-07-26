# Trabalho 2 - Jogo da memória com Arduino

Projeto da disciplina de Eletrônica para Computação, ministrada pelo Professor Eduardo Simões - USP São Carlos, ICMC. O objetivo é projetar e construir um circuito funcional utilizando o Arduino. Nesse caso, foi construido um jogo da memória com leds e efeitos sonoros, inspirado no Genius, utilizando um Arduino UNO.

> [Vídeo de demonstração do circuito](https://youtu.be/0idglTDbHpw)

## Grupo 44
|  Nº USP  |  Aluno  |
|---|---|
| 13671810 | Enzo Nunes Sedenho | 
| 13782369 | Luis Henrique Giorgetti Dantas | 
| 13672766 | Pedro Augusto Monteiro Delgado | 
| 13677239 | Yvin Miguel Juanico Carvalho | 

# Componentes da fonte

|  Qtd.  |  Componente |  Preço  |
|---|---|---|
| 1x | Arduino UNO | R$ XXX |
| 5x | Push button 4 pinos | R$ 0,70 |
| 1x | Buzzer ativo 5V | R$ 8,00 |
| 1x | Led difuso 5mm azul | R$ 2,00 |
| 1x | Led difuso 5mm verde | R$ 0,50 |
| 1x | Led difuso 5mm vermelho | R$ 0,50 |
| 1x | Led difuso 5mm amarelo | R$ 0,50 |
| 1x | Resistor 470 Ω | R$ 0,70 |
| 3x | Resistor 220 Ω | R$ 0,70 |
| 1x | Protoboard | - | - |
| 12x | Fios Jumpers | - | - |
| Total | - | R$ XXXX |

_Obs.: Os fios e a protoboard foram emprestados do laboratório._

# Diagramas do projeto

## Circuito no Tinkercad
> [Diagrama do circuito no simulador Tinkercad](https://www.tinkercad.com/things/316zUlV3nzP-brilliant-amur/editel?sharecode=ZDVESLm344NNm34ZEWPucYJBQrtOrZFcA-oQCMIJ-rM)
<img src="https://i.imgur.com/q7dexZ6.png">

## Esquemático no Tinkercad
> Diagrama esquemático do circuito no programa Tinkercad
<img src="https://i.imgur.com/GCvSZ0i.png">

# Fotos do circuito montado

> Visão geral do circuito
<img src="https://i.imgur.com/ngKpYBF.jpg">

> Conexões e componentes do circuito
<img src="https://i.imgur.com/lYcuxEG.jpg">

# Explicação do código
O código pode ser encontrado no link do [Tinkercad, na aba "Código" no canto superior direito.](https://www.tinkercad.com/things/316zUlV3nzP-brilliant-amur/editel?sharecode=ZDVESLm344NNm34ZEWPucYJBQrtOrZFcA-oQCMIJ-rM)

## Inicialização das variáveis globais
<img src="https://i.imgur.com/DDXITig.png">
Definimos um número máximo de números sorteados como 20, ou seja, a sequência máxima à ser memorizada é de 20 leds. As variáveis "numAtualSorteado" e "numAtualEscolhido" correspondem ao led correspondente da sequência sorteada, e aquele que foi escolhido pelo usuário, posteriormente, as variáveis são comparadas para analisar a continuidade do jogo. Nível corresponde ao nível em que o jogo se encontra, ou seja, quantas sequências já se passaram. "verifica" e "sortear" são auxiliares utilizadas no decorrer do código.

## Reiniciando o jogo
<img src="https://i.imgur.com/rnqmxho.png">
Essa função é encarregada de restaurar as variáveis para seus valores padrão. Quando a função é chamada, os leds brilham ao mesmo tempo e, na sequência, o nível volta para o 0 e os números são sorteados novamente.

## Errando uma sequência
<img src="https://i.imgur.com/3HcBvsu.png">
Quando o jogador erra a sequência, o programa inicia um laço para piscar repetidamente os leds e emitir efeitos sonoros (o laço ocorre por 3 vezes). Na sequência, os números sorteados são redeclarados para 0, e a função "reiniciar" é chamada para recomeçar o jogo.

## Acendendo os leds da sequência
<img src="https://i.imgur.com/XzuE4QT.png">
Cada número sorteado corresponde a um led, 1 para verde, 2 para vermelho, 3 para amarelo e 4 para azul.
Uma vez que o vetor de núemros sorteados foi inicializado com a sequência da atual rodada, essa função é iniciada. Um laço que vai de 0 até o nível atual (quantidade de números do vetor) faz com que, para cada posição deslocada no vetor, o led correspondente ao número brilhe e um efeito sonoro seja produzido.

## Verificando se o jogador acertou a sequência
<img src="https://i.imgur.com/uK3prFK.png">
Caso o usuário erre o led, a função de escolha errada é chamada, caso contrário, o led por ele selecionado brilha, e um efeito sonoro é emitido. Na sequencia, uma condicional verifica se o número de acertos corresponde ao nível atual do código, caso isso aconteça, significa que o usuário acertou toda a sequência, então o programa incrementa o nível, define a variável "verifica" como 0, sinalizando que não há mais nenhum número à ser verificado ("verifica" corresponde ao índice do vetor de números sorteados) e define a variável booleana "sortear" como verdadeira, indicando que um novo número deve ser sorteado. Se houver mais algum número à ser verificado no vetor, incrementamos a variável "verifica".

## Laço principal do programa
<img src="https://i.imgur.com/t9K0Rw6.png">
Caso o jogador tenha atingido o nível máximo, o jogo é reiniciado. Caso contrário, o programa analisa a variável "sortear", caso ela seja verdadeira, sorteamos um novo número correspondente ao nível e chamamos a função que mostra a sequência atual ao usuário. Na sequência, o programa lê o botão pressionado pelo usuário e chama a função para verificar se o número escolhido é o número correto. O botão superior no projeto (correspondente à D6 tem a função de reiniciar o programa, simplesmente para que não seja necessário reiniciar o arduino ou recompilar o código).

# Cálculos
> Cálculos realizados para projetar o circuito
<img src="https://i.imgur.com/XjGQf3z.png">

> [Vídeo explicativo sobre o projeto](https://youtu.be/_4TR3g88akQ)

