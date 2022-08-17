# TC-Zelda

</br>
<img width="788" alt="Screen Shot 2020-03-30 at 10 17 57 PM" src="https://raw.githubusercontent.com/Luizzgs/TC-Zelda/main/images/Zelda_Preview.png">

## Tópicos
1. [Introdução](#Introdução)
2. [Linguagens](#Linguagens)
3. [Características](#Características)
4. [Instruções](#Instruções)

## Introdução

Trabalho feito para a matéria de Teoria da Computação, inspirado no jogo Zelda clássico utilizando autômatos.

## Linguagens

**Javascript** <br/> 
Feito em Javascript puro sem qualquer dependência, utiliza sprites para definir o mundo e o jogador.

## Características




<br/> 


    ``` javascript
      //Cria o cenario
    const cenario = {
        spriteX: 0,
        spriteY: 0,
        largura: 720,
        altura: 620,
        x: 0,
        y: 100,
    
    desenha(){
        contexto.fillStyle = "black"
        contexto.fillRect(0,0, 720, 100);
        contexto.fillStyle = "white"
        contexto.fillText(resposta, 350, 60);
        contexto.drawImage(
        sprites,
            cenario.spriteX, cenario.spriteY, //Sprite x e y
            cenario.largura, cenario.altura, //Tamanho da sprite
            cenario.x, cenario.y, //Posição 
            cenario.largura, cenario.altura, //Tamanho
        );
    }
}
      
    ```


    ``` javascript
    //Verifica se a palavra pertence ao alfabeto
    function verificaAlfabeto(w) {
        if (alfabeto.includes(w)) {
            return true;
        }
        return false;
    }
    ```
    
## Instruções


