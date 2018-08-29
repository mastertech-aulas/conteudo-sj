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

>>> Mostrar a aba `Network` das ferramentas de desenvolvedor para ilustrar a explicação acima

Se o servidor precisa executar algum código antes de entregar ou montar os arquivos para o browser, esse código é o back end. Note que o browser não consegue ver ou acessar o código de backend, visto que ele é completamente executado pelo servidor e o resultado dessa execução são os arquivos entregues para o cliente. Dessa forma, um arquivo HTML pode ser gerado dinamicamente através de dados armazenados no banco de dados, por exemplo, ao invés de ser um arquivo convencional imutável.

## HTML (30min)

O HTML é uma linguagem de marcação estruturada por *tags*. Cada tag de html corresponde a um elemento da página, com suas características e conteúdo.

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

> No Visual Studio Code é possível usar a combinação *ctrl + shift + p* e digitar *Reindent Lines* para reorganizar todas as linhas de um arquivo de código.


Algumas tags não são identificadas somente pelo conteúdo. As tags podem ter *propriedades*, que as modificam sem alterar diretamente sua natureza. As propriedades são definidas na abertura da tag que identifica o elemento, com o nome da propriedade e um valor associado a ela, colocado entre aspas. Um exemplo é a tag de âncora (**a**), que possui a propriedade *href*, que aponta para onde o navegador deve seguir quando o link for acessado:

```
<a href="http://mastertech.tech">Clique para acessar a página da Mastertech!</a>
```

Existem tags cujas propriedades são suficientes para definir e construir a estrutura do elemento. Exemplos mais comuns são as tags de **img** e **input**. Essas tags não possuem conteúdo e, portanto, não possuem fechamento:

```
<img src="imagens/foo.png" alt="alguma imagem qualquer">
<input type="text" placeholder="Digite algo aqui">
```

> Na realidade, algumas ferramentas exigem que as tags sem conteúdo sejam fechadas, usando uma barra no final da tag, como em <img src="foo.jpg">

> As tags **meta**, no início do template do Visual Studio Code, também são exemplos de tags sem fechamento.

> É importante abrir uma página, como github.com por exemplo, inspecionar os elementos usando as ferramentas de desenvolvedor para dar exemplos de como as tags são usadas e organizadas em um arquivo de HTML. Evite páginas muito complexas, como e-commerces ou o globoesporte, porque essas páginas são geradas com ferramentas e não costumam ter o HTML simples de interpretar.

O HTML é responsável somente pela criação dos itens na página. A formatação e o posicionamento desses itens é realizada através do *CSS*.

## CSS I - Formatação geral (45min)

## CSS II - Posicionamento e responsividade (60min)

## Publicação (45min)