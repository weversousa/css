# Pseudo-classes

Uma *pseudo-classe* CSS é uma palavra-chave adicionada a seletores que especifica um estado especial do elemento selecionado.  
Sintaxe `elemento:pseudo-classe {}` ou `:pseudo-classe {}`
Algumas delas possuem parâmetros então ficaria asism `elemento:pseudo-classe(parâmetro) {}`.


## :hover

Ao passar o cursor sobre o elemento.

```html
/* arquivo.html */

<button>Enviar</button>
```

```css
/* arquivo.css */

button:hover {
    background-color: green;
}
```

![hover](https://user-images.githubusercontent.com/69995549/159518544-2a15aec8-f06b-4b23-a53d-c31e27858338.gif)

***

## :active

Ao clicar no elemento.

```html
/* arquivo.html */

<button>Enviar</button>
```

```css
/* arquivo.css */

button:active {
    background-color: yellow;
}
```

![active](https://user-images.githubusercontent.com/69995549/159518647-97ae1ca9-e3ae-4afe-8250-236da9409cb2.gif)

***

## :empty

Elementos que não tenham conteúdo dentro dele.

```html
/* arquivo.html */

<button>Enviar</button>
<button>Cancelar</button>
<button>Limpar</button>
```

```css
/* arquivo.css */

button:empty {
    background-color: plum;
}
```

![empty](https://user-images.githubusercontent.com/69995549/159520277-dff3773d-bfe3-4475-a56e-21b0fba5d098.png)

***

## :focus

Ao focar no elemento.

```html
/* arquivo.html */

<button>Enviar</button>
```

```css
/* arquivo.css */

button:focus {
    background-color: brown;
}
```

![focus](https://user-images.githubusercontent.com/69995549/159518723-5dfb9563-72f7-4a39-843f-2d82802c530d.gif)

***

## :not(parameter)

Elementos que não tenham determinada condição passada por parâmetro.  
O Not é um método, então ele necessita de parâmetros entre parênteses.

```html
/* arquivo.html */

<button class="btn">Salvar</button>
<button class="btn">Cancelar</button>
<button class="btn limp">Limpar</button>
```

```css
/* arquivo.css */

button:not(.limp) {
    background-color: lightskyblue;
}
```

![not](https://user-images.githubusercontent.com/69995549/159519021-27afcc7d-e22f-4602-b794-4816169c8b9c.png)

***

## :disabled & :enabled

Campos de formulário ou elementos que tem a propriedade `disabled`.  
Por padrão é `enabled`


```html
/* arquivo.html */

<button disabled>Enviar</button>
<button>Cancelar</button>
<input type="text" disabled>
<input type="text">
```

```css
/* arquivo.css */

:disabled {
    background-color: darkgray;
}

/* Pega o que estiver diferente de disabled */
:enabled {}
```

![disabled](https://user-images.githubusercontent.com/69995549/159519102-2b809b34-fb7c-45b9-abed-8caaa3a556a1.png)

***

## :invalid & :valid

Baseado em cima dos valores das propriedades definidas no elemento. Exemplo, um input com o tipo e-mail,  
caso o valor digitado não atenda o padrão de um e-mail esse elemento será capturado pelo `:invalid`.

```html
<!-- arquivo.html -->

<input type="email">
```

```css
/* arquivo.css */

input:invalid {}
input:valid {}
```

***

## :required

Exemplo, um input com a propriedade `required`, antes de enviar o formulário
ele deve receber obrigatoriamente um valor caso não aconteça será capturado pelo `:invalid`.  
Por padrão é `optional`

```html
<!-- arquivo.html -->

<input type="text" required>
<input type="text">
```

```css
/* arquivo.css */

input:required {}
input:optional {}
```

***

## :readonly

signifa comente leitura, exemplo, um input com essa propriedade não pode ser alterado.  
Por padrão `Readwrite`.

```html
<!-- arquivo.html -->

<input type="text" readonly>
<input type="text">
```

```css
/* arquivo.css */

input:read-only {}
input:read-write {}
```

***

## :in-range & :out-of-range

Usado em inputs do tipo numérico e baseado nas propriedades *min* e *max*.

```html
<!-- arquivo.html -->

<input type="number" min="10" max="20">
```

```css
/* arquivo.css */

input:in-range {}
input:out-of-range {}
```

***

## :checked)

Seleciona os elementos checkbox que estão checados.

```html
/* arquivo.html */

<input type="checkbox">
<input type="checkbox">
<input type="checkbox">
```

```css
/* arquivo.css */

input:checked {
    width: 30px;
    height: 30px;
}
```

![checked](https://user-images.githubusercontent.com/69995549/159519169-1465ed77-8b0f-4cc3-aa12-aab4d223bd11.gif)

***

## ::fter & :checked

Combinando pseudo classes com pseudo elementos.

```html
/* arquivo.html */

<input type="checkbox">
<input type="checkbox">
<input type="checkbox">
```

```css
/* arquivo.css */

input::after {
    position: relative;
    content: 'Inativo';
    margin-left: 20px;
}

input:checked::after {
    content: 'Ativo';
    color: green;
}
```

![checked after](https://user-images.githubusercontent.com/69995549/159519300-b4ac1975-b394-4ab2-9cf0-601518f64b00.gif)

***

## :first-child & last-child)

Selecionando o primeiro e o último elemento.  

```html
<!-- arquivo.html -->

<ul>
    <li>São Paulo</li>
    <li>Salvador</li>
    <li>Rio de Janeiro</li>
    <li>Belo Horizonte</li>
</ul>
```

```css
/* arquivo.css */

ul li:first-child {
    color: red;
}

ul li:last-child {
    color: green;
}
```

![first-child- -last-child](https://user-images.githubusercontent.com/69995549/159374377-6a646358-fcc5-4585-b899-732287e88b9a.png)

### Observação

Caso o primeiro filho de ul não fosse um li, não iria funcionar.  
Por exemplo, se tive um h1 antes dos li.  
A condição não é simplesmente o primeiro filho, mas sim "pegue o *li* caso ele seja o primeiro filho.  
Atenção nisso pois é que confunde geral.  

Serve a mesma regra para o `last-child`.  
  
  
Para isso temos a pseudo-classes `nth-of-type` que pega o primeiro filho do tipo especificado,  
mesmo que ele não seja o primeiro filho.  
E se a gente não especificar o tipo do filho, ele vai pegar o 1º filho d ecada tipo.
  
  
Mas também devemos ter atenção. Vamos supor que a gente quer selecionar o 1º elemento  
com uma classe qualquer.  

```css

div .destaque:nth-of-type(1) {
    color: red;
}
```

```html

<div>
    <h1>H 1</h1>
    <p>P 1</p>
    <p class="destaque">P 2</p>
    <p>P 3</p>
</div>
```

Não funciona devido a propriedade `nth-of-type` trabalhar diretamente pela tag.  
O código em CSS está falando (rsrsrs): pegue o 1º filho da *div* do tipo *p* SE ele tiver a classe destaque.  
Acontece que o 1º filho *p* da *div* não tem a classe destaque.

***

Uso real para `last-child`. Vamos remover a última borda.

```css
/* arquivo.css */

ul {
    list-style: none;
    margin: 0;
    padding: 0;
}

ul li {
    border-bottom: 1px solid #eee;
    margin-bottom: 5px;
    padding-bottom: 5px;
}

ul li:last-child {
    border: none;
}
```

![last-child-real](https://user-images.githubusercontent.com/69995549/159374378-f990ec03-073f-4cbf-b238-31373d0c3b60.png)

***

## nth-child

nth signica enésimo.  
Selecionando o segundo elemento.

```css
/* arquivo.css */

ul li:nth-child(2) {
    color: green;
}
```

![nth-child](https://user-images.githubusercontent.com/69995549/159374381-3841bebb-0bc7-409e-86e0-d267a807d4d2.png)

***

Breve conceito para os parâmetros

* n
  * todas a linhas
* 2n
  * 2 x 1 = 2 - segunda linha
  * 2 x 2 = 4 - quarta linha
  * 2 x 3 = 6 - sexta linha
* 2n-1
  * 2 x 1 - 1 = 1 - primeira linha
  * 2 x 2 - 1 = 3 - terceira linha
  * 2 x 3 - 1 = 5 - quinta linha

  
O valor *n* vai de 0 até 1.  
E o 2 poderia ser qualquer número, e ele seria multiplicado por n.

***

Selecionando os elementos pares.
Para isso existem duas opções.

```css
/* arquivo.css */

ul li:nth-child(2n) {
    color: red;
}

ul li:nth-child(even) {
    color: red;
}
```

![nth-child-2n- -even](https://user-images.githubusercontent.com/69995549/159374382-3d0faa7a-fb9f-400f-ba1c-c99c47f8bdf3.png)

***

Selecionando os elementos ímpares.  
Para isso existem duas opções.

```css
/* arquivo.css */

ul li:nth-child(2n-1) {
    color: green;
}

ul li:nth-child(odd) {
    color: green;
}
```

![nth-child-2n-1- -odd](https://user-images.githubusercontent.com/69995549/159374385-1d896375-f2e9-4e9b-b519-ac4301d1c10e.png)

***

As mesmas regras do `nth-child()`, porém conta debaixo para cima.

```css
/* arquivo.css */

ul li:nth-last-child(2n) {}
```

***

`:NTH-CHILD()` vs `:NTH-OF-TYPE`

```html
<!-- arquivo.html -->

<div>
    <div>São Padivo</div>
    <a href="#">SP</a>
    <div>Salvador</div>
    <a href="#">BA</a>
    <div>RJ</div>
    <a href="#">SP</a>
    <div>Belo Horizonte</div>
    <a href="#">MG</a>
</div>
```

Não distingue elementos. Logo, é exatamente o segundo filho do elemento.

```css
/* arquivo.css */

div :nth-child(2n) {
    color: green;
}
```

![nth-child-vs-nth-of-type-1](https://user-images.githubusercontent.com/69995549/159374386-ec326422-3c08-47c0-8ffc-9f957d43a700.png)

Já o `:NTH-OF-TYPE` vai pegar cada filho direto, que seja o segundo elemento do tipo do filho.

```css
/* arquivo.css */

div :nth-of-type(2n) {
    color: green;
}
```

![nth-child-vs-nth-of-type-2](https://user-images.githubusercontent.com/69995549/159374387-2749413c-e077-4f25-99e9-affcc38ea228.png)
