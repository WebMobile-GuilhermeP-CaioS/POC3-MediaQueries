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

Demonstração:

Antes
![image](https://github.com/user-attachments/assets/7dfc15e2-fade-4903-b25a-723336e35b8d)
Depois
![image](https://github.com/user-attachments/assets/903675f9-7d1b-41a0-8a92-5a48a2434f80)

