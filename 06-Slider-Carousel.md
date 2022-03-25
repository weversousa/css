## Slider Carousel - (só HTML3 & CSS5) 

```css
<!-- arquivo.css -->


main {
    position: relative;
    height: 150px;
    width: 220px;
    display: flex;
    border: 5px solid palevioletred;
    overflow: hidden;
}

main input {
    display: none;
}

img {
    height: 100%;
    width: 100%;
    object-fit: cover;
}

.divLabel {
    position: absolute;
    width: 100%;
    display: flex;
    justify-content: space-evenly;
    align-self: flex-end;
    margin-bottom: 8px;
}

label {
    height: 20px;
    width: 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 1px solid palevioletred;
    border-radius: 50%;
    transition: all 1.0s;
    cursor: pointer;
}

label:hover:after {
    content: '';
    height: 12px;
    width: 12px;
    background-color: palevioletred;
    border-radius: 50%;
    transition: all 1.0s;
}


#inputRadio1:checked ~ #img1 {
    left: 0;
    transition: all 1.0s;
}

#inputRadio2:checked ~ #img1 {
    margin-left: -100%;
    transition: all 1.0s;
}

#inputRadio3:checked ~ #img1 {
    margin-left: -200%;
    transition: all 1.0s;
}

#inputRadio1:checked ~ div label[for='inputRadio1']:after,
#inputRadio2:checked ~ div label[for='inputRadio2']:after,
#inputRadio3:checked ~ div label[for='inputRadio3']:after {
    content: '';
    height: 12px;
    width: 12px;
    background-color: palevioletred;
    border-radius: 50%;
    transition: all 1.0s;
}
```

```html
<!-- arquivo.html -->


<main>
    <input type="radio" name="inputRadio" id="inputRadio1" checked>
    <input type="radio" name="inputRadio" id="inputRadio2">
    <input type="radio" name="inputRadio" id="inputRadio3">

    <img src="../static/images/1.jpg" id="img1">
    <img src="../static/images/2.jpg" id="img2">
    <img src="../static/images/3.jpg" id="img3">

    <div class="divLabel">
        <label for="inputRadio1"></label>
        <label for="inputRadio2"></label>
        <label for="inputRadio3"></label>
    </div>
</main>
```

![com-overflow](https://user-images.githubusercontent.com/69995549/160041871-789c80d5-456f-4eab-b23a-9f55aebff2a5.gif)

Abaixo o mesmo slider, porém sem o atributo overflow para esconder as imagem, assim temos uma noção de como funciona o deslocamento das imagens.
