# Input


## Float Label

```css
/* arquivo.css */

main {

    /* Para o label ser absoluto dentro dele */
    position: relative;
}

input[type='text'] {

    /* Limpando os estilos que vem por padrão */
    appearance: none;
    outline: none;
    border: none;
    background: none;

    width: 300px;
    padding: 10px 0 10px 10px;
    border: 2px solid palevioletred;

    font-size: 1.2em;
    font-weight: bold;

    /* Quando o mouse estiver sobre o elemento se transforma em uma mão */
    cursor: pointer;
}

label.labelFloat {

    /* Será absoluto dentro do main que está como relativo */
    position: absolute;

    top: 13px;
    left: 10px;

    transition: all 0.6s;
}


/* Quando o input for focado e se logo abaixo a ele for um label */
/* Se o placeholder NÃO estiver sendo exibido (significaa que ta preenchido) e se logo abaixo a ele for um label */
input.inputFloat:focus + label.labelFloat,
input.inputFloat:not(:placeholder-shown) + label.labelFloat {

    transition: all 0.6s;

    /* Move o label conforme especificado */
    top: -8px;

    /* Caso a cor de fundo do input e div que envolve o input sejam a mesma */
    /* Colocando a mesma cor de fundo deles vai causar um efeito como se a borda estivesse aberta na área do label   */
    background-color: aliceblue;
}
```

![input-float](https://user-images.githubusercontent.com/69995549/159974322-01bed151-c80f-4c9e-bcaf-54bd0d7d7401.gif)

***

```css
/* arquivo.css */


.labelCheckCourse {
    display: flex;
    align-items: center;
    margin-bottom: 40px;
}

.inputCheckCourse {
    appearance: none;
    height: 100px;
    width: 100px;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 5px solid palevioletred;
    margin-right: 20px;
}

.inputCheckCourse:hover,
.inputCheckCourse:checked:hover {
    transition: all 0.6s;
    background-color: rgb(216, 112, 147, 40%);
}

.inputCheckCourse:checked {
    transition: all 0.6s;
    background-color: rgb(216, 112, 147, 75%);
}

.inputCheckCourse:checked::after {
    content: url('../static/images/check-solid.svg');
    transition: all 0.6s;
    width: 70%;
}

.spanCheckCourse {
    font-size: 50px;
    font-weight: bold;
    color: palevioletred;
}
```

```html
<!-- arquivo.html -->


<label class="labelCheckCourse">
    <input type="checkbox" class="inputCheckCourse">
    <span class="spanCheckCourse">Python</span>
</label>

<label class="labelCheckCourse">
    <input type="checkbox" class="inputCheckCourse">
    <span class="spanCheckCourse">CSS</span>
</label>
```

```svg
<!-- arquivo.svg -->


<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
    <path fill="#fff" d="M438.6 105.4C451.1 117.9 451.1 138.1 438.6 150.6L182.6 406.6C170.1 419.1 149.9 419.1 137.4 406.6L9.372 278.6C-3.124 266.1-3.124 245.9 9.372 233.4C21.87 220.9 42.13 220.9 54.63 233.4L159.1 338.7L393.4 105.4C405.9 92.88 426.1 92.88 438.6 105.4H438.6z"/>
</svg>
```

![inputCheck](https://user-images.githubusercontent.com/69995549/159992406-e6650f18-a2d4-40fe-8071-c6a0380a7c4a.gif)

***



```svg

```css
/* arquivo.css */


```

```html
<!-- arquivo.html -->


```

```svg

```
