# CSS


## PSEUDO CLASSES

### :LINK

Ainda não foi clicado.

```css
/* arquivo.css */

a:link {}
```

### :VISITED

Link que já foi clicado.

```css
/* arquivo.css */

a:visited {}
```

### :FIRST-CHILD & :LAST-CHILD

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

Uso Real (Remover a última borda).

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

### :NTH-CHILD(parâmetro)

```css
/* arquivo.css */

ul li:nth-child(2) {
    color: green;
}
```

![nth-child](https://user-images.githubusercontent.com/69995549/159374381-3841bebb-0bc7-409e-86e0-d267a807d4d2.png)

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

Para pegar os pares temos as duas opções.

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

Para pegar os ímpares temos as duas opções.

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

### :NTH-LAST-CHILD(parâmetro)

As mesmas regras do `nth-child()`, porém conta debaixo para cima.

```css
/* arquivo.css */

ul li:nth-last-child(2n) {}
```

### :NTH-CHIL() vs :NTH-OF-TYPE

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

Vai pegar cada filho direto, que seja o segundo elemento do tipo do filho.

```css
/* arquivo.css */

div :nth-of-type(2n) {
    color: green;
}
```

![nth-child-vs-nth-of-type-2](https://user-images.githubusercontent.com/69995549/159374387-2749413c-e077-4f25-99e9-affcc38ea228.png)

### :DISABLED & :ENABLED

```html
<!-- arquivo.html -->

<input type="text" disabled>
<input type="text">
```

```css
/* arquivo.css */

input:disabled {}
input:enabled {}
```

### :INVALID & :VALID

```html
<!-- arquivo.html -->

<input type="email">
```

```css
/* arquivo.css */

input:invalid {}
input:valid {}
```

### :REQUIRED & :OPTIONAL

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

### :READONLY

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

### IN_RANGE & OUT-OF-RANGE

```html
<!-- arquivo.html -->

<input type="number" min="10" max="20">
```

```css
/* arquivo.css */

input:in-range {}
input:out-of-range {}
```

### CHECKED

```html
<!-- arquivo.html -->

<input type="checkbox" name="" id="" checked>
```

```css
/* arquivo.css */

input:checked {}
```


## PSEUDO-ELEMENTO

### ::BEFORE & ::AFTER

```html
<!-- arquivo.html -->

<h1>Título</h1>
```

```css
/* arquivo.css */

h1::before {
    content: 'before';
    color: red;
}

h1::after {
    content: 'after';
    color: green;
}
```

![before-after](https://user-images.githubusercontent.com/69995549/159374370-fc528058-6770-4817-a3bc-c3dac154382c.png)

```css
/* arquivo.css */

h1::before {
    content: '';
    display: block;
    width: 200px;
    height: 2px;
    background-color: red;
}

h1::after {
    content: '';
    display: block;
    width: 200px;
    height: 2px;
    background-color: green;
}
```

![before-after-row](https://user-images.githubusercontent.com/69995549/159374375-c739a3db-fdd2-47ec-b71b-02af0b438964.png)

```css
/* arquivo.css */

h1::before {
    content: '';
    display: block;
    background-color: red;
    width: 50px;
    height: 50px;
    border-radius: 50%;
}

h1::after {
    content: '';
    display: block;
    background-color: green;
    width: 50px;
    height: 50px;
    border-radius: 50%;
}
```

![before-after-circle](https://user-images.githubusercontent.com/69995549/159374373-f79890b3-1572-4849-ac06-40c1fd3d550c.png)

```html
<!-- arquivo.html -->

```

```css
/* arquivo.css */

```
