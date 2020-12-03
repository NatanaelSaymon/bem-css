## ORGANIZANDO CSS COM SASS E BEM

<br><br>

## BEM - O que é?

**Block Element Modifier**, que são as espeficações que seguiremos nesse style guide.
<br><br>

**Bloco**: Entidade autonoma que eh significativa por si so. Consegue existir sozinha.

Ex: header, footer, checkbox.

**Elemento**: Faz parte de um Bloco (elemento-filho).

Ex: item de menu, item de lista, label do checkbox.

**Modificador**: Eh uma variante de um Bloco ou Elemento.

Ex: disabled, checked, full-width, dark.
<br><br>

BLOCO
````css
.menu {}
````

ELEMENTO
````css
.menu__item {}
````

MODIFICADOR
````css
.menu--dark {}
````

<br><br>

**Abordagem BEM**

Garante que todos que participam do projeto trabalhe com uma unica base de codigo e falem o mesmo idioma.

<br>

  - **Facil**: Eh uma convesao de nomes.
  - **Modular**: Codigo independente e reusavel.
  - **Flexivel**: Use da maneira que preferir.

<br>

**Por que BEM?** 

  - Eh muito simples de aprender e rapido de implementar.
  - Prove uma ba arquitetura para usa
  - Com uma terminologia amplamente usada e reconhecida.
<br><br><br>

<div align="center">

BEM utilizado na prática

<img src="https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F6f0c9b1d-600a-486f-887b-bffaa6307c94%2FBEM.png?table=block&id=d05aa9dd-3f82-4e51-83be-5b8311ee1ac6&width=3070&userId=&cache=v2" width="60%">
</div>

**.card** - Elemento pai e que terá sua classe como prefixo nas classes filho.

**.card__image** - filhos tem como prefixo a classe pai seguido de **__** como separação.

**card__button--sucess** - o modificador.

<br><br><br>

<div align="center">
 EXPLICAÇÕES DAS CLASSES
</div>

## Block

Elemento pai e que terá sua classe como prefixo nas classes filhos, por exemplo: 

````html
<div class="block"></div>
````
<br><br>
## ELEMENT

Todos os elementos filhos inseridos dentro do contexto do block, por exemplo:

````html
<div class="block">
  <h1 class="block__title">Title</h1>
  <p class="block__text">Lorem Ipsum</p>
</div>
````
<br><br>
## MODIFIER

Modificadores são utilizados para modificar algum estilo de uma classe, no exemplo abaixo temos duas tags <p> que complartilham o mesmo estilos como tamanho da fonte, peso da fonte, etc, exceto a cor. Que  está sendo alterada pelo modificador:

````html
<div class="block">
  <h1 class="block__title">Title</h1>
  <p class="block__text">Lorem Ipsum</p>
  <p class="block__text--red">Lorem Ipsum</p>
</div>
````
<br><br>
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

