# Robotron 2000

![robotron](https://user-images.githubusercontent.com/104650333/232256486-309d8070-e9d8-4c1f-87dc-50ce289c3458.png)

<a href="https://robotron-2000-662i-i76cugtw1-bruleonel.vercel.app/">Clique aqui para ver o projeto</a>

## document.getElementById()
- retorna o elemento e atravéz do id e asism você pode manipulá-lo.

## document.getElementClassName()
- retorna o elemento e atravéz da classe e asism você pode manipulá-lo.

## document.querySelector()
- retorna o elemento e atravéz da classe oi id e asism você pode manipulá-lo.

## O que é DOM?
- O DOM é uma interface de linguagem neutra que permite que o documento HTML seja atualizado dinamicamente.

O DOM (Document Object Model) e o JavaScript, juntos, possuem grande poder de modificar dinamicamente a estrutura de um documento HTML. Sendo possível, por exemplo:

Adicionar/modificar/remover tags, textos, imagens e qualquer elemento no HTML.
Alterar estilos CSS da página.
Criar novos eventos HTML.
Vamos conferir formas de realizar os itens listados no tópico acima.

Métodos para selecionar elementos no HTML

document.getElementByID(id) - Selecionar um elemento pelo ID.
document.getElementsByTagName(name) - Selecionar um elemento pelo nome.
document.getElementsByClassName(name) - Selecionar um elemento pelo nome da classe.
Propriedades e métodos para alterar elementos no HTML

element.innerHTML - Esta propriedade obtém ou altera qualquer elemento no HTML, inclusive tags.
element.innerText - Esta propriedade permite inserir textos no HTML.
element.attribute - Esta propriedade altera o valor de um elemento HTML
element.setAttribute(atributo, valor) - Este método altera o valor de um atributo de um elemento HTML.
Adicionando e excluindo elementos

document.write() - Escreve no fluxo de saída do HTML.
document.appendChild() - Adiciona um elemento HTML.
document.removeChild() - Remove um elemento HTML.
document.replaceChild() - Substitui um elemento HTML.
document.createElement() - Cria um elemento HTML.

## Mudanças no código:

```ruby

//const controle = document.querySelectorAll(".controle-ajuste");
const controle = document.querySelectorAll("[data-controle]");

controle.forEach((elemento) => {
    elemento.addEventListener('click', (evento) => { 
        //manipulaDados(evento.target.textContent, evento.target.parentNode);
        manipulaDados(evento.target.dataset.controle, evento.target.parentNode);
    });
})


function manipulaDados(operacao, controle) {
    const peca = controle.querySelector(".controle-contador")
    if (operacao === "-") {
        peca.value = parseInt(peca.value) - 1;
    }
    else {
        peca.value = parseInt(peca.value) + 1;
    }
}

```

Com o evento.target.textContent o js recebia o valor do conteúdo do botão,dessa forma o css fica acoplado ao Js, o que não é legal, mas com o "[data-controle]" e  evento.target.dataSet.controle ele recebe o valor do atributo data.

Também arrumei o 

````ruby
    const peca = controle.querySelector("[data-contador]");
````
