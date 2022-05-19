# Responsividade

Reposítorio destinado a aula da [Rocketseat](https://www.rocketseat.com.br) sobre Responsividade na Prática, ministrada pelo Mayk Brito. O foco principal da aula é mostrar as melhores estratégias de se aplicar a responsividade no layout para que ele fique fluído.

## O que é responsividade? :thinking:

Responsividade é a capacidade que um site possuí para fazer com que os elementos se adapatem com o tamanho da tela do usuário. Dessa forma, não importa qual dispositivo será utilizado, pois o layout será visualizado da melhor forma possível para encontrar o que deseja, mantendo uma navegação simples e intuitiva.

**Algumas vantagens de um site responsivo são as seguintes:**

- Aumento de Vendas
- Influência no SEO
- Diminuição da taxa de rejeição
- Aceleração do tempo de carregamento das páginas
- Compatibilidade com novos dispositivos

## CSS Units - Unidades de medidas do CSS

**Layout Fixo**

- `px` - Pixels

**Layout Fluido**

- `%` - Porcentagem
- `auto` - Automática => ex: height se adapta a altura do texto
- `vh` - Viewport Height
- `vw` - Viewport Width

**Textos Fixos**

- `1px` = 0.75pt
- `16px` = 12pt

**Textos Fluidos**

- `em` - multiplicado pelo elemento pai
- `rem` - multiplicado pelo root => html tem o padrão de `16px` = 1rem

## CSS Media Queries

Servem para delimitar e ajustar o conteúdo

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

```css
@media (max-width: 768px) {
  /* de 0 até 768px */
  span {
    color: red;
  }
  /* Dessa forma, a estilização aqui dentro só será aplicada em até no máximo 768px */
}
```

## HTML Media Attributes

Também posso definir um arquivo que so vai cuidar das estilizações até um certo tamanho

```html
<link
  rel="stylesheet"
  href="./responsive.css"
  media="screen and (max-width: 768px)"
/>
```

```css
html {
  font-size: 50%;
}
```

## Imagens

O uso das imagens é algo de grande impacto em um site e o desenvolvedor deve ter cuidado com o consumo de memória, pois elas podem ser muito grandes.

Como auxilio existe as tags <picture> e <source> que servem para que as imagens sejam responsivas. Juntas elas vão permitir que o navegador escolha a imagem mais adequada para o layout de acordo com o breakpoint passado na própria tag, funciona da seguinte forma:

```html
<picture class="imagem" alt="Imagem">
  <source
    media="(min-width: 768px)"
    srcset="https://i.ytimg.com/vi/GykTLqODQuU/maxresdefault.jpg"
  />
  <source
    media="(min-width: 320px)"
    srcset="https://i.ytimg.com/vi/GykTLqODQuU/hqdefault.jpg"
  />
  <source
    media="(min-width: 10px)"
    srcset="https://i.ytimg.com/vi/GykTLqODQuU/mqqdefault.jpg"
  />
</picture>
```

## Diferença - jpg, png x svg

No formato jpg e png são imagens com número fixo de pixels, isso faz com que a imagem não possa ser ampliada sem ocorrer distorção.

No formato svg as imagens são feitas de forma vetorial, ou seja, mesmo que a tela seja ampliada ou dimensionada, não afeta a qualidade e o formato.

![Png vs Svg](/images/svg-and-jpg.png)
