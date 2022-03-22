## ID

```css
/* arquivo.css */

div#container {}
#container {}
```

```html
<!-- arquivo.html -->

<div id="container"></div>
```

***

## CLASSE

```css
/* arquivo.css */

div.container {}
.container {}
```

```html
<!-- arquivo.html -->

<div class="container"></div>
```

***

## ATRIBUTO

```css
/* arquivo.css */

a[href] {}
[href] {}
```

```html
<!-- arquivo.html -->

<a href="#"></a>
```

### ATRIBUTO & VALOR

Valor exato.

```css
/* arquivo.css */

[href='https://www.google.com/'] {}
```

```html
<!-- arquivo.html -->

<a href="https://www.google.com/"></a>
```

`~` Procurar um determinado valor sozinho ou separado por espaço.

```css
/* arquivo.css */

button[acao~='fechar'] {}
```

```html
<!-- arquivo.html -->

<button type="submit" acao="fechar">OK</button>
<button type="submit" acao="fechar cancelar">OK</button>
<button type="submit" acao="fechar;cancelar">FAIL</button>
<button type="submit" acao="fechar; cancelar">FAIL</button>
```

`*` Procurar uma sequência em qualquer posição na string.

```css
/* arquivo.css */

button[acao*='fechar'] {}
```

```html
<!-- arquivo.html -->

<button type="submit" acao="fechar">OK</button>
<button type="submit" acao="fechar cancelar">OK</button>
<button type="submit" acao="fechar;cancelar">OK</button>
<button type="submit" acao="fechar; cancelar">OK</button>
```

***

## IRMÃO ADJACENTE

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

***

## IRMÃO GERAL

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

***

## FILHO

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

***

## DESCENDENTE

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

***

## ESPECÍFICO

Aplica-se a regra a todos os elementos iguais ao elemento especificado.

```css
/* arquivo.css */

div {}
```

***

## MÚLTIPLOS ESPECÍFICO

Aplica-se a regra a todos os elementos iguais a cada elemento separado,
pela vírgula.

```css
/* arquivo.css */

li, p {}
```