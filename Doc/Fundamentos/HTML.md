# Fundamentos de HTML

## 📌 O que é HTML?

HTML (HyperText Markup Language) é a linguagem de marcação fundamental para criar páginas web. Ela fornece a estrutura e o conteúdo semântico dos documentos web.

---

## 🏗️ Estrutura Básica de um Documento HTML

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Título da Página</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Cabeçalho</h1>
    </header>
    
    <main>
        <section>
            <h2>Seção Principal</h2>
            <p>Conteúdo aqui</p>
        </section>
    </main>
    
    <footer>
        <p>&copy; 2024 Todos os direitos reservados.</p>
    </footer>
</body>
</html>
```

---

## 🏷️ Elementos HTML Essenciais

### 1. **Meta Tags**
Fornecem informações sobre o documento:

| Tag | Função |
|-----|--------|
| `<meta charset="UTF-8">` | Define a codificação de caracteres |
| `<meta name="viewport" content="width=device-width, initial-scale=1.0">` | Torna a página responsiva |
| `<meta name="description" content="">` | Descrição para buscadores |

### 2. **Estrutura Semântica**

| Tag | Uso |
|-----|-----|
| `<header>` | Cabeçalho da página ou seção |
| `<nav>` | Barra de navegação |
| `<main>` | Conteúdo principal |
| `<section>` | Seção de conteúdo |
| `<article>` | Artigo independente |
| `<aside>` | Conteúdo lateral/complementar |
| `<footer>` | Rodapé |

### 3. **Títulos e Textos**

```html
<h1>Título Principal</h1>      <!-- Único por página -->
<h2>Subtítulo</h2>              <!-- Nível 2 -->
<h3>Subtítulo nível 3</h3>      <!-- Nível 3 -->

<p>Parágrafo de texto</p>
<strong>Texto em negrito (semântico)</strong>
<em>Texto em itálico (semântico)</em>
```

### 4. **Listas**

**Lista Não Ordenada:**
```html
<ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ul>
```

**Lista Ordenada:**
```html
<ol>
    <li>Primeiro</li>
    <li>Segundo</li>
    <li>Terceiro</li>
</ol>
```

### 5. **Links**

```html
<!-- Link simples -->
<a href="https://exemplo.com">Clique aqui</a>

<!-- Link interno -->
<a href="./outra-pagina.html">Página Interna</a>

<!-- Link com âncora -->
<a href="#secao1">Ir para Seção 1</a>
```

### 6. **Imagens**

```html
<img src="caminho/imagem.jpg" alt="Descrição da imagem" width="300" height="200">
```

**Atributos importantes:**
- `src` - Caminho da imagem
- `alt` - Texto alternativo (acessibilidade)
- `width` e `height` - Dimensões

---

## 📋 Formulários

### Estrutura Básica

```html
<form action="processar.php" method="POST">
    <!-- Campo de texto -->
    <label for="nome">Nome:</label>
    <input type="text" id="nome" name="nome" required>
    
    <!-- Email -->
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>
    
    <!-- Senha -->
    <label for="senha">Senha:</label>
    <input type="password" id="senha" name="senha">
    
    <!-- Checkbox -->
    <input type="checkbox" id="termos" name="termos">
    <label for="termos">Aceito os termos</label>
    
    <!-- Radio Button -->
    <label>
        <input type="radio" name="opcao" value="sim"> Sim
    </label>
    <label>
        <input type="radio" name="opcao" value="nao"> Não
    </label>
    
    <!-- Select (Dropdown) -->
    <label for="pais">País:</label>
    <select id="pais" name="pais">
        <option value="">Selecione um país</option>
        <option value="br">Brasil</option>
        <option value="us">Estados Unidos</option>
    </select>
    
    <!-- Textarea -->
    <label for="mensagem">Mensagem:</label>
    <textarea id="mensagem" name="mensagem" rows="5"></textarea>
    
    <!-- Botão -->
    <button type="submit">Enviar</button>
    <button type="reset">Limpar</button>
</form>
```

---

## 🎯 Atributos Comuns

| Atributo | Função | Exemplo |
|----------|--------|---------|
| `id` | Identificador único | `<div id="header">` |
| `class` | Classe CSS | `<p class="destaque">` |
| `style` | Estilos inline | `<p style="color: red;">` |
| `alt` | Texto alternativo | `<img alt="Logo">` |
| `href` | Link | `<a href="url">` |
| `src` | Fonte (imagem, script) | `<img src="url">` |
| `disabled` | Desativa elemento | `<button disabled>` |
| `required` | Campo obrigatório | `<input required>` |

---

## 🔗 Entidades HTML Comuns

| Entidade | Símbolo |
|----------|---------|
| `&copy;` | © |
| `&reg;` | ® |
| `&trade;` | ™ |
| `&nbsp;` | Espaço em branco |
| `&lt;` | < |
| `&gt;` | > |
| `&amp;` | & |

---

## 📱 Responsividade Básica

```html
<head>
    <!-- Meta tag viewport obrigatória -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
```

---

## ✅ Boas Práticas

1. **Semântica:** Use tags semânticas apropriadas
2. **Acessibilidade:** Sempre use `alt` em imagens
3. **Organização:** Indente o código corretamente
4. **Convenção de nomes:** Use nomes descritivos e em minúsculas
5. **Meta charset:** Sempre defina `<meta charset="UTF-8">`
6. **Validação:** Valide seu HTML em [W3C Validator](https://validator.w3.org/)

---

## 📚 Referências

- [MDN Web Docs - HTML](https://developer.mozilla.org/pt-BR/docs/Web/HTML)
- [W3C HTML Standard](https://www.w3.org/TR/html52/)
- [HTML Validator](https://validator.w3.org/)

