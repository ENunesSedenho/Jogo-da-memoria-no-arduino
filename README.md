# Trabalho 2 - Jogo da memória com Arduino

Projeto da disciplina de Eletrônica para Computação, ministrada pelo Professor Eduardo Simões - USP São Carlos, ICMC. O objetivo é projetar e construir um circuito funcional utilizando o Arduino. Nesse caso, foi construido um jogo da memória com leds e efeitos sonoros, inspirado no Genius, utilizando um Arduino UNO.

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
| 5x | Push button | R$ 0,70 |
| 1x | Buzzer ativo 5V | R$ 8,00 |
| 1x | Led difuso 5mm azul | R$ 2,00 |
| 1x | Led difuso 5mm verde | R$ 0,50 |
| 1x | Led difuso 5mm vermelho | R$ 0,50 |
| 1x | Led difuso 5mm amarelo | R$ 0,50 |
| 1x | Resistor 470 Ω | R$ 0,70 |
| 3x | Resistor 220 Ω | R$ 0,70 |
| 1x | Protoboard | - | - |
| Total | - | R$ XXXX |

_Obs.: Os fios e a protoboard foram emprestados do laboratório._

# Diagramas do projeto

## Circuito no Tinkercad
> [Diagrama do circuito no simulador Tinkercad!!!!!!](https://tinyurl.com/29mso46y)
<img src="https://i.imgur.com/q7dexZ6.png">

## Esquemático no Tinkercad
> Diagrama esquemático do circuito no programa Tinkercad
<img src="https://i.imgur.com/GCvSZ0i.png">


## Fotos do circuito montado

> Visão geral do circuito
<img src="https://i.imgur.com/Ky8oyaa.jpg">

> Tensão mínima fornecida pelo circuito
<img src="https://i.imgur.com/XeoWRnE.jpg">

> Tensão máxima fornecida pelo circuito
<img src="https://i.imgur.com/J0DqqGh.jpg">

# Cálculos
> Cálculos realizados para projetar o circuito
<img src="https://i.imgur.com/K7KXgve.png">

> [Vídeo explicativo sobre o projeto](https://youtu.be/uK48WSZexMw)

# Diagramas do projeto 

## Simulação do projeto no Tinkercad

<img src="https://i.imgur.com/TExPbqC.png">

## Diagrama esquemático no Tinkercad

<img src="https://i.imgur.com/KfnWCMk.png">

* **Link para a simulação do projeto no Tinkercad:** https://www.tinkercad.com/things/316zUlV3nzP-brilliant-amur/editel?tenant=circuits

## Foto do projeto montado

# Explicação do código

<img src="https://i.imgur.com/DDXITig.png">

## Inicialização das variáveis globais:
Definimos um número máximo de números sorteados como 20, ou seja, a sequência máxima à ser memorizada é de 20 leds.
As variáveis "numAtualSorteado" e "numAtualEscolhido" correspondem ao led correspondente da sequência sorteada, e aquele que foi escolhido pelo usuário, posteriormente, as variáveis são comparadas para analisar a continuidade do jogo.
Nível corresponde ao nível em que o jogo se encontra, ou seja, quantas sequências já se passaram.
"verifica" e "sortear" são auxiliares utilizadas no decorrer do código.

<img src="https://i.imgur.com/rnqmxho.png">

## Reiniciando o jogo:
Essa função é encarregada de restaurar as variáveis para seus valores padrão.
Quando a função é chamada, os leds brilham ao mesmo tempo e, na sequência, o nível volta para o 0 e os números são sorteados novamente.

<img src="https://i.imgur.com/3HcBvsu.png">

## Função para a escolha errada:
Quando o jogador erra a sequência, o programa inicia um laço para piscar repetidamente os leds e emitir efeitos sonoros (o laço ocorre por 3 vezes).
Na sequência, os números sorteados são redeclarados para 0, e a função "reiniciar" é chamada para recomeçar o jogo.

<img src="https://i.imgur.com/IY2SMWS.png">

<img src="https://i.imgur.com/rb3qi1F.png">

## Mostrando a sequência dos leds sorteados:
Cada número sorteado corresponde a um led, 1 para verde, 2 para vermelho, 3 para amarelo e 4 para azul.
Uma vez que o vetor de núemros sorteados foi inicializado com a sequência da atual rodada, essa função é iniciada.
Um laço que vai de 0 até o nível atual (quantidade de números do vetor) faz com que, para cada posição deslocada no vetor, o led correspondente ao número brilhe e um efeito sonoro seja produzido.

<img src="https://i.imgur.com/uK3prFK.png">

## Verificando se o usuário acertou a sequência:
Caso o usuário erre o led, a função de escolha errada é chamada, caso contrário, o led por ele selecionado brilha, e um efeito sonoro é emitido.
Na sequencia, uma condicional verifica se o número de acertos corresponde ao nível atual do código, caso isso aconteça, significa que o usuário acertou toda a sequência, então o programa incrementa o nível, define a variável "verifica" como 0, sinalizando que não há mais nenhum número à ser verificado ("verifica" corresponde ao índice do vetor de números sorteados) e define a variável booleana "sortear" como verdadeira, indicando que um novo número deve ser sorteado.
Se houver mais algum número à ser verificado no vetor, incrementamos a variável "verifica".

<img src="https://i.imgur.com/J7aBFof.png">

<img src="https://i.imgur.com/YtT0WJr.png">

## Laço principal do programa:
Caso o jogador tenha atingido o nível máximo, o jogo é reiniciado.
Caso contrário, o programa analisa a variável "sortear", caso ela seja verdadeira, sorteamos um novo número correspondente ao nível e chamamos a função que mostra a sequência atual ao usuário.
Na sequência, o programa lê o botão pressionado pelo usuário e chama a função para verificar se o número escolhido é o número correto. 
O botão superior no projeto (correspondente à D6 tem a função de reiniciar o programa, simplesmente para que não seja necessário reiniciar o arduino ou recompilar o código).


## Componentes do projeto

|  Quantidade  |  Componente  |  Especificações  |  Preço  |
|---|---|---|---|
| 1x | Arduino UNO | Arduíno UNO 5V Atmega328 Smd | R$ 110,00 |
| 1x | Buzzer | Sonalarme SEM-12A-3 / 7V-C-N 3A 7V DIGILECT| R$ 8,50 |
| 2x | Resistor 220Ω | Resistor CR25 220R Carvão | R$ 0,14 |
| 1x | Resistor 100Ω | Resistor CR25 100R Carvão ROHS | R$ 0,07 |
| 1x | Resistor 470Ω | Resistor CR25 100R Carvão LGE | R$ 0,20 |
| 1x | LED vermelho | LED 5MM VM Difuso 333-2SDRD/S530-L EVERLIGHT | R$ 0,50 |
| 1x | LED amarelo | LED 5MM AM Difuso 333UTD/S530-A3 EVERLIGHT | R$ 0,50 |
| 1x | LED verde | LED 5MM VR Difuso EVERLIGHT | R$ 0,50 |
| 1x | LED azul | LED 5MM AZ Difuso EVERLIGHT | R$ 2,00 |
| 12x | Fios Jumpers | - | - |
| 4x | Fios | - | - |
| 1x | Protoboard | - | - |
| Total | - | - | R$ 122,55 |

* Obs.: Os fios e protoboard foram emprestados do laboratório.



# Vídeos
