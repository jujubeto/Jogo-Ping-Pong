# Jogo-Ping-Pong
Aprendizado sobre Java Script - Curso Alura

## Funcionalidade
- Jogo Multijogador - Duas pessoas.
- Controles:

| Controle | Jogador  1 | Jogador 2  |
| ------------- | ------------- | ------------- |
| Para cima  | " W " | " ↑ " |
| Para baixo  | " S " | " ↓ " |
- Placar para contar os pontos.

## Sobre Desenvolvimento
- Desenvolvido em Java Script, HTML e CSS no Sketch.
- Variaveis e Funções da Bolinha, Raquete e Placar.
- Utilização de um arquivo puxado de p5.collide2D para funcionalidade de colisão da raquete:
```
function colisaoRaqueteBlibioteca(x, y){
  colidiu = collideRectCircle(x, y, raqueteComprimento, raqueteAltura, xBolinha, yBolinha, raio);
  if (colidiu){
    velocidadeXBolinha *= -1;
  }
    raquetada.play();
}
```
- Funções para Sons do Jogo:
Criamos a variavel e criação uma função "preload" onde atribuimos os caminhos dos arquivos de som, depois associamos do jeito que queremos que toque o som, ".loop()" vai tocar em um loop de tempo.
```
//sons do jogo
let trilha;

//delegando sons
function preload(){
  trilha = loadSound("trilha.mp3");
}
//cria o fundo por onde vai ser o jogo
function setup() {
  createCanvas(600, 400);
  trilha.loop();
}
```
- Funções de criação do Sketch.
A função "Draw()" vai executar tudo relacionado ao que você criar.
```
//executa todos os metodos/funções
function draw() {
  background(0);
  mostraBolinha();
  movimentaBolinha();
  verificaColisaoBordas();
  mostraRaquete(xRaquete, yRaquete);
  mostraRaquete(xRaqueteOponente, yRaqueteOponente);
  movimentaMinhaRaquete();
  colisaoRaqueteBlibioteca(xRaquete, yRaquete);
  colisaoRaqueteBlibioteca(xRaqueteOponente, yRaqueteOponente);
  movimentaRaqueteOponente();
  incluiPlacar();
  marcaPonto();
  bolinhaNaoFicaPresa();
}
```

