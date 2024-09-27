# POC3 - Media Queries

## Alunos:

* Caio Sampaio. RA: 10381053;
* Guilherme Picoli. RA: 10389843;
* Caio Filardi. RA: 10341128.

## Enunciado

Para esta Prova de Conceito, você deve mostrar como funcionam as media queries no CSS. As seguintes regras das mediaqueries devem ser exploradas:

* Print - apenas impressão
* Larguras de dispositivos diferentes (pelo menos smartphone, tablet e desktop)
* Disposição dos dispositivos (landscape e portrait)

Aproveite para criar exemplos que façam sentido com os breakpoints e não apenas mudar a cor de uma div. Você pode construir menus, galerias de imagens, textos em mais de uma coluna, entre muitas outras aplicações.

## POC 3

Para essa POC, criamos um galeria de imagens que simula uma galeria de uma rede social. Assim aplicaremos os conceitos de Media Queries.

### **Print - apenas impressão**:

A Media Query para impressão (print) permite diferenciar os estilos das sua página para impressão, podendo ser usada para várias aplicações. Por exemplo, adicionar marcas d'água, esconder e redimencionar elementos e/ou alterar cores. No exemplo abaixo, alteramos as cores do background do Body, trocamos as cores dos textos e títulos do Site para preto, adicionamos uma borda preta de 1px na galeria e escondemos o menu lateral:

`@media print {
    nav {
        display: none;
    }
    body {
        font-size: 12pt;
        color: black;
        background-color: #fff;
    }
    main h1{
        color: #000;
        text-shadow: none;
    }
    .gallery {
        border: 1px solid #333;
    }
    .gallery img {
        width: 100%;
        height: 100%;
    }
    .gallery img:hover {
        width: 100%;
        height: 100%;
    }
    nav {
        display: none;
    }
    * {
        background: none !important;
        color: black !important;
    }`

Demonstração:

Tela de Computador:
![image](https://github.com/user-attachments/assets/362178d3-b5bb-402c-b610-eccb94c389aa)

Print:
![image](https://github.com/user-attachments/assets/1ad92ba3-bb76-4806-aee9-41233b195c33)


### Larguras de dispositivos diferentes (pelo menos smartphone, tablet e desktop):  

Inicialmente, priorizamos as telas de Desktop (Desktop First), assim todos os nossos estilos para telas Desktop foram definidos fora de uma Media Query:

`body {
    font-family: Arial, sans-serif;
    display: flex;
    margin: 0px;
    background-color: #929292;
}
nav {
    background-color: #333;
    color: white;
    padding-right: 15px;
    padding-left: 15px;
    width: 120px;
}
nav ul {
    list-style: none;
    display: block;
    margin: 0px;
    padding: 0px;
}
nav ul li {
    margin-right: 0px;
    margin-top: 15px;
}
main{
    padding: 5px;
}
main h1{
    text-align: center;
    color: rgb(192, 2, 40);
    text-shadow: 1px 0 #fff, -1px 0 #fff, 0 1px #fff, 0 -1px #fff,
             1px 1px #fff, -1px -1px #fff, 1px -1px #fff, -1px 1px #fff;
}
.gallery {
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    gap: 10px;
    padding: 10px;
}
.gallery img {
    width: 100%;
    height: 100%;
}
.gallery img:hover {
    width: 600px;
    height: auto;
}`

Posteriormente, definimos as telas de celulares com a Media Query para tamanho máximo de tela, assim retiramos o menu da lateral do site e o colocamos no topo do site. Ademais, alteramos a disposição interna dos itens do menu, deixando-os na horizontal, o tamanho das letras e do menu, para 60px, e mantivemos o menu fixo na tela (além de dar um espaço de 50px entre o menu e a galeria):

`@media (max-width: 600px) {
    nav {
        position: fixed;
        width: 100%;
        height: 50px;
    }
    nav ul {
        display: flex;
    }
    nav ul li {
        margin-right: 10px;
        font-size: 0.75em;
    }
    main {
        padding-top: 50px;
    }
}`

Por fim, definimos as telas de tables com a Media Query para tamanho mínimo e máximo de tela, assim retiramos o menu da lateral do site e o colocamos no topo do site em posição absoluta. Ademais, alteramos a disposição interna dos itens do menu, deixando-os na horizontal, o tamanho das letras e do menu, para 60px, e colocamos um espaço de 60px entre o menu e a galeria:

`@media (min-width: 601px) and (max-width: 1024px){
    nav {
        position: absolute;
        width: 100%;
        height: 60px;
    }
    nav ul {
        display: flex;
    }
    nav ul li {
        margin-right: 20px;
        font-size: 2em;
    }
    main {
        padding-top: 60px;
    }
}`


Demonstração:

Tela de Computador:
![image](https://github.com/user-attachments/assets/362178d3-b5bb-402c-b610-eccb94c389aa)

Tela de Celular:
![image](https://github.com/user-attachments/assets/365fa8fe-2e4d-4759-a051-383ee9a2e52c)

Tela de Tablet:
![image](https://github.com/user-attachments/assets/fb8407e8-1a78-4ff0-a0cc-d60b6b8b51e7)

### Disposição dos dispositivos (landscape e portrait):

A Media Query para disposição dos dispositivos (orientation:) permite diferenciar os estilos das sua página conforme a disposição da tela. Assim, alteramos a quantidade de imagens por linha na galeria com o uso das disposições landscape e portrait. Com portrait comportando dois itens por linha e landscape quatro itens por linha. Vale notar que essa diferenciação também afeta outras Media Queries (como print e tamanho de tela), porém não achamos necessário tomar quaisquer ações para evitar essa interferência no nosso exemplo.

`@media (orientation: portrait) {
    .gallery {
        grid-template-columns: repeat(2, 1fr);
    }
}
@media (orientation: landscape) {
    .gallery {
        grid-template-columns: repeat(4, 1fr);
    }
}`

Demonstração:

Landscape:
![image](https://github.com/user-attachments/assets/bf88a739-6ea9-41b7-8576-4dd97bcde1f9)

Portrait:
![image](https://github.com/user-attachments/assets/57d33fd0-f98f-45d0-be01-faa1771fd897)
