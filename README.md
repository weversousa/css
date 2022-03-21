# CSS



## INTEGRAÇÃO EM UM DOCUMENTO HTML

### EXTERNO

```html
<!-- arquivo.html -->

<head>
    <link rel="stylesheet" href="caminho/arquivo.css">
</head>
```

### INTERNO

```html
<!-- arquivo.html -->

<head>
    <style>
        elemento {
            propriedade: valor;
        }
    </style>
</head>
```

### INLINE

```html
<!-- arquivo.html -->

<div style="propriedade: valor;"></div>
```


## SELETORES

### ID

```css
/* arquivo.css */

#container {}

div#container {}
```

```html
<!-- arquivo.html -->

<div id="container"></div>
```

### CLASSE

```css
/* arquivo.css */

.container {}

div.container {}
```

```html
<!-- arquivo.html -->

<div class="container"></div>
```

### ATRIBUTO

```css
/* arquivo.css */

[href] {}

a[href] {}
```

```html
<!-- arquivo.html -->

<a href="https://www.google.com.br/">OK -Tem um atributo href</a>
```

### ATRIBUTO & VALOR

O sinal `*` procura o valor em qualquer parte da String.

```css
/* arquivo.css */

[href*=google] {}
```

```html
<!-- arquivo.html -->

<a href="https://www.google.com.br/">OK -Tem a sequência 'google' no valor da atributo href</a>
<a href="https://www.youtube.com/"></a>
```

O sinal `~` procura uma sequência (sozinha ou separada por espaços).  
Podemos criar os nossos próprios atributos.  
Podem ou não ocnter valores.

```css
/* arquivo.css */

[personalizado~=sim] {}
```

```html
<!-- arquivo.html -->

<div personalizado="sim nao">OK -Tem a sequência 'sim' no valor da atributo href</div>
<div personalizado="sim,nao">FAIL -A sequência 'sim,nao' no valor da atributo href é uma coisa só</div>
<div personalizado="sim">OK -Tem a sequência 'sim' no valor da atributo href</div>
```

O sinal `~` procura a sequência exata (sozinha).

```css
/* arquivo.css */

[personalizado~=sim] {}
```

```html
<!-- arquivo.html -->

<div personalizado="sim nao">FAIL -A sequência 'sim' no valor da atributo href tem espaço e outra sequência</div>
<div personalizado="sim,nao">FAIL -A sequência 'sim,nao' no valor da atributo href é uma coisa só</div>
<div personalizado="sim">OK -Tem a sequência 'sim' e somente ela no valor da atributo href</div>
```

### ADJACENTE SIBLING (IRMÃO AO LADO)

Aplica-se a regra a todos os elementos iguais ao elemento após o sinal de `+`,  
caso o elemento **exatamente anterior** a ele (irmão/de mesmo nível),  
seja igual ao elemento antes do sinal de `+`.  
Os descendentes do pai serão atingidos, seguindo a lógica do CSS.

```css
/* arquivo.css */

div + div {}
```

```html
<!-- arquivo.html -->

<div>FAIL -É uma div. Mas não tem irmão anterior a ele.</div>

<div>OK -É uma div. E o seu irmão exatamente anterior também é uma div.</div>

<section>FAIL -O seu irmão exatamente anterior é uma div. Mas ele não é uma div</section>

<div>FAIL -É uma div. Mas o seu irmão exatamente anterior não é uma div</div>

<div>OK -É uma div. E o seu irmão exatamente anterior também é uma div.
    <section>OK -Mesmo não sendo uma div, recebe a herança do seu pai.</section>

    <div>OK -Mesmo o seu irmão exatamente anterior não sendo uma div, recebe a herança do seu pai.</div>
</div>
```

### GENERAL SIBLING (IRMÃO GERAL)

Aplica-se a regra a todos os elementos iguais ao elemento após o sinal de `~`,  
caso exista no **mínimo 1 elemento anterior** a ele, (irmão/de mesmo nível), que seja  
igual ao elemento antes do sinal de `~`.  
Os descendentes do pai serão atingidos, seguindo a lógica do CSS.

```css
/* arquivo.css */

div ~ div {}
```

```html
<!-- arquivo.html -->

<div>FAIL -É uma div. Mas não tem nenhum irmão anterior a ele.</div>

<div>OK -É uma div. E tem irmão anterior que é uma div.</div>

<section>FAIL -Tem irmãos div anteiores a ele. Mas não é uma div</section>

<div>OK -É uma div. E tem irmão anterior que é uma div.</div>

<div>OK -É uma div. E tem irmão anterior que é uma div.
    <section>OK -Mesmo não sendo uma div e não tendo irmão div anterior a ele, recebe a herança do seu pai.</section>

    <div>OK -Mesmo não tendo irmão div anterior a ele, recebe a herança do seu pai.</div>
</div>
```

### CHILD

Aplica-se a regra a todos os elementos iguais ao elemento após o sinal de `>`,
caso o seu **pai** seja igual ao elemento antes do sinal de `>`.  
Os descendentes do pai serão atingidos, seguindo a lógica do CSS.

```css
/* arquivo.css */

div > div {}
```

```html
<!-- arquivo.html -->

<div>
    <section>FAIL -É descendente direto de uma div. Mas não é uma div.
        <div>FAIL -Não é descendente direto de uma div. E o seu o pai não é uma div.</div>
    </section>
</div>

<div>
    <div>OK -É descendente direto de uma div, e é uma div.
        <section>OK -Mesmo não sendo uma div, recebe a herança do seu pai.</section>
    </div>
</div>
```

### DESCENDANT

Aplica-se a regra a todos os elementos iguais ao elemento da direita,
caso algum de seus **ancentrais** sejam iguais ao elemento da esquerda.  
Os descendentes do pai serão atingidos, seguindo a lógica do CSS.

```css
/* arquivo.css */

div div {}
```

```html
<!-- arquivo.html -->

<div>FAIL -É uma div. Mas não tem ancestral div.</div>

<section>FAIL -Não é uma div.
    <div>FAIL -É uma div. Mas não tem ancestral div.</div>
</section>

<header>FAIL -Não é uma div.
    <nav> FAIL -Não é uma div.
        <div>FAIL -É uma div. Mas não tem ancestral div.</div>
    </nav>
</header>

<section>
    <div>
        <main>FAIL -Não é uma div.
            <section>FAIL -Não é uma div.
                <div>OK -É uma div. E um de seus ancestrais é uma div.</div>
            </section>
        </main>
    </div>
</section>
```

### MÚLTIPLOS

Aplica-se a regra a todos os elementos iguais a cada elemento separado,
pela vírgula.

```css
/* arquivo.css */

li, p {}
```

### ÚNICO

Aplica-se a regra a todos os elementos iguais ao elemento especificado.

```css
/* arquivo.css */

div {}
```


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

### :HOVER

Ao passar o cursor por cima do elemento.

```css
/* arquivo.css */

div:hover {}
```

### :FOCUS

Se o foco estiver no elemento.

```css
/* arquivo.css */

div:focus {}
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

### :NTH-CHILD(parâmetro)

```css
/* arquivo.css */

ul li:nth-child(2) {
    color: green;
}
```

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

Vai pegar cada filho direto, que seja o segundo elemento do tipo do filho.

```css
/* arquivo.css */

div :nth-of-type(2n) {
    color: green;
}
```

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

```html
<!-- arquivo.html -->

```

```css
/* arquivo.css */

```