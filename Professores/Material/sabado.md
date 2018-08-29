# Material de Apoio - Sábado

### Objetivos
- Criar um entendimento fundamental de como funciona e quais tecnologias compõe a web moderna
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

## HTML
É importante primeiro mostrar abertura e fechamento da tag de HTML - *div*, *p* e *h1-h6* são bons exemplos. Daí, já mostrar nas ferramentas de desenvolvedor uma página que tenha tags *p* ou *h1*, como o próprio github.com.

Depois falar de tags que tem propriedades necessárias, como a tag *a* com o href. Dizer que uma propriedade está lá para configurar alguma característica da tag.

Depois falar de tags que não fecham, que são compostas somente pelas propriedades. O melhor exemplo é a tag *img*, e as tags *meta* de configuração do head do template padrão do visual studio.

Com essa base, fechar a lista das principais tags - incluindo *form*, *input* e *button*, sempre mostrando exemplos usando as ferramentas de desenvolvedor, com páginas prontas.

Evite páginas muito complexas, como e-commerces ou o globoesporte, porque essas páginas são geradas com ferramentas e não costumam ter o HTML simples de interpretar.

## CSS I - Formatação geral

## CSS II - Posicionamento e responsividade

## Publicação