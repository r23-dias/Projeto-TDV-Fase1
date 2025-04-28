# Projeto-TDV-Fase1

Trabalho realizado no âmbito da cadeira de "Técnicas de Desenvolvimento de Videojogos", lecionada na Licenciatura em Engenharia e Desenvolvimento de Jogos Digitais, do Instituto Politécnico do Cávado e do Ave.
O trabalho envolve a escolha de um projeto de um videojogo, desenvolvido em ambiente C# a 3 dimensões, e posteriormente realizar a sua apropriada documentação e estudo de Implementação.

O projeto escolhido neste relatório é da autoria do utilizador do GitHub "tylersriver" que desenvolveu uma versão digital e pouco complexa do jogo de tabuleiro Connect 4 (ou "Quatro em Linha") em ambiente C# utilizando Windows Forms do Microsoft Visual Studio Professional 2013. 

Link do GitHub do projeto documentado: https://github.com/tylersriver/Connect-4/tree/master

# Connect 4 game

João Miguel dos Santos Veloso (31492)

Nuno Gonçalves Soares (33220)

Rodrigo Vieira Dias (31081)


# 1- Descrição da implementação do Videojogo

## Objetivo do Jogo: 

O objetivo do videojogo Connect 4 (ou "Quatro em Linha") é alinhar quatro peças da tua cor (horizontalmente, verticalmente ou na diagonal) antes do adversário.

Explicando mais detalhadamente:

- Dois jogadores jogam alternadamente.

- Cada um, na sua vez, deixa cair uma peça numa coluna do tabuleiro.

- A peça ocupa o espaço mais baixo livre dessa coluna.

- O primeiro jogador a formar uma linha contínua de quatro peças vence.

- Se o tabuleiro ficar cheio e ninguém conseguir alinhar quatro peças, o jogo termina em empate.

## Linguagens de Programação utilizadas:
C#

## Programa de Desenvolvimento: 
Microsoft Visual Studio Professional 2013

## Plataformas: 
Windows

# 2- Decisões de Desenvolvimento

## Uso de linguagem C#:

- Simplicidade e Organização:
C# é uma linguagem moderna, com uma sintaxe limpa e fácil de entender, o que facilita a manutenção e a leitura do código — ideal para projetos académicos ou pequenos videojogos como este.

- Programação Orientada a Objetos:
C# é completamente orientado a objetos, o que é perfeito para estruturar o jogo em classes como Jogador, Tabuleiro, Peça, etc., tornando o código mais modular e organizado.

- Boa Integração com o Windows:
Como o Connect 4 é um jogo simples e não precisa de gráficos avançados, usar C# numa plataforma como o Windows facilita a execução direta e aproveita melhor as APIs do próprio sistema operativo.

## Uso de Windows Forms:

- Rápido para criar interfaces gráficas:
Windows Forms permite desenhar botões, painéis e outros elementos gráficos de forma muito rápida e visual, sem precisar de muita programação complexa.

- Ideal para jogos 2D simples:
Para um jogo como o Connect 4, onde basta desenhar círculos (as peças) e um tabuleiro, Windows Forms é suficiente — não há necessidade de motores gráficos pesados como Unity ou frameworks como MonoGame.

- Ferramentas de arrastar-e-soltar no Visual Studio:
O Visual Studio Professional 2013 tem uma interface muito boa para criar janelas e componentes gráficos arrastando elementos (drag-and-drop), o que acelera muito o desenvolvimento.

- Compatibilidade e Estabilidade:
Como é tecnologia da própria Microsoft, Windows Forms é muito estável em ambientes Windows, o que garante que o jogo corre sem grandes problemas em PCs que usem esse sistema.

# 3- Instruções de Jogo

## Executar o Jogo: 

Para executar o jogo, deve ser, primeiramente, feito o download a partir do repositório do utilizador autor, link este colocado no início deste relatório e no fim desta secção. Após isto, todos os ficheiros devem ser extraídos e nos novos ficheiros seguir a seguinte ordem de abertura de pastas: Connect-4-master\Connect4\Connect4\bin\Debug\Connect4.exe.
Ao chegarem ao ficheiro .exe deve, o mesmo, ser executador e a partir daí está o jogo em execução.

Link do GitHub do projeto documentado: https://github.com/tylersriver/Connect-4/tree/master

## Interface do Jogo

O executável apresenta numa tela branca os seguintes componentes:

- Grelha de jogo com quadrados com círculos destacados à semelhança do tabuleiro original -> Localizada à direita
  
- Caixa de Texto a indicar o jogador que deve jogar a seguir -> Topo esquerdo
  
- Botão de Reset -> Localizado no topo esquerdo abaixo da caixa de texto
  

## Instruções de Controlo do Jogo

O jogo é inteiramente jogado com o rato ou touchpad do computador. O utilizador ao clicar na grelha de jogo, seja em que espaço for, será calculada a posição da peça tendo em conta a posição mais baixa da coluna onde o input surgiu. No primeiro input joga o jogador 1 e, seguidamente, joga o jogador 2, alternando assim a vez dos jogadores até a grelha se encher ou um dos jogadores alinhar 4 das suas peças em linha (horizontal, vertical, horizontal). 

Ao ser determinado um vencedor, é automaticamente anunciado numa janela nova o vencedor e o jogo recomeça com a grelha limpa novamente na vez do jogador 1. É possível fazer uma limpeza precoce da grelha utilizando o botão "reset" previamente discutido. 

# 4- Organização dos ficheiros e Pastas

## Assets
Properties/Resources.resx

Aqui podem estar armazenadas imagens ou strings usadas no Form.

## Código principal

Form1.cs — Contém a lógica de interação com o utilizador (UI + eventos).

Form1.Designer.cs — Gerado automaticamente, contém o layout (posição de botões, labels, etc.).

Game.cs — Implementa a lógica do jogo (Parte que gere o tabuleiro e o fluxo do jogo).

Program.cs — Contém a função Main(), ponto de entrada da aplicação.

## Configurações da aplicação

App.config — Pode conter configurações gerais (neste caso, está presente mas parece vazio).

Properties/Settings.settings — Definições de settings (configurações específicas da aplicação como, por exemplo, largura da janela, cores, etc.).

Properties/Resources.resx — Recursos visuais e de texto da aplicação.

## Organização

A organização atual do projeto facilita a manutenção, especialmente devido à separação entre o código da interface gráfica e a lógica de jogo. Cada responsabilidade está relativamente bem isolada, o que torna o código mais claro e simples de modificar. Apesar disso, numa perspetiva de crescimento futuro, poderia ser interessante criar uma estrutura de pastas mais específica para separar a lógica de jogo da interface, o que tornaria a escalabilidade e a manutenção ainda mais fáceis.

# 5- Análise do Código

## Resumo de Análise do Código

O código implementa o jogo Connect 4 usando Windows Forms em C#.
Tem uma divisão razoável entre lógica de jogo e interface gráfica.
A implementação é funcional, mas há partes que poderiam ser melhoradas em clareza, nomeação de variáveis e reutilização de código.
Há boas práticas presentes, mas também repetições e pequenas omissões (ex.: salvar/jogo incompleto).



## Estrutura do código

O projeto é modular.

 
Program.cs: ponto de entrada.

Form1.cs e Form1.Designer.cs: interface gráfica.

Game.cs: lógica do jogo.


Portanto, não está tudo num ficheiro, está bem separado.



## Qualidade do código

-Comentado: Sim, tem vários comentários úteis.

-Limpo: Moderadamente — podia ser mais organizado e evitar repetições.

-Fácil de entender: Sim, especialmente para quem tem conhecimento prévio de Windows Forms e C#.


Algumas variáveis são pouco claras (X, full), mas no geral é um código compreensível.

## Boas práticas usadas

-Separação Lógica: Sim, boa separação entre lógica de jogo e interface.

-Nomes de variáveis: Em geral bons, mas alguns nomes são pouco descritivos.

-Uso de enum para estado do tabuleiro: Muito positivo.

-Tratamento de eventos: Correto.

-Comentários: Presentes e úteis.

-Problemas: Algumas repetições podiam ser refatoradas, e a gestão de gravação/carregamento do jogo está incompleta.




