```
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    /*
        background-image: url(link);
        background-repeat: no-repeat;
        background-position: top center;
        background-size: cover/contain
    
        Short-hand - 
            background: color image repeat position/size
    */
    background: url(./assets/bg-mobile.jpg) no-repeat top center/cover;
}
body * {
    font-family: 'Young Serif', serif;
    color: white;
}

#container {
    width: 360px;
    /* 
        height: 712px;
        O css respeita a altura da caixa de acordo com os conteudos em seu interior
    */
    border: 1px solid red;
    margin: auto; 
    padding: 100px;
    /* 
        margin-right: auto;
        margin-left: auto;
    */
}

#profile {
    text-align: center;
}

#profile img {
    width: 112px;
}

#profile p {
    font-weight: 500;
    font-size: 16px; /*  navegador deixa por padrão neste tamanho */
    line-height: 24px;
}
```