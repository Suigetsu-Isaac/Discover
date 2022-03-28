# CSS

## Cascading

  O **cascading**, ou cascata é como o css trabalha
  graças a isso o código css funciona de cima para baixo, de tal forma que o ultimo elemento da cascata
  terá prioridade acima dos demais.

## Especifidade

  Especificidade é a ideia de que quanto mais especifico for o elemento maior a importancia dele, sobrescrevendo o modelo de cascading se for preciso

## HSL

  O **HSL** é um formato de cor, tal como rgb e hexadecimal, Ela trabalha da seguinte maneira,

  O **H** representa a cor, ao qual vai do <font color='red'>vermelho </font> até ele proprio, seguindo uma circufêrencia de 360º, tambem temos
  
  O **S** que representa o porcentual de saturação da cor, seria a "força" da cor, e por fim temos
  
  O **L** que representa o percentual de luz da cor, sendo 0% equivalente a nenhuma luz ou seja a cor Preta, e 100% a toda a luz ou seja a cor Branca.

## Box Model

  Todo seletor é uma caixa, ao qual temos a `margin`, que envolve a `border`, que envolve o `padding` que por sua vez envolve o **elemento**.
  
  o **border-box** ultiliza ultiliza o conceito de medir a largura e altura do elemento apartir da borda. Pois por padrão o navegador mede apartir do padding.

## REM

  **REM** é uma unidade de medida relativa, ela pega a medida do `font-size` do root, e apartir dela faz suas métricas, por exemplo se tivemos `height: 2rem`, siginifica dizer que a altura corresponde a 2 * o `font-size` da pagina. Esse tipo de medida é bom para que haja responsividade na criação da página web.

## Position

  Quando aplicamos o position habilitamos os seguintes elementos
  **top,bottom,left,right**: a posição do elemento,
  **z-index**: a profundidade do elemento
  Quando aplicamos o position o elemento fica em uma camada diferente do original, em vez de ficar acima dos demais elementos ele fica ou a frente ou atrás.
  Existe 3 tipos de position: `Fixed`, `Absolute`, `Relative`

  **Fixed**: Nela o objeto fica fixo na tela, mesmo quando você abaixa até não o vê ele irá o acompanhar.

  **Relative**: o objeto tem uma posição relativa a pagina.

  **Absolute**: o objeto tem uma posição absoluta a página.

  Quando ultilizamos o absolute ele irá ter uma posição absoluta referente a toda pagina a menos que o elemento pai tenha uma posição relativa, se isso acontecer ele irá de forma absoluta apenas dentro deste elemento.

## Overflow

  o Overflow é uma propriedade do css que responde ao que acontece quando excede o tamanho do conteudo, isso faz com que tenhamos aquela barra lateral, caso não queira que isso ocorra basta aplicar a propriedade hidden `overflow: hidden`.

## :root

  É o Elemento raiz do css, nele contem as funcionalidades padrão dos navegadores, e se você quiser pode modifica-las, nela é onde geralmente guardamos as variáveis do css.

  variáveis é como em qualquer linguagem de programação guardando uma informação que será resgatada depois.
  esses valores geralmento são cores, ou tamanhos de algo na pagina
  `:root { --color: #cdcdcd }`
  
  note que eu guardei a cor no elemento _--color_, se eu quiser resgatar ele valor basta eu ultilizar a propridade **var()** do css
  `h1 {background-color: var(--color)}`, o resultado será a cor correspondete a #cdcdcd .

## :hover

  É um subElemento ao qual aplicamos uma funcionalidade quando o usuario colocar o mouse sobre o elemento
  `h1:hover{background-color: #fff}`, se seguirmos o a ideia anterior o `h1` tem a cor de fundo de `#cdcdcd`, caso colequemos o mouse sobre ele ele ficara com a cor de fundo de `#fff`,
  
  caso queira que essa mudança seja aplicado de uma forma mais suave basta aplicar a propridade `transition`, nela você coloca o elemento e a duração que ele irá realiza entre o original e o hover, `transition: background-color 0.3s`, ou seja, em uma duração de 300 milesimo ou 0.3 segundos faça uma transição de cinza -> `#cdcdcd` para o branco -> `#fff`

## ::before

  É um pseudoElemento criado pelo css, o before cria um elemento antes do selecionado, precisamos explicitar qual será o seu conteudo, tamanho e tudo mais.
  `h1::before {content:"",width: 100px,height: 100px}`
  nesse exemplo ele tem um conteudo vazio e altura e largura de 100px, e irá ser criado antes do h1.
  
  Geralmente ultiliza-se o `::before` em conjunto com o position como o absolute assim criamos um elemento absoluto antes do elemento.

## Display

  o display é como o elemento irá ser mostrado na pagina,
  temos diversos tipos de display como o block, inline, grid e flex
  
  **Grid**: O grid ele faz com que o elemento e seus filhos trabalhem em formato de grid,ou seja de forma horizontal e vertical, que tem diversas funcionalidades uma delas é o gap que faz com que o espacamento entre os elementos seje conforme explicitado
  `div {display: grid; gap: 2rem;}`

  **Flex**: O flex trabalha com a ideia de flex-box, enquanto o grid trabalha nas formas horizontais e verticais o flex só trabalha com uma direção, contudo podemos ainda ter o dominio da parte lateral e vertical do elemento
  
  <details> <summary><b>Funcionalidades do Flex</b></summary>
      
      Flex-Start
        coloca o conteúdo no começo da pagina
       
      Flex-End
        coloca o conteúdo ao Final da pagina
      
      Center
        Centraliza o conteúdo ao meio
      
      Space-Between
        Faz com que os elementos fiquem um extremidade do outro
    
  </details>

  O Flex tambem trabalha com dois eixos de manipulação o `justify-content` que corresponde ao eixo principal e o `align-item` que corresponde ao eixo secundário, por padrão o flex trabalha de forma horizontal - linha, caso queira mudar esse elemento basta aplicar a propriedade `flex-direction: column` que ele irá trabalhar na forma de coluna - vertical.

  **Inline**: o inline é como o seletores de texto geralmente trabalham como o `<span>` e o `<a>`, nele a altura e a largura são do tamanho de texto.

  **Block**: É o oposto do inline nele o conteudo é tratado como bloco sendo assim ele ocupara a largura e altura referente ao selecionado pelo programado.

  Tambem temos propridades que junta essas ideias como por exemplo o Inline-Flex.

  **Inline-Flex**: ele Junta os elementos do inline e do flex, assim podemos deixa ou a altura fixa do inline ou mudar com o flex, alem de tambem incorporar as funcionalidades do flex 