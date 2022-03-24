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

```html
<!-- arquivo.html -->


```

```svg

```





/* arquivo.css */


```

```html
<!-- arquivo.html -->


```

```svg

```
