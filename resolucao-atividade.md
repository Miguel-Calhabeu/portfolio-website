# Introdução ao CSS no Desenvolvimento Front-end

**Aluno:** Miguel Filippo Rocha Calhabeu
**Atividade:** Introdução ao CSS no Desenvolvimento Front-end
**Template escolhido:** MyResume, da BootstrapMade
**Link do portfólio publicado:** pendente de publicação no GitHub Pages

## 1. Diferença entre HTML e CSS

HTML e CSS têm funções diferentes dentro de uma página web.

O **HTML** é responsável pela estrutura e pelo conteúdo da página. É com HTML que definimos quais elementos existem: títulos, parágrafos, imagens, links, listas, botões, formulários, seções e áreas de navegação. Em outras palavras, o HTML organiza o significado da página e cria a base que o navegador interpreta.

O **CSS** é responsável pela apresentação visual dessa estrutura. Ele define cores, tamanhos, fontes, espaçamentos, bordas, alinhamentos, responsividade e estados visuais de interação, como o efeito ao passar o mouse sobre um botão.

As duas tecnologias se complementam porque o HTML cria a estrutura semântica e o CSS transforma essa estrutura em uma interface visual agradável, organizada e adaptável a diferentes tamanhos de tela. Por exemplo, um botão pode ser criado em HTML com a tag `<a>` ou `<button>`, enquanto o CSS define sua cor, seu tamanho, sua borda e seu comportamento visual ao receber foco ou hover.

## 2. Exemplos de uso de CSS

### `color`

A propriedade `color` define a cor do texto de um elemento. Ela afeta diretamente a leitura e a hierarquia visual da página.

```css
p {
  color: #18212f;
}
```

### `font-size`

A propriedade `font-size` define o tamanho do texto. Ela ajuda a diferenciar títulos, subtítulos, parágrafos e informações secundárias.

```css
h1 {
  font-size: 4rem;
}
```

### `background-color`

A propriedade `background-color` define a cor de fundo de um elemento. Ela pode ser usada para destacar seções, cartões, botões e áreas de navegação.

```css
.button-primary {
  background-color: #0f766e;
  color: #ffffff;
}
```

### Exemplo completo

```html
<section class="exemplo">
  <h1>Meu portfólio</h1>
  <p>Sou estudante de desenvolvimento web.</p>
  <a class="botao" href="#contato">Contato</a>
</section>
```

```css
.exemplo {
  background-color: #f6f7f9;
  padding: 32px;
}

.exemplo h1 {
  color: #0f766e;
  font-size: 40px;
}

.botao {
  background-color: #0f766e;
  color: white;
  padding: 12px 18px;
}
```

## 3. Formas de aplicar CSS em uma página HTML

### CSS inline

O CSS inline é aplicado diretamente no elemento HTML, usando o atributo `style`.

```html
<p style="color: #0f766e; font-size: 18px;">
  Texto estilizado com CSS inline.
</p>
```

**Vantagens:** é simples para testes rápidos e afeta apenas o elemento em que foi aplicado.
**Desvantagens:** dificulta manutenção, reaproveitamento e padronização visual. Em projetos maiores, torna o código repetitivo e menos organizado.

### CSS interno

O CSS interno é escrito dentro da própria página HTML, geralmente dentro da tag `<style>` no `<head>`.

```html
<!DOCTYPE html>
<html lang="pt-BR">
  <head>
    <style>
      h1 {
        color: #0f766e;
      }
    </style>
  </head>
  <body>
    <h1>Portfólio</h1>
  </body>
</html>
```

**Vantagens:** mantém os estilos concentrados na página e é útil quando há apenas uma página pequena.
**Desvantagens:** não reaproveita os estilos entre várias páginas e aumenta o tamanho do arquivo HTML.

### CSS externo

O CSS externo fica em um arquivo separado, como `styles.css`, conectado ao HTML por meio da tag `<link>`.

```html
<link rel="stylesheet" href="assets/css/styles.css" />
```

```css
body {
  font-family: Arial, sans-serif;
  background-color: #f6f7f9;
}
```

**Vantagens:** melhora organização, reaproveitamento, manutenção e separação de responsabilidades entre estrutura e aparência.
**Desvantagens:** depende do carregamento de mais um arquivo; se o caminho estiver errado, a página perde a estilização.

## 4. Entendendo template web e seus estilos

O template escolhido foi o **MyResume**, da BootstrapMade:
https://bootstrapmade.com/free-html-bootstrap-template-my-resume/

Segundo a página da BootstrapMade, o MyResume é um template de currículo e portfólio construído com Bootstrap, HTML5, CSS3 e jQuery, com layout responsivo e seções de portfólio.

### Tipos de CSS identificados

No modelo escolhido e na adaptação criada para esta atividade, o tipo principal de CSS é o **CSS externo**. Na adaptação, isso aparece no arquivo HTML:

```html
<link rel="stylesheet" href="assets/css/styles.css" />
```

Também há uso de CSS externo por bibliotecas, como o Bootstrap Icons:

```html
<link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.css"
/>
```

Não foi necessário usar CSS inline para montar o portfólio final, porque a separação em arquivo externo é mais organizada. Também não foi usado CSS interno no projeto final, embora ele tenha sido demonstrado na questão anterior.

### Seletores simples

Seletores simples selecionam elementos por nome de tag, classe, id, grupo ou seletor universal.

Exemplos usados no arquivo `assets/css/styles.css`:

```css
* {
  box-sizing: border-box;
}

body {
  margin: 0;
}

#topo {
  scroll-margin-top: 0;
}

.button-primary {
  background: var(--color-primary);
}

p,
h1,
h2,
h3 {
  margin-top: 0;
}
```

### Seletores de pseudo-classes

Pseudo-classes selecionam elementos em um estado específico, como `:hover`, `:focus-visible` ou `:nth-child()`.

```css
.nav-list a:hover,
.nav-list a:focus-visible {
  background: #e8f3f1;
  color: var(--color-primary-dark);
}

.project-card:nth-child(2) {
  border-top: 4px solid var(--color-primary);
}
```

### Seletores combinadores

Combinadores selecionam elementos com base na relação entre eles.

```css
.nav-list > li {
  display: flex;
}

.section-header + .lead {
  margin-bottom: 18px;
}

.muted-section > * {
  max-width: var(--max-width);
}

.project-card h3 {
  margin-bottom: 12px;
}
```

No primeiro exemplo, `>` seleciona filhos diretos. No segundo, `+` seleciona o elemento imediatamente seguinte. No último, o espaço indica seleção de descendente.

### Seletores de pseudo-elementos

Pseudo-elementos estilizam uma parte específica do elemento ou criam uma parte visual extra.

```css
::selection {
  background: rgba(15, 118, 110, 0.24);
}

.profile-panel::before {
  content: "";
  border-top: 4px solid var(--color-accent);
}

a[target="_blank"]::after {
  content: " ↗";
}
```

### Seletores de atributos

Seletores de atributos selecionam elementos com base na existência ou valor de um atributo.

```css
a[target="_blank"]::after {
  content: " ↗";
}

.project-card[data-category="api"] {
  background: #fbfdfc;
}

.contact-grid a[href^="mailto:"] {
  color: var(--color-primary-dark);
}
```

## 5. Adaptação do template para portfólio profissional

Foi criada uma adaptação do template de portfólio profissional com as seguintes seções:

### Sobre mim

Nome: Miguel Filippo Rocha Calhabeu.

Descrição: desenvolvedor em formação com interesse em arquitetura de software, engenharia de dados e inteligência artificial aplicada.

Área de interesse: arquitetura de software, engenharia de dados, IA aplicada, automação e integrações via APIs, com estudo atual sobre Amazon SP-API.

### Habilidades

Soft skills incluídas:

- Organização e responsabilidade com prazos
- Comunicação objetiva
- Trabalho em equipe
- Aprendizado contínuo
- Resolução estruturada de problemas

Tecnologias incluídas:

- HTML
- CSS
- JavaScript
- Python
- SQL
- Git
- GCP
- BigQuery
- GA4
- APIs REST
- Next.js
- TypeScript
- Amazon SP-API
- IA aplicada

### Projetos

**Projeto 1: Autenticação segura para integrações de marketplace**
Descrição: serviço para resolver tokens OAuth válidos para consumidores de ingestão, removendo lógica de refresh de webhooks individuais e centralizando ciclo de vida, IAM, Firestore e Secret Manager.
Tecnologias: Python, Google Cloud Functions, Firestore, Secret Manager, IAM e pytest.

**Projeto 2: Pipeline de dados para funil de vendas digital**
Descrição: pipeline acionado por eventos no GCS para ingerir planilhas Excel, aplicar tratamento em Python, carregar staging no BigQuery e consolidar métricas diárias e mensais por MERGE incremental.
Tecnologias: Python, pandas, Cloud Functions, GCS, BigQuery e SQL.

**Projeto 3: Dashboard financeiro de contas a pagar**
Descrição: dashboard operacional para consolidar dados financeiros de múltiplos tenants do Tiny ERP, com API Routes atuando como proxy, normalização de dados e visualizações para acompanhamento de fluxo de caixa.
Tecnologias: Next.js, TypeScript, Tailwind CSS, Google Cloud IAP, Recharts e Tiny ERP API.

**Projeto 4: Conferência automatizada de estoque**
Descrição: aplicação local em Streamlit para comparar estoque de Magalu e Mercado Livre contra Tiny ERP, com mapeamento DE-PARA de SKUs, consulta à API e geração de snapshots auditáveis.
Tecnologias: Python, Streamlit, pandas, Excel, Tiny API e JSON.

**Projeto 5: Análise estatística de conversão em site**
Descrição: análise estatística para inferir gatilhos de pop-up por inatividade ou scroll usando eventos GA4 exportados para BigQuery, timestamps, segmentação e bootstrap para intervalos de confiança.
Tecnologias: BigQuery, GA4, Python, pandas, estatística e visualização de dados.

**Projeto 6: Padronização inteligente de tags de marketing**
Descrição: CLI para propor renomeações padronizadas em exports do Google Tag Manager com apoio de modelo de IA, validação estrutural em Python e reescrita segura de referências de variáveis.
Tecnologias: Python, Gemini/OpenRouter, JSON Schema, GTM e automação com IA.

### Contato

O portfólio contém uma seção de contato com:

- E-mail
- LinkedIn
- GitHub acadêmico
- GitHub pessoal
- Botão de envio de mensagem por e-mail

Os contatos utilizados no portfólio são:

- `miguel.calhabeu@gmail.com`
- `https://www.linkedin.com/in/miguel-filippo-calhabeu-40654130a/`
- `https://github.com/miguel-filippo`
- `https://github.com/Miguel-Calhabeu`

## Personalização visual com CSS

Foram feitas as seguintes alterações visuais:

### Alteração das cores principais

As cores principais foram definidas com variáveis CSS. A paleta usa fundo cinza frio, texto escuro, verde técnico como cor primária e laranja como cor de destaque:

```css
:root {
  --color-background: #eef1f5;
  --color-text: #17202c;
  --color-primary: #0f766e;
  --color-primary-dark: #0b4f4a;
  --color-accent: #b84613;
}
```

### Modificação de tipografia e tamanho de textos

A tipografia foi personalizada com duas fontes: Atkinson Hyperlegible para textos corridos e Fraunces para títulos. Essa combinação melhora a leitura e cria uma identidade visual mais editorial:

```css
body {
  font-family: var(--font-body);
}

h1,
h2 {
  font-family: var(--font-display);
}
```

Os tamanhos de título foram ajustados por breakpoints, mantendo hierarquia visual sem depender de escala contínua pelo tamanho da tela:

```css
h1 {
  font-size: 5rem;
}

@media (max-width: 520px) {
  h1 {
    font-size: 3rem;
  }
}
```

### Personalização de botões e links

Os botões receberam cor própria, borda, espaçamento, ícone, sombra e estados de hover/focus:

```css
.button-primary {
  background: var(--color-primary);
  color: #ffffff;
  box-shadow: 5px 5px 0 rgba(15, 118, 110, 0.2);
}

.button-primary:hover,
.button-primary:focus-visible {
  background: var(--color-primary-dark);
  box-shadow: 8px 8px 0 rgba(15, 118, 110, 0.18);
}
```

Além disso, foram aplicados recursos adicionais de CSS para demonstrar domínio visual:

- fundo com grid sutil usando múltiplos `linear-gradient`;
- contadores automáticos nas seções com `counter-reset` e `counter-increment`;
- pseudo-elementos em cards e painéis para criar detalhes gráficos;
- estados acessíveis com `:focus-visible`;
- media queries para responsividade;
- `prefers-reduced-motion` para respeitar usuários que reduzem animações.

## GitHub Pages

[miguel-calhabeu.github.io/portfolio-website](https://miguel-calhabeu.github.io/portfolio-website/)

