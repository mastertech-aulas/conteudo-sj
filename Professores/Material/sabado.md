# Material de Apoio - Sábado

### Objetivos
- Criar um entendimento fundamental de como funciona e quais tecnologias compõem a web moderna
- Noções práticas de uso de linguagens de marcação e estilização
- Capacidade de criar um site simples e publicá-lo
- Direcionar o aluno para continuar os estudos por conta

## Design Thinking (60min)

## Introdução à Web (30min)

### Redes e Protocolos
O que acontece quando acessamos o Google? Como é a interação entre os diversos sistemas desde o momento em que digitamos a URL no navegador até o momento que temos a página exibida em nossa tela?

Os computadores conseguem se comunicar porque estão interligados por redes - a ligação dessas redes umas às outras forma a Internet. Dentro da Internet, os computadores têm endereços específicos, que os identificam para a troca de dados, e mecanismos que permitem que a comunicação seja realizada de forma *transparente* ao usuário. Em informática, o conceito de transparente é o contrário do que podemos esperar: a Internet opera de forma transparente porque o usuário não vê nenhuma das etapas que acontecem até que os dados sejam acessados no seu computador.

No cenário de aplicações Web (essas com páginas que você abre usando o navegador do seu computador), os computadores que se comunicam podem assumir o papel de *cliente* ou de *servidor*. O servidor é o computador que está disponibilizando um serviço, como os computadores do Google, do Facebook, da Mastertech disponibilizam as páginas para acesso. O cliente é quem consome o serviço, ou seja, quem acessa essas páginas para mostrar ao usuário.

Para que cliente e servidor possam se comunicar de forma efetiva, é necessário que haja um *protocolo*. Um protocolo é um conjunto de regras e de formatos padronizados para os computadores se comunicarem. Um bom protocolo de comunicação define como e quando os computadores conversam entre si.
O principal protocolo usado para a troca de dados na Web é o HTTP - *Hyper Text Transfer Protocol*. Hiper-texto é o nome dado aos textos contendo imagens, sons, vídeos e estilos, que são os dados que compõem uma página da Web. O Hiper-texto que será trocado entre os computadores é construído utilizando três linguagens principais: HTML, CSS e JavaScript.

O HTML - *Hyper Text Markup Language* - é uma linguagem de marcação, e não de programação. Sua finalidade é determinar como os elementos da página serão estruturados, sua finalidade e conteúdo. Já o CSS - *Cascading StyleSheets* é uma linguagem de estilo para HTML, criada com a finalidade de organizar a formatação e o posicionamento dos itens definidos no HTML. O JavaScript é a linugagem de programação utilizada para criar interação dos itens com o usuário, realizar a primeira etapa de processamento dos dados da página e trocar dados pontuais com servidores durante a navegação.

> Dica: Esse é o momento em que o aluno sai de uma atividade criativa (design thinking) e entra num contexto de aula tradicional. É importante aproveitar esse momento e despertar o interesse dele no tema.


### Front End e Back End
Ao acessar o site pela primeira vez, seu computador faz o download do código do site que está disponível no servidor. O primeiro arquivo que é baixado é o HTML do site. O browser se encarrega de ler cada linha do HTML e interpreta o código para *renderizá-lo*, ou seja, transformá-lo em uma página visualmente agradável. Se ele encontra alguma referência a outro arquivo (um arquivo de CSS, ou uma imagem, por exemplo), o browser faz uma nova requisição ao servidor para baixar o arquivo que ele necessita. O código baixado e executado pelo computador é o front end, ou client-side.

> Mostrar a aba `Network` das ferramentas de desenvolvedor para ilustrar a explicação acima

Se o servidor precisa executar algum código antes de entregar ou montar os arquivos para o browser, esse código é o back end. Note que o browser não consegue ver ou acessar o código de backend, visto que ele é completamente executado pelo servidor e o resultado dessa execução são os arquivos entregues para o cliente. Dessa forma, um arquivo HTML pode ser gerado dinamicamente através de dados armazenados no banco de dados, por exemplo, ao invés de ser um arquivo convencional imutável.



### Semântica em código? 
Semântica dentro de HTML é a prática de dar significado ao conteúdo da página estruturando a mesma usando os elementos adequados, igual feito no português, inglês.... Código semântico descreve a importância do conteúdo de uma página, independentemente do estilo ou aparência do que conteúdo. Existem várias vantagens de se utilizar elementos semânticos, permitindo que computadores, leitores de tela, motores de busca e outros dispositivos de leitura compreendam adequadamente o conteúdo em uma página web. 

## HTML (30min)

O HTML é uma linguagem de marcação estruturada por *tags*. Cada tag de html corresponde a um elemento da página, com suas características e conteúdo.

O arquivo deve ser salvo com a extensão .html, e de preferência deve se chamar 'index.html'.

> O arquivo HTML pode ter qualquer nome, mas o padrão da maioria dos serviços é buscar 'index.html' como página inicial.

> O Visual Studio Code tem um autocomplete para html:5, que pode ser usado como o kickstart da aula. Algumas tags já vem construídas junto com a estrutura obrigatória.

As tags são identificadas por seus nomes no momento da abertura. Para abrir uma tag, inserimos seu nome entre '<' e '>'. O fechamento da tag é composto pelos sinais de '<' e '>', com o nome da tag precedido por '/'. O conteúdo de um elemento HTML fica entre a abertura e o fechamento.

A estrutura mínima obrigatória para um documento HTML está descrita abaixo. Todas as outras tags devem ser criadas dentro do elemento **head**, caso sejam metadados e informações, ou dentro do **body** se forem conteúdo efetivo da página.

```
<html>
    <head>
    </head>
    <body>
    <body>
</html>
```

As principais tags básicas usadas em HTML são (em ordem alfabética):

- **a** : A tag de âncora serve para criar ligação com outras páginas ou com elementos em uma mesma página, através de links clicáveis.
- **article** : Artigo.
- **aside** : Barra lateral. Importante: a barra não fica por padrão na lateral, deve ser formatada para isso. A tag só dá significado a uma divisão da página que deve ser uma barra lateral.
- **body** : O corpo da página. Dentro dele devem estar todos os elementos que compõem a estrutura de navegação.
- **button** : Um botão clicável.
- **code** : Identifica exemplos de código no conteúdo da página.
- **div** : Cria uma divisão, não-semântica, na página. Serve para agrupar e organizar os elementos.
- **footer** : O rodapé da página.
- **form** : Um formulário para entrada de dados do usuário que está navegando. Normalmente composto de texto em geral, **inputs** e **buttons**.
- **h1** até **h6** : Títulos e subtítulos. Os números de 1 a 6 definem os níveis, sendo 1 o título principal, externo, e 6 o subtítulo mais interno.
- **head** : A cabeça da página. Nela são colocados os *metadados* da página, ou seja, elementos que não fazem parte do conteúdo, mas definem configurações e informações sobre o documento.
- **header** : O cabeçalho da página. Importante: não confundir com **head**! O **header** fica dentro do **body**, definindo o cabeçalho visível da página.
- **html** : Tag principal do documento. Todas as outras tags devem estar organizadas dentro dela.
- **img** : Imagem. Precisa de um link para o arquivo de imagem e uma descrição.
- **input** : Caixa de entrada de dados do usuário.
- **li** : Item de lista. Deve estar dentro de uma lista do tipo **ol** ou **ul**.
- **link** : Herói do jogo Legend Of Zelda. Não, ele não se chama Zelda.
- **meta** : Metadados da página. Informações sobre o documento HTML que precisam ser passadas para o navegador.
- **nav** : Menu de navegação da página.
- **ol** : *Ordered list*: lista ordenada de elementos.
- **p** : Parágrafo de texto.
- **script** : Insere código de *scripts* de programação do lado do cliente na página. Normalmente, esse código é escrito em *JavaScript*.
- **section** : Seção da página, exceto cabeçalho e rodapé.
- **span** : Divisão similar a **div**, para organização sem semântica, mas dentro da própria linha de texto.
- **title** : Título da página que deve aparecer na janela do navegador.
- **ul** : *Unordered list*: lista não ordenada de elementos.

> Uma lista de todas as tags categorizadas por tipo de aplicação pode ser encontrada [no site da w3schools](https://www.w3schools.com/tags/ref_byfunc.asp).

Como exemplo, para criar uma seção na página com um título e dois parágrafos:

```
<html>
    <head>
    </head>
    <body>
        <section>
            <h2>Este é o título da seção<h2>
            <p>Aqui vai o texto do primeiro parágrafo.</p>
            <p>Aqui, por sua vez, vai o texto do segundo parágrafo.</p>
        </section>
    <body>
</html>
```

O recuo a partir da esquerda do código, chamado de endentação (ou indentação, ou identação), é importante para aumentar a legibilidade do código e descrever como os elementos se relacionam. No exemplo acima, a endentação ajuda a ver que o título e os parágrafos estão dentro da seção, que por sua vez está dentro do corpo da página.

> No Visual Studio Code é possível pressionar a tecla *f1* e digitar *Reindent Lines* para reorganizar todas as linhas de um arquivo de código.

Algumas tags não são identificadas somente pelo conteúdo. As tags podem ter *propriedades*, que as modificam sem alterar diretamente sua natureza. As propriedades são definidas na abertura da tag que identifica o elemento, com o nome da propriedade e um valor associado a ela, colocado entre aspas. Um exemplo é a tag de âncora (**a**), que possui a propriedade *href*, que aponta para onde o navegador deve seguir quando o link for acessado:

```
<a href="http://mastertech.tech">Clique para acessar a página da Mastertech!</a>
```

Existem tags cujas propriedades são suficientes para definir e construir a estrutura do elemento. Exemplos mais comuns são as tags de **img** e **input**. Essas tags não possuem conteúdo e, portanto, não possuem fechamento:

```
<img src="imagens/foo.png" alt="alguma imagem qualquer">
<input type="text" placeholder="Digite algo aqui">
```
> As tags **meta**, no início do template do Visual Studio Code, também são exemplos de tags sem fechamento.

> Versões anteriores do HTML exigiam que as tags sem fechamento usassem uma barra no final da tag, como em <img src="foo.jpg"/>. Essa forma não é mais necessária no HTML5 e geralmente não é recomendada.

> É importante abrir uma página, como github.com por exemplo, inspecionar os elementos usando as ferramentas de desenvolvedor para dar exemplos de como as tags são usadas e organizadas em um arquivo de HTML. Evite páginas muito complexas, como e-commerces ou o globoesporte, porque essas páginas são geradas com ferramentas e não costumam ter o HTML simples de interpretar.

O HTML é responsável somente pela criação dos itens na página. A formatação e o posicionamento desses itens é realizada através do *CSS*.

## CSS I - Formatação geral (45min)

A demanda por maiores recursos visuais nas páginas adicionou ao HTML tags de formatação e de posicionamento, tornando a especificação muito complexa e difícil de manter. O CSS foi criado para substituir essas tags. A utilização como padrão e as atualizações trouxeram uma gama enorme de opções de estilzação de elementos usando a linguagem.

> Existe mais de uma maneira de usar o CSS para estilizar uma página. É conveniente ensinar somente uma delas a princípio.

Para usar o CSS, um arquivo .css deve ser criado. Esse arquivo deve ser aplicado ao HTML através de uma ligação externa, utilizando a tag **link**, fazendo assim com que :
```
<link rel="stylesheet" href="css/styles.css">
```

No exemplo, 'styles.css' é o nome do arquivo, e ele se encontra dentro da pasta 'css'. A pasta 'css' está no mesmo local que o arquivo HTML.

> É importante lembrar que o caminho do arquivo deve partir da mesma pasta onde está o HTML.

### Blocos e seletores

A estrutura de um arquivo CSS é organizada em blocos, da seguinte forma:

```
seletor {
    propriedade-1: valor-1;
    propriedade-2: valor-2;
}
```

O *seletor* do bloco diz a quais elementos do HTML as propriedades devem ser aplicadas. As propriedades são as definições de estilo em si. Por exemplo, para que todas as **sections** tenham a fonte em vermelho, podemos aplicar:

```
section {
    color: red;
}
```

O seletor mostrado acima é um seletor de tag. Quando usamos o próprio nome da TAG para selecionar CSS, estamos aplicando o bloco de formatação a todos os elementos criados com a mesma tag no HTML. Por isso o exemplo acima formatará todas as **sections**.

No entanto, as vezes queremos formatar somente alguns elementos no HTML. Podemos fazer isso aplicando a eles propriedades de HTML chamadas *class* e *id*. Uma *class** é um conjunto de elementos que possuem características em comum. Já um *id* é usado para identificar unicamente um elemento. Observe o código HTML abaixo:

```
<body>
    <header>
        <h1>Título da Página</h1>
        <nav>
            <a>Link 1</a>
            <a>Link 2</a>
            <a>Link 3</a>
            <a>Link 4</a>
        </nav>
    </header>
    <aside>
        <h2>Título Lateral</h2>
        <nav>
            <a>Link Lateral 1</a>
            <a>Link Lateral 2</a>
        </nav>
        <p>Parágrafo 1</p>
        <p>Parágrafo 2</p>
    </aside>
    <section>
        <h2>Título da Seção<h2>
        <p>Parágrafo 3</p>
        <p>Parágrafo 4</p>
        <p>Parágrafo 5</p>
    </section>
</body>
```

Nessa página, os subtítulos **h2** precisam ter uma fonte diferente. Alguns links e parágrafos devem ter destaque, com um fundo azul, e o primeiro parágrafo da seção deve ter um tamanho de fonte maior. Para os subtítulos, podemos utilizar o seletor de tag. Para os itens em destaque, definiremos uma classe e chamaremos de 'destaque'. Para o parágrafo maior, criaremos um id e chamaremos de 'maior'.

> Vários elementos podem ser da mesma class, mas só um elemento pode ser identificado por um mesmo id.
> Um elemento pode ter várias classes, mas um elemento pode ter somente um id. Para que um elemento tenha várias classes, basta listá-las na propriedade class separando com espaço: `<div class="primeira segunda terceira"></div>`.

> Os nomes das classes e ids podem ser escolhidos à vontade, mas é sempre bom se ater ao significado que eles têm para a página.

```
<body>
    <header>
        <h1>Título da Página</h1>
        <nav>
            <a class="destaque">Link 1</a>
            <a class="destaque">Link 2</a>
            <a>Link 3</a>
            <a>Link 4</a>
        </nav>
    </header>
    <aside>
        <h2>Título Lateral</h2>
        <nav>
            <a class="destaque">Link Lateral 1</a>
            <a>Link Lateral 2</a>
        </nav>
        <p>Parágrafo 1</p>
        <p class="destaque">Parágrafo 2</p>
    </aside>
    <section>
        <h2>Título da Seção<h2>
        <p id="maior">Parágrafo 3</p>
        <p>Parágrafo 4</p>
        <p class="destaque">Parágrafo 5</p>
    </section>
</body>
```

Para cumprir as regras de formatação, usaremos seletores de class e de id no CSS. Um seletor de class começa com '.', seguido do nome da class. Um seletor de id começa com '#', seguido do nome do id.

```
h2 {
    font-family: sans-serif;
}

.destaque {
    background-color: blue;
}

#maior {
    font-size: 20pt;
}
```

Agora que sabemos como aplicar CSS aos elementos, é importante saber o que podemos alterar. Os links abaixo trazem várias propriedades de formatação e orientam sobre como usá-las. Se houver dificuldade com o inglês, o google tradutor é seu amigo:
- [Formatação de fontes](https://www.w3schools.com/css/css_font.asp)
- [Cores no geral](https://www.w3schools.com/css/css_colors.asp)
- [Planos de fundo](https://www.w3schools.com/css/css_background.asp)
- [Formatação de texto no geral](https://www.w3schools.com/css/css_text.asp)

#### Unidades de medida

As medidas de tamanho no CSS precisam de uma unidade definida. Algumas unidades são absolutas, ou seja, fazem com que os elementos tenham sempre o mesmo tamanho. Outras são relativas, dependendo de outros fatores para definir o seu tamanho. As principais unidades de medida de tamanho são:

| Unidade | Tipo | Descrição |
|---------|------|-----------|
| **mm** | Absoluta | Medida exata em milímetros. Normalmente não usada por ser muito restritiva. |
| **pt** | Absoluta | Pontos. Normalmente usada em fontes, por ser o padrão da maioria dos editores de texto. |
| **px** | Absoluta | Quantidade de pixels. Medida mais comum para o box model. Apesar de ser absoluta, pode variar com a resolução da tela. |
| **%**  | Relativa | Porcentagem do tamanho disponível para o elemento no documento. |
| **vw** | Relativa | Porcentagem da largura total da parte visível da tela. |
| **vh** | Relativa | Porcentagem da altura total da parte visível da tela. |

### Margin e Padding

Margin - É a margem do elemento, ou seja, o espaçamento externo do elemento.

Padding - É o preenchimento do elemento, ou seja, o espaçamento interno do elemento.

![diferenças](https://i.stack.imgur.com/zLQiz.png)


### O Box Model

Para definir o tamanho de um elemento no CSS precisamos primeiro conhecer o *Box Model*, ou *Modelo de Caixa*. A caixa de um elemento tem quatro camadas:
- Conteúdo: É a área onde fica o texto ou imagem do elemento.
- Padding: É o espaçamento existente entre o conteúdo e a borda do elemento, definindo sua área útil. É normalmente usado para fazer com que o elemento ocupe mais espaço no total, ou simplesmente para afastar a borda do conteúdo.
- Border: É a borda que limita o elemento.
- Margin: É o espaçamento externo à borda do elemento. É normalmente usada para afastar os elementos uns dos outros.

> É possivel mostrar a organização do box model com essas camadas acessando as ferramentas do desenvolvedor, aba 'elements' e opção 'styles'.

Para definir o tamanho do conteúdo, basta usar as propriedades *width* e *height* com as unidades de medida desejadas.

Os tamanhos da borda, padding e margin podem ser definidos pelas propriedades de mesmo nome. Podem ser definidos tanto individualmente, usando -*top*, -*bottom*, -*left* e -*right* como sufixo da propriedade do box model, como todos de uma vez, usando somente o nome da propriedade e colocando os valores. Ex:

- **border-top: 5px**: formata somente a borda superior com 5px de espessura.
- **padding: 10px**: formata os paddings dos quatro lados para 10px.
- **margin: 30px 50px**: formata as margens superior e inferior com 30px e as margens esquerda e direita com 50px.
- **padding: 10px 20px 30px**: formata o padding superior com 10px, os laterais com 20px e o inferior com 30px.
- **margin: 10px 0 30px 40px**: formata a margem superior com 10px, a margem direita com 0 (desnecessária a unidade de medida para zero), a margem inferior com 30px e a margem esquerda com 40px.

Para as bordas, é possível definir uma cor, com *border-color*. A cor do padding é a mesma *background-color* do conteúdo do elemento].

> Exceto pelo conteúdo, é comum que as medidas da caixa sejam definidas em **px**.

## CSS II - Posicionamento e responsividade (60min)

Display
- display: inline : permite posicionar os elementos um do lado do outro. Uma
desvantagem é que os elementos não aceitam que sejam modificadas as
propriedades width e height.

- block : permite os elementos se posicionarem um do lado do outro
porém, diferentemente do display: inline ele permite que os elementos tenham
sua width e height modificadas. Uma desvantagem de usar display: inline-block é
espaçar os elementos entre si. Para fazer isso temos que colocar margin.

- float : O float empurra o elemento para um dos lados (left | right) e os
elementos que estão em baixo sobem. Pode ser uma alternativa para posicionar 2
elementos como <div> uma ao lado da outra.

- display: flex : Ele permite os elementos ficarem um do lado do outro, permite
espaçar os elementos de forma mais intuitiva. Além disso ele também permite alinhar
os elementos verticalmente de forma fácil. O display flex pode ser um pouco mais
complicado de usar porém é bom enfatizar que é uma ótimo alternativo para criação de layouts responsivos.

- [Exemplos de display flex](https://imasters.com.br/css/adeus-flexbox-bem-vindo-css-grid-layout)

Position

- Static: valor default de todo elemento HTML, ou seja, ele vai seguir o fluxo comum da sua página.

- Relative: A posição do elemento é relativa ao elemento anterior. Ou seja, na posição inicial do elemento, inserido no próprio html, é possível alterar sua posição com as propriedades Top, Bottom, Left e Right...e sua base inicial é a sua primeira posição.

- Absolute: A posição do elemento é relativa ao viewport, ou ao elemento pai quando este tem um position definido. Esta posição é influenciada pela rolagem da página.

- Fixed: A posição do elemento é relativa ao viewport igual ao absolute porém não é influenciada pela rolagem da página. Um exemplo bom, é de algumas <nav> que são utilizadas a posição fixed para se manter no topo da tela e o restante do site rodar por trás.

> Para um layout responsivo usar % para determinar o posicionamento. Se for um layout estático, use PX mesmo. Lembrando que % é um unidade de medida dinâmica, ou seja, o elemento com posicionamento por porcentagem vai variar de acordo com seu elemento pai.

- [exemplo de position] (http://pt-br.learnlayout.com/position.html)

Exemplo:

```
<div id="elemento_pai">
   <div id="elemento_filho"></div>
</div>

```
#elemento_pai {
    width:100%; height:100%
    }
#elemento_filho {
    width:50%; height:100%; margin-left:50%
    }
```

MediaQuery

São expressões de CSS utilizadas para mudar o layout em diferentes dispositivos sem mudar o conteúdo. E como usar em seu CSS? Em resumo os atributos seriam como um tutorial do que você precisa que aconteça em um determinado dispositivo.

Um bom conceito para que seja compreendido é associar como se você perguntasse para o browser: “ O seu dispositivo é uma tela e a largura máxima é 320 pixels?”. Se a resposta for sim o navegador aplica o que consta no seu arquivo css.

320 pixels – Smartphones no modo retrato.
480 pixels – Smartphones no modo paisagem.
600 pixels – Tablets pequenos. Ex: Amazon Kindle (600×800)
768 pixels – Tablets maiores em modo retrato. Ex: iPad (768×1024)
1024 pixels – Tablets maiores em modo paisagem, monitores antigos.
1200 pixels – Monitores

```
./* regra aplicada em todo código */
body { background: blue; }

/* aplica somente a partir de 320px */
@media screen and (min-width: 320px) {
body { font-size: 80%; }
}

/* aplica somente a partir de 480px em landscape */
@media screen and (min-width: 480px) and (orientation: landscape) {
nav { float: left; }
}
```

####Exemplos para aula

Como montar um menu de navegação:

Estrutura HTML
```
<html>
<body>
    <header>
        <nav id="menu">
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">Sobre</a></li>
            <li><a href="#">Equipe</a></li>
            <li><a href="#">Contato</a></li>
        </ul>
        </nav>
         <h1>Título da Página</h1>
</body>
</html>

```
Estrutura CSS

#menu ul li{
    display: inline;
}

#menu ul li a {
    color: blue;
    padding: 10px;
    text-decoration: none;
    border: 2px solid black;
    margin-left: 10px;
}
```

       

## Publicação (45min)

### Noções de Terminal
O terminal nada mais é que outra forma de interagir com o computador. Estamos habituados a utilizar uma interface gráfica composta de janelas e ícones para realizar as tarefas que necessitamos no dia-a-dia, como abrir um editor de texto, salvar um arquivo ou acessar uma página da internet.

Essas mesmas atividades podem ser realizadas unicamente através de comandos no terminal. Ainda que esse método possua uma maior curva de aprendizado, ele possibilita uma flexibilidade e agilidade muito grande, de forma que ele se torna uma ferramenta de trabalho diário da maioria dos programadores.

```
windows: procure por *cmd* no menu iniciar  
macos: procure por *terminal* no Spotlight
```

| Comando | Descrição |
|---------|-----------|
| cd | muda de diretório |
| dir (windows) | lista os arquivos do diretório atual |
| ls (mac/linux) | lista os arquivos do diretório atual |

### Firebase
O Firebase é um serviço cloud do Google que permite, entre outras coisas, a hospedagem gratuita de sites. Vamos utilizá-lo para publicar os trabalhos que realizarmos no curso. Para isso, precisamos de três coisas: uma conta no Google, um projeto criado no Firebase e o programa de terminal do Firebase instalado em nosso computador (Firebase CLI).

#### #1 Como instalar o Firebase CLI
O pré-requisito para instalar o Firebase CLI é possuir o NodeJS instalado no computador. O NodeJS é um ambiente de execução de Javascript para terminal, e pode ser baixado através do site [https://nodejs.org].

Após a instalação do NodeJS, basta abrir o terminal e usar o comando:
`npm install -g firebase-cli` (windows)
`sudo npm install -g firebase-cli` (macos/linux)

#### #2 Como criar um novo projeto no Firebase
1- Acessar o Firebase através de uma conta do Google em [https://firebase.google.com/]
2- Clicar em *Go to Console*
3- Clicar em *Add Project*
4- Digitar o nome para seu projeto e aceitar os termos de serviço
5- Clicar em *Create Project*

#### #3 Como publicar um site no Firebase
1- Abrir o terminal
2- Copie o caminho da pasta através do gerenciador de arquivos
3- Digite `cd caminho/para/pasta` no terminal e pressione enter
4- Digite `firebase init` e pressione enter
5- Na lista apresentada, escolha a opção *Hosting* com a barra de espaços e pressione enter
6- Selecione o projeto que você criou anteriormente Firebase e pressione enter
7- *What do you want to use as your public directory?* Digite `.` e pressione enter
8- *Configure as a single-page app (rewrite all urls to /index.html)?* Digite `n` e pressione enter
9- O menu interativo irá encerrar. Digite o comando `firebase deploy` e pressione enter

No final irá aparecer o 2 links de acesso, onde o segundo será possível ver seu site online.