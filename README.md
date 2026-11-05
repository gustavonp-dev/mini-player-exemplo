# Desafio Prático: Recriando o YouTube Music Player
## Unidade Curricular: Desenvolvimento Front-End • SENAI MG

### 🎯 Objetivo do Desafio:
Nesta atividade prática, você irá **recriar do zero** (estruturando seu próprio arquivo `index.html` e estilizando seu `styles.css`) uma interface inspirada no **YouTube Music**, dominando a aplicação de **posicionamento no CSS** (`relative`, `absolute`, `fixed`, `sticky`) e hierarquia de camadas com **z-index**.

Você tem à sua disposição a pasta `assets/` com a arte do clipe musical e o logo oficial.

---

### 🎨 Guia de Estilos Oficial (Design System)

Para que sua reprodução chegue o mais próximo possível do resultado profissional esperado, utilize exatamente as seguintes especificações:

#### 1. Tipografia
* **Fonte principal:** `Arial, Helvetica, sans-serif`
* **Pesos utilizados:** `normal` (400) para legendas e parágrafos, `bold` (700) para títulos, badges e botões.

#### 2. Paleta de Cores (Tabela de Referência Hexadecimal)
| Elemento da Interface | Cor Hex / RGBA | Finalidade Visual |
| :--- | :--- | :--- |
| **Fundo da Página** | `#030303` | Fundo preto característico do YouTube Music |
| **Fundo do Cabeçalho** | `#030303` | Cabeçalho superior (com borda inferior `#272727`) |
| **Containers (Player e Fila)** | `#0f0f0f` | Fundo das seções de informações e da lista de faixas |
| **Fundo da Tela do Vídeo** | `#121212` | Moldura de fundo da arte do clipe |
| **Fundo do Miniplayer** | `#1f1f1f` | Widget flutuante no canto da tela (borda `#383838`) |
| **Vermelho YouTube** | `#ff0000` | Ícone do logo, barra de progresso atual e tag do miniplayer |
| **Vermelho Curtir (Like)** | `#ff0033` | Borda e texto do botão "♥ CURTIR" |
| **Texto Principal** | `#ffffff` / `#f1f1f1` | Títulos das músicas, logo e textos em destaque |
| **Texto Secundário** | `#aaaaaa` / `#888888` | Nomes de artistas, visualizações e contadores de tempo |
| **Linhas e Bordas** | `#272727` / `#1a1a1a` | Divisores sutis entre faixas e bordas dos blocos |
| **Badges Flutuantes Escuras** | `rgba(0, 0, 0, 0.75)` | Fundo translúcido para "1080p HD" e tempo do clipe |
| **Badge Modo Música/Vídeo** | `rgba(255, 255, 255, 0.2)` | Fundo translúcido do alternador de exibição |

---

### 📐 Requisitos Técnicos de Posicionamento

Seu CSS deve contemplar obrigatoriamente os seguintes comportamentos espaciais:

1. **Cabeçalho com Rolagem (`position: sticky`):**
   * Deve permanecer no fluxo normal no topo e **congelar em `top: 0`** com `z-index: 100` assim que o usuário rolar a página.
2. **Tela do Clipe como Âncora (`position: relative`):**
   * O container que envolve a imagem `capa-player.svg` deve receber `position: relative` para servir de base às coordenadas dos botões filhos.
3. **Badges e Botões Sobrepostos (`position: absolute`):**
   * **1080p HD:** Fixado no canto superior esquerdo (`top: 16px; left: 16px; z-index: 10;`).
   * **VÍDEO • MÚSICA:** Fixado no canto superior direito (`top: 16px; right: 16px; z-index: 10;`).
   * **Tempo do Clipe:** Fixado no canto inferior esquerdo (`bottom: 16px; left: 16px; z-index: 10;`).
   * **Botão Curtir:** Fixado no canto inferior direito (`bottom: 16px; right: 16px; z-index: 10;`).
4. **Miniplayer Picture-in-Picture (`position: fixed`):**
   * Deve flutuar no canto inferior direito da janela (`bottom: 24px; right: 24px; width: 320px; z-index: 1000;`) acompanhando a tela mesmo durante a rolagem.

---

### 🚀 Desafio Extra (Biblioteca de Ícones via CDN)
Para que os botões do seu player não fiquem com emojis ou textos improvisados, seu desafio para concluir a entrega com visual 100% profissional é importar uma biblioteca de ícones vetoriais diretamente via `<link>` no `<head>` do seu HTML!

**Exemplo recomendado (Font Awesome 6 via CDN):**
Importe no `<head>`:
```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
```
E utilize os ícones dentro dos botões:
* Play: `<i class="fa-solid fa-play"></i>`
* Pausa: `<i class="fa-solid fa-pause"></i>`
* Faixa Anterior: `<i class="fa-solid fa-backward-step"></i>`
* Próxima Faixa: `<i class="fa-solid fa-forward-step"></i>`
* Aleatório: `<i class="fa-solid fa-shuffle"></i>`
* Repetir: `<i class="fa-solid fa-repeat"></i>`
* Coração / Like: `<i class="fa-solid fa-heart"></i>`
* Fechar: `<i class="fa-solid fa-xmark"></i>`

*(Alternativas gratuitas equivalentes: **Bootstrap Icons** ou **Remix Icon**).*

---

### ⚠️ Regras Importantes de Implementação:
* **Sem Flexbox:** Como o módulo de Flexbox só será introduzido nas próximas aulas, estruture seu layout utilizando o **Box Model** tradicional (`margin: 0 auto` para centralizar blocos, `display: block` e `display: inline-block` com `vertical-align: middle` para itens lado a lado).
* **HTML Semântico:** Utilize as tags adequadas (`<header>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<h2>`, `<button>`, etc.).
* **Botões Nativos:** Elementos interativos clicáveis devem ser tags `<button>`.

---

### 📂 Arquivos Fornecidos na pasta `assets/`:
* `assets/capa-player.svg`: Imagem do clipe musical Synthwave (proporção 16:9).
* `assets/logo-ytmusic.svg`: Ícone vetorial do YouTube Music.
