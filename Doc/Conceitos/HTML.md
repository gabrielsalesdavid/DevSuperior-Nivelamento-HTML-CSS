# Conceitos Avançados de HTML

## 📌 Introdução

Este documento cobre conceitos avançados e boas práticas profissionais de HTML, indo além dos fundamentos básicos.

---

## 🏗️ Semântica HTML Avançada

### Importância da Semântica

A semântica adequada melhora:
- **SEO** - Motores de busca entendem melhor o conteúdo
- **Acessibilidade** - Leitores de tela navegam melhor
- **Manutenção** - Código mais compreensível
- **Estrutura** - Hierarquia lógica do documento

### Elementos Semânticos Avançados

```html
<!-- Article para conteúdo independente -->
<article>
    <header>
        <h1>Título do Artigo</h1>
        <p>Data: <time datetime="2024-01-13">13 de janeiro de 2024</time></p>
    </header>
    <p>Conteúdo do artigo...</p>
</article>

<!-- Section para agrupamento semântico -->
<section>
    <h2>Serviços</h2>
    <article>
        <h3>Serviço 1</h3>
    </article>
    <article>
        <h3>Serviço 2</h3>
    </article>
</section>

<!-- Details e Summary para conteúdo expansível -->
<details>
    <summary>Clique para expandir</summary>
    <p>Este é o conteúdo oculto.</p>
</details>

<!-- Figure e Figcaption para imagens com caption -->
<figure>
    <img src="imagem.jpg" alt="Descrição">
    <figcaption>Descrição ou legenda da imagem</figcaption>
</figure>

<!-- Mark para destacar texto -->
<p>Este é um <mark>texto destacado</mark>.</p>

<!-- Blockquote para citações -->
<blockquote cite="https://exemplo.com">
    <p>Esta é uma citação de um site externo.</p>
    <cite>Autor</cite>
</blockquote>

<!-- Data List para associações -->
<dl>
    <dt>HTML</dt>
    <dd>HyperText Markup Language</dd>
    <dt>CSS</dt>
    <dd>Cascading Style Sheets</dd>
</dl>
```

---

## 🔗 Atributos Avançados

### Data Attributes
```html
<div data-user-id="12345" data-role="admin">
    Conteúdo
</div>

<script>
    const userElement = document.querySelector('div');
    console.log(userElement.dataset.userId);    // 12345
    console.log(userElement.dataset.role);      // admin
</script>
```

### ARIA (Accessible Rich Internet Applications)
```html
<!-- Indicar que é um botão -->
<div role="button" aria-label="Fechar">×</div>

<!-- Indicar estados -->
<button aria-pressed="false" aria-label="Ativar som">
    🔇
</button>

<!-- Indicar relações -->
<div aria-labelledby="titulo-principal">
    Conteúdo associado ao título
</div>
<h1 id="titulo-principal">Título Principal</h1>

<!-- Indicar que elemento está oculto visualmente -->
<span aria-hidden="true">★</span>

<!-- Indicar carregamento -->
<div aria-busy="true">Carregando...</div>
```

### Atributos de Validação Avançada
```html
<form>
    <!-- Máximo de caracteres -->
    <input type="text" maxlength="50">
    
    <!-- Mínimo de caracteres -->
    <input type="text" minlength="5">
    
    <!-- Padrão regex -->
    <input type="text" pattern="[A-Z]{3}[0-9]{4}">
    
    <!-- Placeholder com padrão de entrada -->
    <input type="tel" placeholder="(XX) XXXXX-XXXX" pattern="(\([0-9]{2}\))\s([0-9]{4,5})-([0-9]{4})">
    
    <!-- Autocomplete -->
    <input type="email" autocomplete="email">
    <input type="password" autocomplete="current-password">
    
    <!-- Input com datalist -->
    <input type="text" list="navegadores">
    <datalist id="navegadores">
        <option value="Chrome">
        <option value="Firefox">
        <option value="Safari">
    </datalist>
</form>
```

---

## 🎯 Estrutura de Formulários Avançada

### Fieldset e Legend
```html
<form>
    <fieldset>
        <legend>Dados Pessoais</legend>
        <label for="nome">Nome:</label>
        <input type="text" id="nome" name="nome">
    </fieldset>
    
    <fieldset>
        <legend>Endereço</legend>
        <label for="rua">Rua:</label>
        <input type="text" id="rua" name="rua">
    </fieldset>
</form>
```

### Grupos de Inputs
```html
<form>
    <!-- Agrupar checkboxes relacionados -->
    <fieldset>
        <legend>Escolha suas tecnologias:</legend>
        
        <label>
            <input type="checkbox" name="tech" value="html"> HTML
        </label>
        <label>
            <input type="checkbox" name="tech" value="css"> CSS
        </label>
    </fieldset>
</form>
```

### Inputs Modernos
```html
<form>
    <!-- Email com validação -->
    <input type="email" required>
    
    <!-- URL -->
    <input type="url" placeholder="https://exemplo.com">
    
    <!-- Número -->
    <input type="number" min="1" max="100" step="5">
    
    <!-- Telefone -->
    <input type="tel">
    
    <!-- Data -->
    <input type="date">
    
    <!-- Hora -->
    <input type="time">
    
    <!-- Data e Hora -->
    <input type="datetime-local">
    
    <!-- Mês -->
    <input type="month">
    
    <!-- Semana -->
    <input type="week">
    
    <!-- Cor -->
    <input type="color" value="#FF0000">
    
    <!-- Range/Slider -->
    <input type="range" min="0" max="100" value="50">
    
    <!-- Upload de arquivo -->
    <input type="file" accept="image/*" multiple>
    
    <!-- Busca -->
    <input type="search" placeholder="Pesquisar...">
</form>
```

---

## 📱 Meta Tags Avançadas

```html
<head>
    <!-- Viewport para responsividade -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- Descrição para SEO -->
    <meta name="description" content="Descrição da página para buscadores">
    
    <!-- Keywords (menos relevante agora, mas ainda usado) -->
    <meta name="keywords" content="html, css, javascript">
    
    <!-- Author -->
    <meta name="author" content="Seu Nome">
    
    <!-- Tema color (Android) -->
    <meta name="theme-color" content="#3498db">
    
    <!-- Apple Touch Icon -->
    <link rel="apple-touch-icon" href="/apple-touch-icon.png">
    
    <!-- Favicon -->
    <link rel="icon" type="image/x-icon" href="/favicon.ico">
    
    <!-- Prefetch e Preload -->
    <link rel="prefetch" href="//exemplo.com/pagina-futura.html">
    <link rel="preload" href="fonte.woff2" as="font" type="font/woff2" crossorigin>
    
    <!-- DNS Prefetch -->
    <link rel="dns-prefetch" href="//cdn.exemplo.com">
    
    <!-- Open Graph para redes sociais -->
    <meta property="og:title" content="Título da Página">
    <meta property="og:description" content="Descrição">
    <meta property="og:image" content="imagem.jpg">
    <meta property="og:url" content="https://exemplo.com">
    
    <!-- Twitter Card -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Título">
    <meta name="twitter:description" content="Descrição">
    <meta name="twitter:image" content="imagem.jpg">
</head>
```

---

## 🎬 Mídia Avançada

### Vídeo com Controles
```html
<video width="320" height="240" controls>
    <source src="video.mp4" type="video/mp4">
    <source src="video.webm" type="video/webm">
    Seu navegador não suporta vídeo HTML5.
</video>
```

### Áudio com Controles
```html
<audio controls>
    <source src="audio.mp3" type="audio/mpeg">
    <source src="audio.ogg" type="audio/ogg">
    Seu navegador não suporta áudio HTML5.
</audio>
```

### Picture para Imagens Responsivas
```html
<picture>
    <source media="(min-width: 1200px)" srcset="imagem-grande.jpg">
    <source media="(min-width: 768px)" srcset="imagem-media.jpg">
    <img src="imagem-pequena.jpg" alt="Descrição">
</picture>
```

### Embed e Iframe
```html
<!-- Iframe para conteúdo externo -->
<iframe width="560" height="315" 
    src="https://www.youtube.com/embed/ID" 
    frameborder="0" 
    allowfullscreen>
</iframe>

<!-- Sandbox para segurança -->
<iframe src="conteudo-nao-confiavel.html" 
    sandbox="allow-scripts allow-same-origin">
</iframe>
```

---

## 🔍 Microdata e Schema.org

```html
<!-- Microdata com Schema.org -->
<div itemscope itemtype="https://schema.org/Person">
    <span itemprop="name">João Silva</span>
    <span itemprop="jobTitle">Desenvolvedor</span>
    <a itemprop="url" href="https://exemplo.com">
        exemplo.com
    </a>
</div>

<!-- Evento -->
<div itemscope itemtype="https://schema.org/Event">
    <h2 itemprop="name">Conferência de Web</h2>
    <p>Data: <time itemprop="startDate" datetime="2024-06-15">15 de junho</time></p>
    <p itemprop="description">Descrição do evento...</p>
</div>

<!-- Avaliação (Rating) -->
<div itemscope itemtype="https://schema.org/Review">
    <span itemprop="name">Ótimo produto!</span>
    <span itemprop="reviewRating" itemscope itemtype="https://schema.org/Rating">
        <span itemprop="ratingValue">5</span>/
        <span itemprop="bestRating">5</span>
    </span>
</div>
```

---

## 🛡️ Segurança em HTML

### Content Security Policy
```html
<meta http-equiv="Content-Security-Policy" 
    content="default-src 'self'; script-src 'self' 'unsafe-inline'">
```

### Atributos de Segurança em Links
```html
<!-- Previne vazamento de referrer -->
<a href="https://exemplo.com" rel="noopener noreferrer">
    Link externo
</a>

<!-- Abre em nova janela com segurança -->
<a href="https://exemplo.com" target="_blank" rel="noopener">
    Link seguro
</a>
```

### HTTPS e Preload
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
```

---

## 📊 Tabelas Avançadas

```html
<table>
    <!-- Cabeçalho da tabela -->
    <thead>
        <tr>
            <th scope="col">Nome</th>
            <th scope="col">Idade</th>
            <th scope="col">Cidade</th>
        </tr>
    </thead>
    
    <!-- Corpo da tabela -->
    <tbody>
        <tr>
            <td>João</td>
            <td>30</td>
            <td>São Paulo</td>
        </tr>
        <tr>
            <td>Maria</td>
            <td>28</td>
            <td>Rio de Janeiro</td>
        </tr>
    </tbody>
    
    <!-- Rodapé da tabela -->
    <tfoot>
        <tr>
            <td colspan="3">Total: 2 registros</td>
        </tr>
    </tfoot>
    
    <!-- Colgroup para agrupar colunas -->
    <colgroup>
        <col style="background-color: #f0f0f0;">
        <col style="background-color: white;">
        <col style="background-color: #f0f0f0;">
    </colgroup>
</table>
```

---

## ⚡ Performance em HTML

### Lazy Loading de Imagens
```html
<img src="imagem.jpg" alt="Descrição" loading="lazy">
```

### Defer e Async em Scripts
```html
<!-- Script com defer (executa após HTML carregar) -->
<script src="script.js" defer></script>

<!-- Script com async (executa assim que carrega) -->
<script src="analytics.js" async></script>
```

### Preload de Recursos Críticos
```html
<link rel="preload" href="font.woff2" as="font" type="font/woff2" crossorigin>
<link rel="preload" href="imagem-hero.jpg" as="image">
<link rel="preload" href="script-critico.js" as="script">
```

---

## ✅ Validação e Acessibilidade

### Checklist de Acessibilidade
- ✅ Alt text em todas as imagens
- ✅ Labels associados a inputs (`for` e `id`)
- ✅ Ordem de tabulação lógica (`tabindex`)
- ✅ Contraste de cores adequado
- ✅ Hierarquia de títulos correcta (h1 → h2 → h3)
- ✅ Atributos ARIA quando necessário
- ✅ Conteúdo acessível via teclado

### Estrutura Correta de Formulários
```html
<form>
    <label for="email">Email:</label>
    <input id="email" type="email" required>
    
    <label for="senha">Senha:</label>
    <input id="senha" type="password" required>
    
    <button type="submit">Enviar</button>
</form>
```

---

## 📚 Referências Avançadas

- [MDN - Advanced HTML](https://developer.mozilla.org/pt-BR/docs/Web/HTML)
- [W3C Specifications](https://www.w3.org/TR/html/)
- [Schema.org](https://schema.org/)
- [WCAG - Web Accessibility](https://www.w3.org/WAI/WCAG21/quickref/)
- [Microdata Specification](https://html.spec.whatwg.org/multipage/microdata.html)

