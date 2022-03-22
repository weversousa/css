Adicionando conteúdo ao começo e ao fim de um elemento especificado.

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
