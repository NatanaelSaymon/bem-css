## ORGANIZANDO CSS COM SASS E BEM

## BEM - O que é?

Significa Block Element Modifier, que são as espeficações que seguiremos nesse style guide.

<div align="center">

BEM utilizado na prática

<img src="https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F6f0c9b1d-600a-486f-887b-bffaa6307c94%2FBEM.png?table=block&id=d05aa9dd-3f82-4e51-83be-5b8311ee1ac6&width=3070&userId=&cache=v2" width="60%">
</div>

**.card** - Elemento pai e que terá sua classe como prefixo nas classes filho.

**.card__image** - filhos tem como prefixo a classe pai seguido de **__** como separação.

**card__button--sucess** - o modificador.

<div align="center">
 EXPLICAÇÕES
</div>

## Block

Elemento pai e que terá sua classe como prefixo nas classes filhos, por exemplo: 

````html
<div class="block"></div>
````

## ELEMENT

Todos os elementos filhos inseridos dentro do contexto do block, por exemplo:

````html
<div class="block">
  <h1 class="block__title">Title</h1>
  <p class="block__text">Lorem Ipsum</p>
</div>
````

## MODIFIER

Modificadores são utilizados para modificar algum estilo de uma classe, no exemplo abaixo temos duas tags <p> que complartilham o mesmo estilos como tamanho da fonte, peso da fonte, etc, exceto a cor. Que  está sendo alterada pelo modificador:

````html
<div class="block">
  <h1 class="block__title">Title</h1>
  <p class="block__text">Lorem Ipsum</p>
  <p class="block__text--red">Lorem Ipsum</p>
</div>
````

## USANDO ESSE ESTRUTURA NO SASS

utilizando apenas o BEM, aninhamento e símbolos de referência conseguimos escrever um CSS bonito, organizado e legível para que você ou outros desenvolvedores possam fazer manutenção sem problema algum.

*aninhamento - possibilita aninhar classes para entender melhor a qual contexto ela pertence.*

````css
.block{
  &__elemento{
    /*mesma coisa que .bloco__elemento*/
    &--modificador{
      /*mesma coisa que .bloco__elemento--modificador*/
    }
  }
}
````

