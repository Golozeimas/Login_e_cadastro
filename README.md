# 🔐 Sistema de Login & Cadastro

Interface web de autenticação composta por duas telas: **Login** e **Cadastro**, com layout responsivo e design moderno em duas colunas.

---

## 📁 Estrutura do Projeto

```
projeto/
├── login/
│   ├── index.html
│   ├── style.css
│   └── imgs/
│       ├── info.png
│       └── code.svg
├── cadastro/
│   ├── cadastro.html
│   ├── style.css
│   └── imgs/
│       ├── info.png
│       └── code.svg
└── README.md
```

---

## 🚀 Como Utilizar

1. **Clone ou baixe** os arquivos do projeto.
2. Abra o arquivo `login/index.html` em qualquer navegador moderno — nenhuma instalação ou servidor é necessário.
3. Na tela de login, clique em **"Cadastre-se"** para navegar até a tela de cadastro.
4. Na tela de cadastro, após preencher o formulário e clicar em **"Criar conta"**, o formulário redireciona para `login.html`.
5. O link **"Conecte-se"** na tela de cadastro retorna à tela de login.

> ⚠️ O projeto é puramente front-end. Não há back-end ou banco de dados — os formulários não processam dados reais.

---

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Uso |
|---|---|
| **HTML5** | Estrutura semântica das páginas |
| **CSS3** | Estilização, layout e responsividade |
| **Flexbox** | Sistema de layout das colunas e alinhamentos |
| **Google Fonts (Roboto)** | Tipografia da interface |
| **CSS Media Queries** | Adaptação para telas menores |
| **SVG** | Ícone do logo em vetor escalável |

---

## 📚 Aprendizados Aplicados

### Layout com Flexbox
Uso do Flexbox para construir o layout de duas colunas lado a lado (`flex-direction: row`), com cada coluna ocupando metade da tela via `flex: 1`. Em telas menores, o layout muda para coluna única (`flex-direction: column`).

### Responsividade com Media Queries
A quebra de layout acontece em `1172px` de largura. Abaixo desse ponto, as seções se reorganizam verticalmente, imagens são redimensionadas e os inputs passam a ocupar 100% da largura disponível — garantindo usabilidade em celulares e tablets.

### Navegação entre páginas HTML
Uso do atributo `action` no `<form>` e do atributo `href` em links `<a>` para criar a navegação entre as telas de login e cadastro sem JavaScript.

### Importação de fontes externas
Carregamento da fonte **Roboto** diretamente do Google Fonts via `<link>` no `<head>`, com uso de `font-display: swap` implícito pela URL gerada, melhorando a performance de carregamento.

### Reset de estilos com CSS global
Uso do seletor universal `*` para zerar `margin`, `padding` e `outline`, além de aplicar `box-sizing: border-box` globalmente — evitando comportamentos inesperados de dimensionamento em todos os elementos.

---

## ⚙️ Funcionalidades em Destaque

### 🔁 Redirecionamento via `<form action="">`
Na tela de cadastro, o atributo `action="login.html"` no `<form>` faz com que, ao submeter o formulário com o botão **"Criar conta"**, o navegador redirecione automaticamente para a tela de login — simulando o fluxo pós-cadastro sem uso de JavaScript.

```html
<form action="login.html">
  ...
  <button type="submit">Criar conta</button>
</form>
```

### 📐 Layout Split Screen com Flexbox
O container principal usa `display: flex` com `flex-direction: row` para dividir a tela em dois blocos iguais (`flex: 1` em cada `<main>`). O lado direito exibe o formulário sobre fundo branco, enquanto o lado esquerdo tem fundo azul (`#0056FB`) com conteúdo de marketing — um padrão amplamente usado em SaaS e plataformas de autenticação.

```css
.container_100 {
  width: 100%;
  height: 100dvh; /* altura dinâmica da viewport */
  display: flex;
  flex-direction: row;
}
```

### 📱 Unidade `dvh` (Dynamic Viewport Height)
Em vez de `100vh`, o projeto utiliza `100dvh` — uma unidade moderna que considera a altura real da viewport em dispositivos móveis, descontando barras de navegação do browser que aparecem e somem durante a rolagem.

### ✅ Checkbox de Termos
Na tela de cadastro, o checkbox "Concordo com os termos" está agrupado com seu texto em um container flexbox (`parte_de_baixo`), garantindo alinhamento vertical correto entre o input e o span sem uso de `label`.

```html
<div class="parte_de_baixo">
  <input type="checkbox">
  <span>Concordo com os termos</span>
</div>
```

---

## 🎨 Paleta de Cores

| Cor | Hex | Uso |
|---|---|---|
| Azul principal | `#0056FB` | Fundo esquerdo, botões |
| Preto suave | `#1C1C1C` | Bordas dos inputs |
| Branco | `#FFFFFF` | Fundo direito, texto nos botões |
| Escuro | `#2D2D2D` | Fill do SVG do logo |
