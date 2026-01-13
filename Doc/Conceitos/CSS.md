# Conceitos Avançados de CSS

## 📌 Introdução

Este documento cobre conceitos avançados de CSS que vão além dos fundamentos, incluindo técnicas modernas de layout, animações e otimizações.

---

## 🎯 Flexbox Avançado

### Conceitos Principais

```css
.container {
    display: flex;
    
    /* Direção dos itens */
    flex-direction: row;           /* row, row-reverse, column, column-reverse */
    
    /* Quebra de linhas */
    flex-wrap: wrap;               /* nowrap, wrap, wrap-reverse */
    
    /* Alinhamento principal (eixo principal) */
    justify-content: space-between; /* flex-start, flex-end, center, space-between, 
                                      space-around, space-evenly, stretch */
    
    /* Alinhamento secundário (eixo transversal) */
    align-items: center;           /* flex-start, flex-end, center, stretch, baseline */
    
    /* Alinhamento de múltiplas linhas */
    align-content: space-around;   /* flex-start, flex-end, center, space-between, 
                                     space-around, stretch */
    
    /* Espaçamento entre itens (gap) */
    gap: 20px;                     /* Define espaço entre itens */
    row-gap: 10px;                 /* Espaço entre linhas */
    column-gap: 15px;              /* Espaço entre colunas */
}

/* Propriedades dos itens flex */
.item {
    /* Crescimento (espaço disponível) */
    flex-grow: 1;                  /* Proporção de crescimento */
    
    /* Encolhimento (espaço insuficiente) */
    flex-shrink: 1;                /* Proporção de encolhimento */
    
    /* Tamanho base */
    flex-basis: 200px;             /* Tamanho inicial do item */
    
    /* Shorthand */
    flex: 1 1 200px;               /* grow shrink basis */
    
    /* Alinhamento individual */
    align-self: flex-end;          /* Sobrescreve align-items */
    
    /* Ordem dos itens */
    order: 2;                      /* Muda a ordem de exibição */
}
```

### Exemplos Práticos

```css
/* Layout de navegação responsiva */
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 20px;
    flex-wrap: wrap;
}

/* Grid com Flexbox */
.card-container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.card {
    flex: 1 1 calc(33.333% - 20px);
    min-width: 250px;
}

/* Distribuição igual */
.distribuir-igual {
    display: flex;
    gap: 10px;
}

.distribuir-igual > * {
    flex: 1;
}
```

---

## 📐 CSS Grid Avançado

### Grid Básico

```css
.grid-container {
    display: grid;
    
    /* Definir colunas */
    grid-template-columns: 1fr 2fr 1fr;  /* Frações */
    grid-template-columns: repeat(3, 1fr); /* Repetição */
    grid-template-columns: 200px auto 1fr; /* Tamanhos variados */
    
    /* Definir linhas */
    grid-template-rows: 100px auto 50px;
    grid-template-rows: repeat(auto-fit, minmax(200px, 1fr));
    
    /* Espaçamento */
    gap: 20px;
    row-gap: 10px;
    column-gap: 15px;
    
    /* Alinhamento de itens dentro das células */
    align-items: center;           /* Eixo vertical */
    justify-items: center;         /* Eixo horizontal */
    
    /* Alinhamento do grid inteiro */
    align-content: space-around;
    justify-content: space-between;
}

/* Propriedades dos itens */
.grid-item {
    /* Posicionamento */
    grid-column: 1 / 3;           /* Começa na coluna 1, termina na 3 */
    grid-row: 1 / 2;               /* Primeira linha */
    
    /* Abreviado */
    grid-column: span 2;           /* Ocupa 2 colunas */
    
    /* Alinhamento individual */
    align-self: end;
    justify-self: start;
    
    /* Auto-placement */
    grid-auto-flow: dense;
}
```

### Template Areas

```css
.grid-layout {
    display: grid;
    grid-template-areas:
        "header header header"
        "sidebar main main"
        "footer footer footer";
    
    grid-template-columns: 200px 1fr 1fr;
    grid-template-rows: auto 1fr auto;
    gap: 20px;
}

header {
    grid-area: header;
}

aside {
    grid-area: sidebar;
}

main {
    grid-area: main;
}

footer {
    grid-area: footer;
}
```

---

## 🎨 Transformações

### 2D Transforms

```css
.elemento {
    /* Translação (movimento) */
    transform: translate(50px, 100px);     /* X, Y */
    transform: translateX(50px);
    transform: translateY(100px);
    transform: translate(50%);             /* Relativo ao próprio tamanho */
    
    /* Rotação */
    transform: rotate(45deg);              /* Em graus */
    transform: rotateX(45deg);
    transform: rotateY(45deg);
    
    /* Escala */
    transform: scale(2);                   /* Ambas as dimensões */
    transform: scale(2, 1.5);              /* X, Y */
    transform: scaleX(1.5);
    transform: scaleY(0.5);
    
    /* Inclinação (skew) */
    transform: skew(10deg, 20deg);
    transform: skewX(10deg);
    
    /* Combinação */
    transform: translate(50px, 100px) rotate(45deg) scale(1.5);
    
    /* Origem da transformação */
    transform-origin: center;              /* center, top, bottom, left, right, ... */
    transform-origin: 50% 50%;             /* Coordenadas percentuais */
}
```

### 3D Transforms

```css
.container3d {
    perspective: 1000px;                   /* Profundidade da perspectiva */
}

.elemento3d {
    transform: rotate3d(1, 1, 1, 45deg);
    transform: translateZ(100px);
    transform: rotateX(45deg) rotateY(45deg);
    
    /* Preservar 3D para filhos */
    transform-style: preserve-3d;
    
    /* Visibilidade da face traseira */
    backface-visibility: hidden;
}
```

---

## 💫 Transições

```css
.elemento {
    /* Propriedade afetada */
    transition-property: background-color, color;
    
    /* Duração */
    transition-duration: 0.3s;
    
    /* Delay */
    transition-delay: 0.1s;
    
    /* Função de tempo */
    transition-timing-function: ease-in-out;
    /* ease, linear, ease-in, ease-out, ease-in-out, cubic-bezier() */
    
    /* Shorthand */
    transition: background-color 0.3s ease-in-out 0.1s;
    
    /* Todas as propriedades */
    transition: all 0.3s ease;
}

.elemento:hover {
    background-color: red;
    color: white;
}

/* Bezier customizado */
.suave {
    transition: all 0.5s cubic-bezier(0.25, 0.46, 0.45, 0.94);
}
```

---

## 🎬 Animações

### Keyframes

```css
@keyframes deslizar {
    0% {
        transform: translateX(0);
        opacity: 0;
    }
    
    50% {
        opacity: 1;
    }
    
    100% {
        transform: translateX(500px);
        opacity: 1;
    }
}

.elemento {
    /* Nome da animação */
    animation-name: deslizar;
    
    /* Duração */
    animation-duration: 2s;
    
    /* Delay */
    animation-delay: 0.5s;
    
    /* Função de tempo */
    animation-timing-function: ease-in-out;
    
    /* Iterações */
    animation-iteration-count: infinite;   /* Número ou infinite */
    
    /* Direção */
    animation-direction: alternate;        /* normal, reverse, alternate, alternate-reverse */
    
    /* Estado inicial/final */
    animation-fill-mode: forwards;         /* none, forwards, backwards, both */
    
    /* Shorthand */
    animation: deslizar 2s ease-in-out 0.5s infinite alternate forwards;
    
    /* Controlar animação */
    animation-play-state: paused;          /* running, paused */
}
```

### Exemplos de Animações

```css
/* Pulsação */
@keyframes pulsar {
    0%, 100% {
        transform: scale(1);
        opacity: 1;
    }
    50% {
        transform: scale(1.1);
        opacity: 0.8;
    }
}

/* Rotação contínua */
@keyframes girar {
    from {
        transform: rotate(0deg);
    }
    to {
        transform: rotate(360deg);
    }
}

/* Fade in e fade out */
@keyframes fadeInOut {
    0% {
        opacity: 0;
    }
    50% {
        opacity: 1;
    }
    100% {
        opacity: 0;
    }
}

/* Bounce */
@keyframes bounce {
    0%, 100% {
        transform: translateY(0);
    }
    25% {
        transform: translateY(-20px);
    }
    50% {
        transform: translateY(-40px);
    }
    75% {
        transform: translateY(-20px);
    }
}
```

---

## 📱 Media Queries Avançadas

```css
/* Viewport Width */
@media (max-width: 768px) {
    .sidebar {
        display: none;
    }
}

/* Orientation */
@media (orientation: portrait) {
    .elemento {
        width: 100%;
    }
}

/* Resolução de tela */
@media (min-resolution: 192dpi) {
    .logo {
        width: 100px;
    }
}

/* Preferência de cores */
@media (prefers-color-scheme: dark) {
    body {
        background: #1a1a1a;
        color: #fff;
    }
}

/* Preferência de movimento */
@media (prefers-reduced-motion: reduce) {
    * {
        animation: none !important;
        transition: none !important;
    }
}

/* Múltiplas condições */
@media (min-width: 768px) and (max-width: 1024px) {
    .container {
        width: 90%;
    }
}

/* Condicional OR */
@media (max-width: 600px), (orientation: portrait) {
    .elemento {
        flex-direction: column;
    }
}

/* Container Queries (CSS Moderno) */
@supports (container-type: inline-size) {
    @container (min-width: 400px) {
        .card {
            display: grid;
        }
    }
}
```

### Breakpoints Comuns

```css
/* Mobile First Approach */

/* Extra small devices */
@media (min-width: 0px) {
    /* Estilos base para mobile */
}

/* Small devices (tablets) */
@media (min-width: 576px) {
    /* Ajustes para tablets pequenas */
}

/* Medium devices (tablets maiores) */
@media (min-width: 768px) {
    /* Ajustes para tablets e desktops pequenos */
}

/* Large devices (desktops) */
@media (min-width: 992px) {
    /* Ajustes para desktops */
}

/* Extra large devices */
@media (min-width: 1200px) {
    /* Ajustes para desktops grandes */
}
```

---

## 🌈 Gradientes Avançados

### Linear Gradient

```css
.elemento {
    /* Gradiente simples */
    background: linear-gradient(to right, red, blue);
    
    /* Com ângulo */
    background: linear-gradient(45deg, red, blue);
    
    /* Múltiplas cores */
    background: linear-gradient(
        to right,
        red 0%,
        yellow 25%,
        green 50%,
        blue 75%,
        purple 100%
    );
    
    /* Gradient com posição fixa */
    background: linear-gradient(
        to right,
        red 0,
        red 50%,
        blue 50%,
        blue 100%
    );
}
```

### Radial Gradient

```css
.elemento {
    /* Simples */
    background: radial-gradient(circle, red, blue);
    
    /* Com tamanho e posição */
    background: radial-gradient(
        circle at 30% 30%,
        red,
        blue
    );
    
    /* Múltiplas cores */
    background: radial-gradient(
        circle at center,
        yellow 0%,
        orange 25%,
        red 100%
    );
}
```

### Conic Gradient

```css
.elemento {
    /* Gradiente angular */
    background: conic-gradient(red, yellow, lime, aqua, blue, magenta, red);
    
    /* Com posição customizada */
    background: conic-gradient(
        from 45deg at 50% 50%,
        red 0deg,
        blue 180deg,
        red 360deg
    );
}
```

---

## 🔒 Variáveis CSS e Cálculos

### Custom Properties

```css
:root {
    /* Cores */
    --cor-primaria: #3498db;
    --cor-secundaria: #e74c3c;
    --cor-texto: #333;
    
    /* Espaçamento */
    --espacamento-pequeno: 8px;
    --espacamento-medio: 16px;
    --espacamento-grande: 32px;
    
    /* Tipografia */
    --fonte-principal: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    --tamanho-base: 16px;
    
    /* Sombras */
    --sombra-leve: 0 2px 4px rgba(0, 0, 0, 0.1);
    --sombra-media: 0 4px 8px rgba(0, 0, 0, 0.15);
}

.elemento {
    color: var(--cor-primaria);
    padding: var(--espacamento-medio);
    font-family: var(--fonte-principal);
    box-shadow: var(--sombra-media);
    
    /* Valor padrão se a variável não existir */
    border: 2px solid var(--cor-borda, #ccc);
}

/* Variáveis locais */
.destaque {
    --cor-destaque: #f39c12;
    background-color: var(--cor-destaque);
}

/* Variáveis dinâmicas com JavaScript */
.elemento-dinamico {
    color: var(--cor-dinamica, blue);
}
```

### Calc()

```css
.elemento {
    /* Cálculos básicos */
    width: calc(100% - 20px);
    height: calc(100vh - 80px);
    
    /* Com variáveis */
    padding: calc(var(--espacamento-medio) * 2);
    
    /* Operações complexas */
    font-size: calc(14px + 1vw);
    max-width: calc(100% - (var(--margem) * 2));
    
    /* Min e Max */
    width: min(100%, 500px);
    height: max(100%, 300px);
    
    /* Clamp */
    font-size: clamp(14px, 2.5vw, 24px);  /* min, preferido, max */
}
```

---

## ✨ Filter e Backdrop Filter

```css
.imagem {
    /* Desfoque */
    filter: blur(5px);
    
    /* Brilho */
    filter: brightness(150%);
    
    /* Contraste */
    filter: contrast(200%);
    
    /* Escala de cinzas */
    filter: grayscale(100%);
    
    /* Matiz */
    filter: hue-rotate(90deg);
    
    /* Inverter cores */
    filter: invert(100%);
    
    /* Opacidade */
    filter: opacity(50%);
    
    /* Saturação */
    filter: saturate(200%);
    
    /* Sépias */
    filter: sepia(100%);
    
    /* Combinação */
    filter: brightness(120%) contrast(110%) saturate(130%);
    
    /* Drop Shadow */
    filter: drop-shadow(5px 5px 10px rgba(0, 0, 0, 0.3));
}

/* Backdrop Filter (efeito vidro fosco) */
.modal {
    backdrop-filter: blur(10px);
    background-color: rgba(0, 0, 0, 0.5);
}
```

---

## 🎯 Sombras Avançadas

```css
.elemento {
    /* Box Shadow */
    box-shadow: 10px 10px 20px rgba(0, 0, 0, 0.3);
    
    /* Múltiplas sombras */
    box-shadow: 
        0 1px 3px rgba(0, 0, 0, 0.12),
        0 1px 2px rgba(0, 0, 0, 0.24);
    
    /* Sombra interna */
    box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.3);
    
    /* Text Shadow */
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
    
    /* Efeito de neon */
    text-shadow: 0 0 10px #0ff, 0 0 20px #0ff;
}
```

---

## 🎨 Modos de Blending

```css
.elemento {
    /* Blend modes */
    mix-blend-mode: multiply;      /* multiply, screen, overlay, color-dodge, etc. */
    
    /* Exemplo: lighten */
    mix-blend-mode: lighten;
    
    /* Exemplo: color */
    mix-blend-mode: color;
    
    /* Opacity */
    opacity: 0.7;
    
    /* Isolamento */
    isolation: isolate;
}
```

---

## ✅ Performance e Otimizações

### Propriedades Otimizadas para Animação

```css
/* Otimizado (usa GPU) */
.otimizado {
    animation: deslizar 1s;
}

@keyframes deslizar {
    from {
        transform: translateX(0);
        opacity: 1;
    }
    to {
        transform: translateX(100px);
        opacity: 1;
    }
}

/* Não otimizado (CPU) */
.nao-otimizado {
    animation: mover 1s;
}

@keyframes mover {
    from {
        left: 0;              /* Não usa GPU */
    }
    to {
        left: 100px;          /* Evite left, top, etc. */
    }
}

/* Será */
.elemento {
    will-change: transform, opacity;
    
    /* After animation */
    will-change: auto;          /* Remova quando terminar */
}
```

---

## 📚 Referências Avançadas

- [MDN - CSS Advanced](https://developer.mozilla.org/pt-BR/docs/Web/CSS)
- [CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
- [CSS Flexible Box Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout)
- [CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations)
- [CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
- [CSS Tricks](https://css-tricks.com/)

