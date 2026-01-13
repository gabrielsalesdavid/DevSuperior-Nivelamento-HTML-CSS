# Fundamentos de CSS

## 📌 O que é CSS?

CSS (Cascading Style Sheets) é a linguagem utilizada para estilizar e fazer layout de documentos HTML. Define cores, fontes, espaçamento, dimensões e posicionamento dos elementos.

---

## 🎨 Formas de Aplicar CSS

### 1. **CSS Externo (Recomendado)**

```html
<head>
    <link rel="stylesheet" href="style.css">
</head>
```

**Arquivo style.css:**
```css
body {
    font-family: Arial, sans-serif;
    color: #333;
}
```

### 2. **CSS Interno**

```html
<head>
    <style>
        body {
            font-family: Arial, sans-serif;
            color: #333;
        }
    </style>
</head>
```

### 3. **CSS Inline (Evitar)**

```html
<p style="color: red; font-size: 16px;">Texto vermelho</p>
```

---

## 🏗️ Estrutura de uma Regra CSS

```css
seletor {
    propriedade: valor;
    propriedade: valor;
}
```

**Exemplo:**
```css
h1 {
    color: #000;
    font-size: 24px;
    margin-bottom: 20px;
}
```

---

## 🎯 Seletores CSS

### 1. **Seletor de Elemento**
```css
p {
    color: blue;
}
```

### 2. **Seletor de Classe**
```css
.destaque {
    color: red;
    font-weight: bold;
}
```

**HTML:**
```html
<p class="destaque">Texto destacado</p>
```

### 3. **Seletor de ID**
```css
#header {
    background-color: #333;
    color: white;
}
```

**HTML:**
```html
<header id="header">Cabeçalho</header>
```

### 4. **Seletor Universal**
```css
* {
    margin: 0;
    padding: 0;
}
```

### 5. **Seletor Descendente**
```css
div p {
    color: blue;
}
```

### 6. **Seletor Filho Direto**
```css
ul > li {
    list-style: none;
}
```

### 7. **Seletor de Atributo**
```css
input[type="email"] {
    border: 1px solid #ccc;
}
```

---

## 🎨 Propriedades de Cor e Fundo

### Cores
```css
color: #FF0000;           /* Hexadecimal */
color: rgb(255, 0, 0);    /* RGB */
color: rgba(255, 0, 0, 0.5); /* RGBA com transparência */
color: red;               /* Nome da cor */
```

### Fundo
```css
background-color: #f0f0f0;
background-image: url('imagem.jpg');
background-size: cover;
background-position: center;
background-repeat: no-repeat;

/* Shorthand */
background: #f0f0f0 url('img.jpg') center/cover no-repeat;
```

---

## 📏 Modelo de Caixa (Box Model)

```css
.caixa {
    width: 300px;
    height: 200px;
    
    /* Margem (fora da borda) */
    margin: 20px;           /* Todos os lados */
    margin-top: 10px;
    margin-right: 15px;
    margin-bottom: 10px;
    margin-left: 15px;
    
    /* Preenchimento (dentro da borda) */
    padding: 20px;
    padding-top: 10px;
    
    /* Borda */
    border: 2px solid #333;
    border-radius: 5px;
    
    /* Controla se width/height inclui padding/border */
    box-sizing: border-box;
}
```

**Ordem das propriedades shorthand (superior, direita, inferior, esquerda):**
```css
margin: 10px 20px 10px 20px;   /* cima, direita, baixo, esquerda */
margin: 10px 20px;              /* cima/baixo, direita/esquerda */
margin: 10px;                   /* todos os lados */
```

---

## 🔤 Tipografia

```css
body {
    font-family: 'Arial', sans-serif;
    font-size: 16px;
    font-weight: bold;          /* 100-900 ou bold, normal */
    font-style: italic;         /* italic ou normal */
    line-height: 1.5;           /* Altura da linha */
    letter-spacing: 1px;        /* Espaço entre letras */
    text-align: center;         /* left, right, center, justify */
    text-decoration: underline; /* underline, overline, line-through */
    text-transform: uppercase;  /* uppercase, lowercase, capitalize */
}
```

### Google Fonts
```html
<head>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700&display=swap" rel="stylesheet">
</head>
```

```css
body {
    font-family: 'Roboto', sans-serif;
}
```

---

## 📐 Dimensionamento

```css
.elemento {
    /* Tamanho fixo */
    width: 300px;
    height: 200px;
    
    /* Tamanho relativo */
    width: 50%;
    height: 100vh;          /* 100% da viewport height */
    width: 100vw;           /* 100% da viewport width */
    
    /* Min e Max */
    min-width: 200px;
    max-width: 800px;
    min-height: 100px;
    max-height: 500px;
    
    /* Overflow */
    overflow: hidden;       /* hidden, visible, scroll, auto */
    overflow-x: auto;
    overflow-y: hidden;
}
```

---

## 🎯 Posicionamento

```css
/* Static (padrão) */
.elemento {
    position: static;
}

/* Relative (relativo ao fluxo normal) */
.elemento {
    position: relative;
    top: 10px;
    left: 20px;
}

/* Absolute (relativo ao pai posicionado) */
.container {
    position: relative;
}

.elemento {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
}

/* Fixed (relativo à viewport) */
.elemento {
    position: fixed;
    top: 0;
    right: 0;
}

/* Sticky (alternância entre relative e fixed) */
.elemento {
    position: sticky;
    top: 0;
}
```

---

## 🎨 Display

```css
/* Display block */
.bloco {
    display: block;         /* Ocupa toda a largura */
}

/* Display inline */
.inline {
    display: inline;        /* Ocupa apenas espaço necessário */
}

/* Display inline-block */
.inline-bloco {
    display: inline-block;  /* Combinação de inline e block */
}

/* Display none */
.oculto {
    display: none;          /* Remove do fluxo */
}

/* Display flex */
.container {
    display: flex;
}

/* Display grid */
.grid {
    display: grid;
}
```

---

## 💡 Variáveis CSS (Custom Properties)

```css
:root {
    --cor-primaria: #3498db;
    --cor-secundaria: #e74c3c;
    --font-principal: 'Arial', sans-serif;
    --espaco-padrao: 16px;
}

.botao {
    background-color: var(--cor-primaria);
    padding: var(--espaco-padrao);
    font-family: var(--font-principal);
}
```

---

## 🌈 Pseudo-classes e Pseudo-elementos

### Pseudo-classes
```css
a:hover {
    color: red;             /* Mouse sobre o elemento */
}

button:active {
    transform: scale(0.95); /* Elemento pressionado */
}

input:focus {
    border-color: blue;     /* Elemento em foco */
}

li:first-child {
    font-weight: bold;      /* Primeiro filho */
}

li:last-child {
    margin-bottom: 0;       /* Último filho */
}

li:nth-child(2) {
    background: #f0f0f0;    /* Segundo filho */
}

input:disabled {
    opacity: 0.5;           /* Elemento desabilitado */
}
```

### Pseudo-elementos
```css
p::before {
    content: "→ ";          /* Antes do elemento */
}

p::after {
    content: " ←";          /* Depois do elemento */
}

p::first-letter {
    font-size: 24px;        /* Primeira letra */
}

p::first-line {
    font-weight: bold;      /* Primeira linha */
}
```

---

## ✅ Boas Práticas

1. **Use classes ao invés de IDs** para melhor reutilização
2. **Organize o CSS** em seções lógicas
3. **Use nomes descritivos** para classes
4. **Minimize CSS inline** - use folhas externas
5. **Declare variáveis** para cores e tamanhos recorrentes
6. **Resetar estilos padrão** do navegador
7. **Mantenha especificidade baixa** para evitar conflitos

---

## 📚 Referências

- [MDN Web Docs - CSS](https://developer.mozilla.org/pt-BR/docs/Web/CSS)
- [W3C CSS Specification](https://www.w3.org/Style/CSS/)
- [CSS Tricks](https://css-tricks.com/)
- [Can I Use](https://caniuse.com/) - Compatibilidade de navegadores

