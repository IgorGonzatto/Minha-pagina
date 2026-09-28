# Minha-pagina
Trabalho academico da materia de FrontEnd G1
Professor: Matheus Henrique Barquette 
Site usado de inspiração para o trabalho: https://www.chevrolet.com.br/carros-vintage
Aluno: Igor Gonzatto RA: 1139324 (Optei por fazer individual)

## Checklist — Parte 1

### 1.1 Estrutura HTML semântica e acessível

- [x] **Tags semânticas:** a página utiliza `<header>` para o cabeçalho com a navegação, `<nav>` com `aria-label` para o menu principal, `<main>` envolvendo todo o conteúdo relevante, `<section>` para separar cada bloco temático (hero, comprar, sobre, contato) e `<footer>` para o rodapé.
- [x] **Imagens com `alt` descritivo:** todas as imagens possuem atributo `alt` com descrição do conteúdo — "Logo da Chevrolet", "Carro Chevrolet clássico Opala" e "Opala, Omega, S10 e Monza, carros clássicos da Chevrolet Vintage".
- [x] **Formulário acessível:** a seção de contato contém um formulário com `<label>` associado a cada campo via atributo `for`/`id` (nome, e-mail, mensagem). Os campos de nome e e-mail têm `required` e `autocomplete`. A mensagem de feedback pós-envio usa `role="alert"` e `aria-live="polite"` para leitores de tela.

**Análise do site de referência (chevrolet.com.br/carros-vintage):**  
O site original utiliza `<header>` com logo centralizada e navegação lateral, seções bem delimitadas com `<section>` e imagens de destaque. Não foi identificado um formulário de contato na página original; optei por criar um formulário de contato temático para cumprir o requisito do trabalho. As imagens no original não possuem `alt` adequado em todos os casos — neste clone todas foram descritas corretamente. A fonte original é paga (GM Sans); substituí por Arial/Helvetica, família sem serifa equivalente e de ampla disponibilidade.

---

### 1.2 Fidelidade visual à referência escolhida

- [x] **Proporções e espaçamentos:** o cabeçalho reproduz a altura e o espaçamento lateral do original. A seção hero mantém a imagem em tela cheia com overlay escuro e o texto posicionado no canto superior esquerdo, assim como no site de referência.
- [x] **Cores:** a paleta bege/creme (`#f8f3e8`) das seções de conteúdo e o fundo escuro (`#111`) do formulário foram escolhidos a partir da observação visual do site original.
- [x] **Tipografia:** fonte substituída de GM Sans (paga) por Arial/Helvetica, sans-serif gratuita de aparência semelhante.
- [x] **Organização geral:** cabeçalho → hero → seções de conteúdo → formulário → rodapé, respeitando a hierarquia visual da referência.

---

### 1.3 CSS: seletores, box model e variáveis

- [x] **Variáveis CSS:** definidas em `:root` — cores, fonte, espaçamento lateral e transição padrão (`--cor-fundo-claro`, `--fonte-base`, `--espacamento-lateral`, etc.).
- [x] **Seletores utilizados:**
  - **Classe:** `.cabecalho`, `.hero`, `.comprar`, `.contato`, `.rodape` — estilização dos blocos principais.
  - **Descendente:** `.navegacao a`, `.campo label`, `.campo input` — aplica estilo a elementos dentro de um contexto específico.
  - **Pseudo-elemento:** `.navegacao a::after` (sublinhado animado), `.hero::after` (overlay escuro sobre a imagem).
  - **Pseudo-classe:** `.navegacao a:hover`, `.campo input:focus`, `.comprar-conteudo p:last-child`, `.rodape p + p` (seletor adjacente).
- [x] **Box model:** uso de `padding`, `margin`, `border-bottom` e `box-sizing: border-box` em toda a página.

---

### 1.4 Responsividade: Flexbox, Grid e mobile first

- [x] **Mobile first:** o CSS base foi escrito para telas pequenas (sem nenhuma media query ativa por padrão). O layout funciona completamente em celular sem depender de `@media`.
- [x] **Flexbox:** usado no cabeçalho (logo + navegação), na navegação (links em linha), no formulário (campos em coluna) e no cabeçalho responsivo (linha com espaçamento entre elementos).
- [x] **Media query com `min-width`:** `@media (min-width: 768px)` ajusta o cabeçalho para layout horizontal com logo absolutamente centralizada, aumenta o hero para 610px, amplia fontes e espaçamentos das seções para proporções de desktop.
- [x] **Testado em mobile e desktop:** em mobile o cabeçalho empilha logo e navegação; em desktop a logo fica centralizada e a navegação à esquerda, reproduzindo o layout do site original.

---

### 1.5 Personalização e originalidade

- [x] **Formulário de contato criado:** a página de referência não possui formulário; criei uma seção "Fale Conosco" com campos de nome, e-mail e mensagem, cumprindo o requisito de formulário funcional.
- [x] **Feedback via JavaScript:** ao enviar o formulário, um script intercepta o evento, exibe uma mensagem de confirmação acessível, limpa os campos e esconde o feedback após 5 segundos — funcionalidade inexistente no site original.
- [x] **Rodapé personalizado:** o rodapé identifica o projeto como trabalho acadêmico de Igor Gonzatto, com crédito à referência, diferenciando-o do site original.
