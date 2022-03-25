# Input


## Float Label

```css
/* arquivo.css */


.labelFloat {

    /* Para o label ser absoluto dentro dele */
    position: relative;
}

.inputFloat {

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

.spanFloat {

    /* Será absoluto dentro do main que está como relativo */
    position: absolute;

    top: 13px;
    left: 10px;

    transition: all 0.6s;
}


/* Quando o input for focado e se logo abaixo a ele for um span */
/* Se o placeholder NÃO estiver sendo exibido (significaa que ta preenchido) e se logo abaixo a ele for um span */
.inputFloat:focus + .spanFloat,
.inputFloat:not(:placeholder-shown) + .spanFloat {

    transition: all 0.6s;

    /* Move o span conforme especificado */
    top: -8px;

    /* Caso a cor de fundo do input e div que envolve o input sejam a mesma */
    /* Colocando a mesma cor de fundo deles vai causar um efeito como se a borda estivesse aberta na área do span   */
    background-color: aliceblue;

    padding: 0 7px 0 7px;
}
```

```html
<!-- arquivo.html -->


<label class="labelFloat">
    <input type="text" placeholder=" " class="inputFloat">
    <span class="spanFloat">Seu nome</span>
</label>
```

![float-inputgif](https://user-images.githubusercontent.com/69995549/160025277-339c06db-262c-4a97-b041-89a7755ee585.gif)

***

## Checkbox

```css
/* arquivo.css */


.labelCheckCourse {
    display: flex;
    align-items: center;
    margin-bottom: 40px;
}

.labelCheckCourse:hover {
    cursor: pointer;
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
    color: palevioletred;
}
```

```html
<!-- arquivo.html -->


<label class="labelCheckCourse">
    <input type="checkbox" class="inputCheckCourse">
    <span class="spanCheckCourse">Checkbox</span>
</label>
```

```svg
<!-- arquivo.svg -->


<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
    <path fill="#fff" d="M438.6 105.4C451.1 117.9 451.1 138.1 438.6 150.6L182.6 406.6C170.1 419.1 149.9 419.1 137.4 406.6L9.372 278.6C-3.124 266.1-3.124 245.9 9.372 233.4C21.87 220.9 42.13 220.9 54.63 233.4L159.1 338.7L393.4 105.4C405.9 92.88 426.1 92.88 438.6 105.4H438.6z"/>
</svg>
```

![checkbox](https://user-images.githubusercontent.com/69995549/160023753-44f48a21-3017-480e-901e-55213d8cb523.gif)

***

## Radio

```css
/* arquivo.css */


.labelRadio {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-right: 60px;
}

.labelRadio:hover {
    cursor: pointer;
}

.inputRadio {
    appearance: none;
    height: 100px;
    width: 100px;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 5px solid palevioletred;
    border-radius: 50%;
}

.inputRadio:hover::after {
    content: '';
    display: inline-block;
    text-align: center;
    vertical-align: middle;
    height: 85%;
    width: 85%;
    border-radius: 50%;
    background-color: rgb(216, 112, 147, 40%);
    cursor: pointer;
}

.inputRadio:checked::after {
    content: '';
    display: inline-block;
    text-align: center;
    vertical-align: middle;
    height: 85%;
    width: 85%;
    border-radius: 50%;
    background-color: rgb(216, 112, 147, 75%);
}

.spanRadio {
    font-size: 50px;
    color: palevioletred;
}
```

```html
<!-- arquivo.html -->


<label class="labelRadio">
    <input type="radio" name="radio" class="inputRadio">
    <span class="spanRadio">Radio 1</span>
</label>
<label class="labelRadio">
    <input type="radio" name="radio" class="inputRadio">
    <span class="spanRadio">Radio 2</span>
</label>
```

![radio](https://user-images.githubusercontent.com/69995549/160023981-73c9fed0-6849-4d1b-96cf-f4043d9ab8df.gif)
