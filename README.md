
# Resumo do Código (Blue Origin)

Este projeto implementa a interface proposta usando **HTML5**, **CSS (Flexbox/Grid)** e a fonte **Barlow** do Google Fonts. A página está organizada em seções de cabeçalho, herói, conteúdo, carreiras e rodapé, com comportamento responsivo e menu sanduíche.

## Estrutura de Pastas
- `index.html`: estrutura principal da página.
- `css/estilo.css`: estilos globais, layout e responsividade.
- `img/`: imagens de carreiras utilizadas nos cards.
- `favicon.ico`: ícone da aba do navegador.
- Imagens na raiz: `bg_banner.png`, `blue_origin_symbol.png`, `retorne_terra.png`, `janela_assento.png`, `play.png`, `menu_hamburguer.png`.

## Cabeçalho (Header)
- `header.header` com `.container` usa `display: flex` para alinhar logo, menu e ações à direita.
- Menu de navegação:
  - `.navbar { flex: 1 1 auto; }` faz o menu ocupar o espaço central.
  - `.navbar ul` usa `display: flex` e `justify-content: space-evenly` para espaçamento igual entre itens e nas bordas.
  - Links em branco; item ativo (`.active`) tem sublinhado com `#D9D9D9`.
- Botão CTA: `.btn.btn-light` com fundo `#D9D9D9` e texto `#0033DD`.
- Ícone do menu (`menu_hamburguer.png`) sempre visível; em telas ≤1024px o menu colapsa e abre com clique.

## Menu Sanduíche (Responsivo)
- CSS (em `@media (max-width: 1024px)`):
  - `.navbar` colapsa com `max-height: 0`, `overflow: hidden` e transição.
  - `.navbar.open` expande (`max-height` maior).
  - `.navbar ul` vira coluna, ocupando `width: 100%`.
- JavaScript (no final do `index.html`):
  - Alterna a classe `.open` na `.navbar` ao clicar no `.menu-toggle`.
  - Atualiza `aria-hidden` conforme largura da janela para acessibilidade.

## Seção Herói (Hero)
- `.hero` ocupa `100vh`, centraliza o conteúdo e aplica gradiente com pseudo-elemento.
- `.hero-bg` usa `bg_banner.png` como plano de fundo.
- Título em branco (Barlow Bold) e botão `btn btn-blue`.
- Navegação de slider (`.hero-slider-nav`) com marcadores.

## Seção de Conteúdo
- `.content-section` (fundo `#747272`).
- Blocos (`.content-block`) usam `grid` com duas colunas: painel fixo (380px) + imagem.
- Variante `.reverse` inverte a ordem das colunas.
- Painel escuro (`.content-text.dark-bg`) com tipografia branca e cinza claro.
- Link com ícone (`.icon-link`) usa `play.png`.

## Seção de Carreiras
- `.careers-section` em cinza claro (`#D9D9D9`).
- `.careers-grid` usa `grid` com 3 colunas.
- Cada `.career-card` tem imagem (`object-fit: cover`) e área de informação azul (`#0033DD`).
- Botão `.btn-outline` estilizado para contraste sobre o azul.

## Rodapé (Footer)
- `.footer-grid` usa `grid` com 3 colunas.
- Coluna esquerda: logo (`blue_origin_symbol.png`) e links legais.
- Coluna central: navegação de links.
- Coluna direita: `.footer-subscribe` com fundo escuro (`rgb(56,56,56)` ≈ `#383838`), ocupando altura total e largura da coluna.
  - `.subscribe-form` (painel interno) com fundo `#8C8C8C`, borda leve e `padding`.
  - Inputs e textarea com fundo branco; botão `.btn-dark` preenchendo a largura.

## Responsividade
- `@media (max-width: 1024px)`: menu vira vertical; footer pode ocupar largura total; grid de carreiras muda para 2 colunas.
- `@media (max-width: 768px)`: conteúdo fica em uma coluna; carreiras e footer em 1 coluna.

## Como Executar
- Abrir diretamente o arquivo `index.html` em um navegador, ou
- Usar o servidor local e acessar `http://localhost:8001/`.

## Observações
- O layout utiliza extensivamente `flex` e `grid` para alinhamento e distribuição.
- Há uso pontual de pseudo-elementos e gradientes; ajustes finos podem ser feitos sem alterar a estrutura.
- Se for necessário aderir estritamente à regra de **não usar `position`**, algumas partes (como overlays/gradientes e marcação do slider) podem ser refatoradas para usar apenas `flex/grid` e múltiplos `backgrounds`.