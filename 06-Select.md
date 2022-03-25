## Select

```css
/* arquivo.css */


.divSelectNovo {
    position: relative;
}

.selectNovo {
    appearance: none;
    outline: none;
    box-shadow: none;
    border: none;
    background: none;
    background-image: none;

    transition: all 0.6s;

    width: 300px;
    height: 45px;
    padding: 17px 0 10px 10px;
    border: 2px solid palevioletred;

    background-image: url('../static/images/angle-down-solid.svg');
    background-repeat: no-repeat;
    background-position: right 10px center;

    cursor: pointer;
}

.selectNovo:hover {
    transition: all 0.6s;
    background-color: rgb(216, 112, 147, 10%);
}

.spanSelectNovo {
    position: absolute;
    left: 0;
    margin-top: 11px;
    margin-left: 10px;
    font-weight: 300;
    font-size: 1.4em;
    transition: all 0.6s;
}

.selectNovo:focus + .spanSelectNovo,
.selectNovo:valid + .spanSelectNovo {
    margin-top: -5px;
    font-size: 1em;
    background-color: aliceblue;
    padding: 0 7px 0 7px;
    transition: all 0.6s;
}
```

```html
<!-- arquivo.html -->


<div class="divSelectNovo">
        
    <select class="selectNovo" required>
        <option selected></option>
        <option>Item 1</option>
        <option>Item 2</option>
    </select>

    <span class="spanSelectNovo">Escolha...</span>
</div>
```

![select](https://user-images.githubusercontent.com/69995549/160171032-249d14d2-96b7-4b3d-87c5-528c0fdadf8f.gif)
