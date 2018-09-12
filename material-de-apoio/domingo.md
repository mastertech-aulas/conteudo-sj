# Material de Apoio - Domingo

### Objetivos

## Introdução a programação e a Lógica

### O que é um algoritmo
Um algoritmo é uma sequência de passos para realizar uma tarefa. Essa sequência deve ser *correta*, *completa* e *clara*.

A ideia de sequência é que os passos do algoritmo tem ordem para serem executados, e essa ordem deve ser preservada.

*Correta* significa que a sequência de passos deve, com certeza, atingir o objetivo. Um algoritmo é considerado correto se, após o último passo ser executado, chega-se ao resultado esperado.

*Completa* significa que a sequência não deve ter nenhum passo faltando. Todas as informações e instruções para chegar ao objetivo devem estar no passo-a-passo. Quem lê e executa os passos não deve ter que "inferir" nenhum passo, nem preencher nenhuma lacuna.

*Clara* significa que não pode haver ambiguidade em nenhum dos passos. As informações e instruções devem estar descritas de uma maneira que não gerem dúvidas: a natureza das informações deve ser específica e não pode haver duas maneiras distintas de executar uma instrução. Além disso, quem lê ou executa o algoritmo deve chegar ao resultado fazendo exatamente o que a sequência de passos define.

> Normalmente, quando aprendemos sobre algoritmo, os exemplos dizem que é como uma "receita de bolo". Isso definitivamente não é verdade! A analogia é utilizada porque as receitas possuem um "modo de fazer" sequencial, orientado por passos, mas algumas considerações precisam ser feitas.
Primeiro, as receitas não são claras: não existe padrão para as quantidades dos ingredientes. Uma xícara de chá não tem uma medida exata, assim como uma colher de sopa cheia não significa uma porção exata. Duas pessoas diferentes podem seguir a mesma receita com o material que possuem em casa e as quantidades não serão as mesmas. Além disso, passos como "bata as claras em neve" deixam ambiguidades: como? com qual instrumento? o que define "em neve"?
Segundo, as receitas não são completas: instruções como "pré-aqueça o forno" não traz todas as informações necessárias. Por quanto tempo deve-se pré-aquecer o forno? A qual temperatura?
Por fim, as receitas não são corretas pois existe um risco de seguir todos os passos, exatamente como descrito, na sequência, e não chegar ao resultado esperado.

### Níveis de Abstração

Para escrever um programa, é necessário utilizar uma linguagem que, ao mesmo tempo, seja compreendida pelo computador e pelo programador. Para que seja entendida pelo computador, essa linguagem necessita ter uma sintaxe precisa e instruções claras. Para que seja entendida pelo programador, é importante que ela tenha relação com a linguagem humana e seja de fácil compreensão.

Por isso, as linguagens de programação possuem diferentes níveis de abstração, ou seja, o quão detalhadas são as instruções em relação as operações básicas que um computador pode realizar.

Considere um algoritmo que ensina a trocar um pneu de um carro. Uma sequência de instruções como "pegue a chave de roda", "remova os parafusos da roda", "puxe a roda até que ela saia" parece suficiente. Entretanto, só seria útil para quem saber o que é uma chave de roda, e para quem sabe remover um parafuso.

Algumas pessoas precisariam de instruções mais exatas, como "encaixe a extremidade hexagonal da chave de roda no parafuso", "enquanto o parafuso não sair, gire a chave de roda no sentido anti-horário para desrosquear o parafuso".

O primeiro algoritmo possui um maior nível de abstração em relação ao segundo algoritmo. Em um contexto computacional, uma linguagem de baixo nível necessita de instruções específicas de alocação do espaço de memória e algumas chamadas do sistema operacional para exibir um texto na tela. Por outro lado, ao usar uma linguagem de alto nível, o programador necessita apenas usar um simples comando de impressão.

```
;Hello World em Assembly

section     .text
global      _start                              ;must be declared for linker (ld)

_start:                                         ;tell linker entry point

    mov     edx,len                             ;message length
    mov     ecx,msg                             ;message to write
    mov     ebx,1                               ;file descriptor (stdout)
    mov     eax,4                               ;system call number (sys_write)
    int     0x80                                ;call kernel

    mov     eax,1                               ;system call number (sys_exit)
    int     0x80                                ;call kernel

section     .data

msg     db  'Hello, world!',0xa                 ;our dear string
len     equ $ - msg                             ;length of our dear string
```

```
# Hello World em Python

print('Hello World')
```

### Compilação x Interpretação
Ainda que uma linguagem de programação seja um meio intermediário entre o programador e o computador, ela em seu estado original não é adequada para as operações de baixo nível do sistema. Para que ela possa ser utilizada, é necessário converter o código escrito pelo programador em linguagem de máquina. Esse processo pode ser feito de duas formas distintas: compilação ou interpretação.

No processo de compilação, o código-fonte é convertido um arquivo executável que contém as instruções de baixo nível necessárias para execução do programa pelo computador. Note que não existe um processo simples para "descompilar" o programa, de modo que ter o arquivo executável não nos dá acesso ao código-fonte. Os programas usados em desktop normalmente são compilados.

No processo de interpretação, o código-fonte é convertido em instruções para o computador em tempo real. Isso permite um maior dinamismo para o programador enquanto ele trabalha, visto que ele pode ver de forma imediata as mudanças que ele faz no programa. Por outro lado, a velocidade de execução do programa tende a ser menor, visto que a cada execução é necessário fazer a conversão do código novamente para instruções de máquina. Vale notar que não existe um arquivo executável, então o programa é distribuído no formato de código-fonte.

## Javascript

O Javascript é a linguagem padrão para as páginas da web. É com ele que são implementados desde sites institucionais até sistemas complexos como o Google Drive. O browser possui dentro de si um interpretador da linguagem, que é responsável por executar os scripts presentes nas páginas.

> Iniciar os primeiros comandos dentro do console do browser, para que o aluno possa ver seu resultado em tempo real. Explicar que o console se trata de uma forma interativa de executar comandos de Javascript e é usado para testes, mas que não corresponde à realidade de desenvolvimento do dia-a-dia de um programador web.

### Variáveis
Ao programar, temos a possibilidade de armazenar valores na memória do programa e realizar operações com eles. Para isso, fazemos o uso de variáveis, que são espaços de memória que armazenam valores.

As variáveis são criadas utilizando a palavra chave **let**. O nome da variável é definido livremente pelo programador, desde que algumas regras sejam seguidas:

- Não pode conter caracteres especiais, como acentos, cedilhas ou til
- Não pode conter espaços
- Não pode começar com um número, mas pode conter números em outras posições

```
let salario;
```

Para armazenar um valor em uma variável, usamos o operador **=**.

```
let salario = 1000;
```

No caso do Javascript, a memória é individual para cada página, de forma que duas páginas exibidas em abas diferentes não compartilham valores de memória. Ao recarregar a página, limpa-se a memória e reinicia-se qualquer script que esteja presente na página.

Não podemos redeclarar uma variável, pois isso gera um erro de execução. Para alterar o valor de uma variável já, basta utilizar o operador **=** sem a necessidade da palavra **let**.

```
salario = 2000;
```

Perceba que toda linha é finalizada com um ponto-e-vírgula, que indica que a instrução finalizou.

> Finalizar instruções com ponto-e-vírgula é um requisito do Javascript, ainda que este possua um mecanismo que permita que ele tenha um certo nível de tolerâncias à essa omissão.

### Tipos e Operações

No Javascript, o tipo da variável é definido pelo valor que esta atribuído a ela naquele momento. Os seguintes tipos estão presentes nas linguagem:

| TIPO    | DESCRIÇÃO  |
| --------|----------- |
| number  | valores numéricos, inteiro ou decimal |
| string  | texto |
| boolean | verdadeiro ou falso|
| object  | armazena diversos valores organizados em pares de chave e valor|
| *array  | armazena diversos valores organizados por posição|

> Array não é tecnicamente um tipo de variável, visto que o Javascript o identifica simplesmente como `object`. Porém, incluímos array nessa tabela por motivos didáticos.
> Apesar de citarmos os objetos e vetores entre os tipos de variável, sugerimos que eles não sejam exemplificados nem aprofundados nesse momento da aula.

O tipo de uma variável é importante pois ele determina o resultado de operações realizadas com ela, além de funcionalidades disponíveis. Podemos por exemplo, somar duas variáveis numéricas e obter o resultado da conta, porém se somamos duas variáveis do tipo *string*, o resultado é a união dos dois valores, o que é chamado de *concatenação*.

```
1 + 1 //resutado é 2
'1' + '1' //resultado é 11
```
Os seguintes operadores estão disponíveis em Javascript:

#### Operadores aritméticos
| Operador | Descrição |
|----------|---------- |
| = | atribui um valor à uma variável |
| + | adição ou concatenação, no caso de strings |
| - | subtração |
| * | multiplicação |
| / | divisão |
| ** | potenciação |
| ++ | incremento |
| - - | decremento |


Note que para armazenar o resultado de uma operação em uma variável, é necessário a utilização do operador **=**. Realizar a operação não altera o valor da variável por si.

```
let salario = 1000;
let aumento = 500;

salario + aumento; //resultado é descartado
salario = salario + aumento; //o resultado é armazenado na variável salário
```

#### Criando arquivos .js

Os scripts de uma página são geralmente escritos em arquivos separados com a extensão **.js**. Para que a página carregue esse script é necessário inserir dentro do seu HTML a seguinte tag:

`<script src="scripts.js" defer></script>`

É recomendável que essa tag seja inserida no **head** da página. Note a palavra **defer** na abertura da tag, que indica que o script só deve ser executado quando todo o restante da página já tiver sido carregado.

> Utilize esse momento para propor alguns exercícios simples com operações. Para isso, faça uso das funções *alert* para exibir os valores e *prompt* para obter valores do usuário.

### Conversão de valores
Muitas vezes é necessário converter o tipo de uma variável para utilizá-la de forma correta no contexto do que estamos programando. A função *prompt*, por exemplo, sempre retorna uma variável do tipo **string**, mesmo que o usuário tenha inserido um valor numérico. A tentativa de somar variáveis que foram obtidas pelo método prompt vai resultar na concatenação dos valores.

```
let idade = prompt('Digite sua idade'); //o usuário digitou 11 no popup

let idadeRelativa = idade + 20;

alert(idadeRelativa); //o resultado é 1120
```

Para converter tipos de variável, o Javascript possui as seguintes funções:

| Função | Descrição |
|--------|-----------|
| Number | Converte o valor em **number** |
| String | Converte o valor em **string** |
| Boolean | Converte o valor em **boolean** |

```
let idadeString = prompt('Digite sua idade'); //o usuário digitou 11 no popup
let idade = Number(idadeString); //converte a string em number

let idadeRelativa = idade + 20;

alert(idadeRelativa); //o resultado é 31
```

> Note que ao tentar converter um valor não numérico em Number, o resultado será *NaN*, que significa *Not a Number*. Podemos verificar se uma variável é NaN usando a função **isNaN**

### Condicionais

Uma das capacidades presentes em todas as linguagens de programação é a capacidade de criar algoritmos para tomadas de decisão. A estrutura mais simples para definir o fluxo do programa de acordo à um valor é o **if**.

```
let palavra = prompt('Fale, amigo, e entre.');

if(palavra == 'mellon'){
  alert('Você pode passar!');
}
```   

No caso acima, o alert só será executado caso o valor da variável *palavra* seja igual a `mellon`. Veja que o operador **==** realiza a comparação dos dois valores, e retorna um valor booleano: *true* ou *false*.

Podemos também definir instruções que sejam executadas caso a condição lógica resulte em *false*:

```
let resposta = prompt('Qual a resposta para a vida, o universo e tudo mais?');

if(resposta == '42'){
  alert('Você está correto!');
}else{
  alert('Você errou...');
}
```  

Nesse caso, o alert com o texto *Você errou...* será executado toda vez que o valor inserido pelo usuário **seja diferente** de '42'.

#### Operadores Lógicos
Toda operação lógica resulta em um valor booleano, ou seja, `true` ou `false`;
| Operador | Descrição |
|----------|---------- |
| == | igual |
| != | diferente |
| ! | negação |
| > | maior |
| < | menor |
| >= | maior ou igual |
| <= | menor ou igual |

## Javascript - DOM

O DOM (Document Object Model) é uma interface de programação que representa os elementos de uma página como nodos em uma estrutura de árvore.

```
html
|
--- head
|
--- body
   |
   --- header
   |  |
   |  --- h1
   |
   --- section
   |  |
   |  --- div
   |     |
   |     --- p
   |
   --- footer
```

Cada um desses nodos é um objeto de Javascript que contém todas as propriedades possíveis para este elemento, como suas propriedades de CSS, o texto contido dentro da tag, seu id, etc.

### Manipulando o DOM com Javascript

A forma mais simples de acessar um nodo no Javascript é através de uma função disponível dentro do objeto global **document** chamada de **querySelector**:

> O uso dos métodos getElementById, getElementsByClassName e getElementsByTagName é desencorajado atualmente, e eles são mantidos apenas por propósito de compatibilidade

```
let meuBotao = document.querySelector('button');
```

Nesse exemplo, será selecionado o primeiro elemento que possua a tag button na página, visto que a função querySelector seleciona um único elemento, ignorando os elementos subsequentes.

> A função **querySelectorAll** retorna um vetor de elementos baseado no seletor usado. No entanto, não aconselhamos que ela seja mostrada nesse momento da aula para mantê-la simples.

Depois de selecionado, a referência para o elemento ficou contida na variável **meuBotao**. Para alterar alguma de suas propriedades dinamicamente, podemos usar:

```
meuBotao.innerHTML = 'Novo texto para o botão';
meuBotao.style.color = 'white';
```

Note que as propriedades de CSS são representadas como *string* por uma necessidade do Javascript. No exemplo, a palavra 'white' seria interpretada como uma variável com o mesmo nome caso ela não fosse escrita entre aspas.

Uma limitacao do Javascript é que as variáveis não podem conter hífens em seu nome. Portanto, diversas propriedades de CSS tiveram seu nome alterado para o padrão *camel-case* quando acessadas pelo Javascript:

```
meuBotao.style.backgroundColor = 'white';
meuBotao.style.fontWeight = 'bold';
meuBotao.style.fontSize = '30px';
```

### Eventos do browser

Apesar de eficazes, os exemplos anteriores causam a alteração dos elementos da página imediatamente após seu carregamento. Isso causa no usuário a impressão de que os elementos foram definidos da forma em que eles foram apresentados, removendo a necessidade de fazer sua manipulação via Javascript.

No entanto, quando atribuímos as alterações de um elemento à um evento do browser, como um click ou um mouseover por exemplo, podemos entender a verdadeira necessidade de manipular elementos da página com o Javascript.

```
let meuBotao = document.querySelector('button');

function alterarCorDoBotao(){
    meuBotao.style.backgroundColor = 'blue';
}

meuBotao.onclick = alterarCorDoBotao;
```

Note que **não** devemos utilizar os parênteses no final do nome da função no momento de atribuí-la ao evento. Os parênteses causam a execução imediata da função, e ao evento é atribuído apenas o valor de retorno da função (que não existe no exemplo acima).

> Recomendamos que os eventos sejam atribuídos via Javascript ao invés de dentro do HTML visto que os alunos tendem a esquecer de atualizar o código de HTML, já que ele tem que trabalhar com dois arquivos diferentes para finalizar uma funcionalidade.

Esses são alguns exemplos de eventos que podemos utilizar:

| Evento | Descrição |
| ------ | --------- |
| onclick | clique do mouse |
| onmouseenter | quando o ponteiro entra no elemento |
| onmousemove | quando o ponteiro se movimenta dentro do elemento |
| onmouseleave | quando o ponteiro sai do elemento |
| onkeydown | quando o elemento tem foco e alguma tecla é pressionada|
| onkeydown | o elemento tem foco e quando alguma tecla é solta após ser pressionada |


## Aplicativos Mobile

### Opção 1: Aplicativos Nativos
Essa é a forma padrão para programar uma app mobile. Como as plataformas possuem kits de desenvolvimento diferentes, é necessário criar duas versões do aplicativo, uma para Android e outra para iOS.

**Vantagens:** maior performance e flexibilidade de uso de recursos plataforma.
**Desvantagens:** maior custo e tempo de desenvolvimento, manutenção de duas bases de código.

### Opção 2: Aplicativos Nativos com base de código compartilhada
Para resolver o problema de manter duas bases de código, surgiram frameworks que unificam o fluxo de desenvolvimento e, a partir de um único código fonte, compila-se duas versões do aplicativo. O Xamarin da Microsoft e o React Native do Facebook são exemplos dessa abordagem.

**Vantagens:** maior agilidade no desenvolvimento e alteração de apps
**Desvantagens:** menor flexibilidade para uso de recursos nativos, ainda é necessário fazer ajustes específicos por plataforma

### Opção 3: Aplicativos Híbridos
Essa abordagem emprega o uso de tecnologias web para criar a interface do aplicativo, ou  seja, o aplicativo em realidade é um "site" que é instalado no celular através de uma camada de código nativa. Para usar recursos nativos do celular (GPS, acelerômetro, giroscópio, push notification), o Javascript tem acesso a uma interface de programação que faz a ponte entre o código web e o nativo. O Cordova e o Ionic são os exemplos mais famosos de plataformas para desenvolvimento de apps híbridos.

**Vantagens:** é uma das formas mais rápidas e baratas para desenvolvimento de apps, um programador web pode reutilizar seus conhecimentos de HTML, CSS e JS
**Desvantagens:** menor performance e maior quantidade de limitações em relação a apps puramente nativos

### Opção 4: PWA
O PWA (Progressive Web Apps) é uma opção relativamente nova para o desenvolvimento de aplicações mobile. Ela consiste em uma aplicação puramente web que pode ser instalada no celular diretamente do browser, mantendo funcionalidades offline e com um ícone para acesso disponível na gaveta de aplicativos. As novas versões dos sistemas iOS e Android suportam os PWAs, o que tem aumentado significativamente sua popularidade.

**Vantagens:** é uma das formas mais rápidas e baratas para desenvolvimento de apps, um programador web pode reutilizar seus conhecimentos de HTML, CSS e JS
**Desvantagens:** menor performance e maior quantidade de limitações em relação a apps puramente nativos

> Quer identificar um PWA? Basta utilizar o Lighthouse. Trata-se de uma extensão do Google Chrome produzida pelo próprio Google que faz diversos testes com a página, como testes de cache offline ou com uma conexão de internet ruim, responsividade em diferentes resoluções, tempo de carregamento, meta informações, etc.

## Como criar um PWA
Para ser identificado corretamente como um PWA, um site precisa atender alguns requisitos:

1- Possuir um manifest.json, que fornece metadados sobre a instalação ao app
2- Possuir um service-worker, que faz o cache de informações para acesso offline
3- Ser servido em conexão criptografada (HTTPS)
4- Ser responsivo, possuir tempo rápido de carregamento e funcionar nos principais browsers

> Para ver essa lista com detalhes, visite a página oficial do Google em https://developers.google.com/web/progressive-web-apps/checklist

> Utilizar como base para a criação dos PWAs o código disponível em https://github.com/mastertech-aulas/pwa-base

### O manifest.json

O arquivo manifest.json deve ser criado na pasta raiz do site e deve ser referenciado no head da página da seguinte forma:

```
<link rel="manifest" href="/manifest.json">
```

Este é um exemplo do conteúdo do arquivo com as propriedades mais comuns:
```
{
  "name": "Meu App",
  "short_name": "MApp",
  "icons": [
    {
      "src": "img/icon-192.png",
      "sizes": "192x192",
      "type": "image/png"
    },
    {
      "src": "img/icon-512.png",
      "sizes": "512x512",
      "type": "image/png"
    }
  ],
  "start_url": "/index.html",
  "display": "fullscreen",
  "background_color": "#3E4EB8",
  "theme_color": "#2F3BA2"
}
```

**name**: O nome completo do app.

**short_name**: O nome que é efetivamente utilizado abaixo do ícone do app, após instalado.

**icons**: Ícone para o app. O exemplo mostra dois tamanhos padrão para o ícone, porém não são os únicos tamanhos disponíveis. Note que cada arquivo de imagem deve conter exatamente a resolução em pixels descrita.

**start_url**: Arquivo de HTML que é utilizado como página principal da aplicação.

**display**: Determina o comportamento do app após instalado no celular.
- *fullscreen* exibe o app em tela cheia, sem a barra de navegação do browser e a barra de status do sistema operacional do celular
- *standalone* exibe o app de forma similar à outros apps nativos
- *browser* exibe o app dentro do browser, similar à um website

**background_color**: Cor de fundo da aplicação enquanto o CSS não é carregado. Afeta a *splash screen* no Android, que é a tela de carregamento inicial de um app.

**theme_color**: Cor do tema do app. Afeta características diversas, como a cor da barra de status na parte superior do sistema Android.

### O service-worker

O service worker é essencialmente um arquivo de Javascript que funciona de forma independente à página e tem a tarefa de interceptar requisições para a web e fazer o cache de informações para o funcionamento offline da aplicação.

Vamos utilizar um modelo padrão de service-worker que faz o cache de todos os arquivos estáticos do site (folhas de estilo, scripts, imagens, etc):

```
let cacheName = 'meu-app-cache-v1';
let filesToCache = [
    '/',
    '/index.html',
    '/main.js',
    '/main.css'
];

self.addEventListener('install', function(event) {
    console.log('[ServiceWorker] Install');
    event.waitUntil(
        caches.open(cacheName).then(function(cache) {
            console.log('[ServiceWorker] Caching app shell');
            return cache.addAll(filesToCache);
        })
    );
});

self.addEventListener('fetch', function(event) {
    console.log('[Service Worker] Fetch', event.request.url);    
    event.respondWith(
        caches.match(event.request).then(function(response) {
            return response || fetch(event.request);
        })
    );
});

self.addEventListener('activate', function(event) {
    console.log('[ServiceWorker] Activate');
    event.waitUntil(
        caches.keys().then(function(keyList) {
            return Promise.all(keyList.map(function(key) {
                if (key !== cacheName) {
                    console.log('[ServiceWorker] Removing old cache', key);
                    return caches.delete(key);
                }
            }));
        })
    );
});
```

É importante adicionar qualquer arquivo que deve estar disponível offline dentro do vetor **filesToCache**. Cuidado ao manipular essa variável, pois a adição de qualquer arquivo inexistente irá gerar um erro que impede o funcionamento do service-worker.

O service-worker deve então ser referenciado dentro de um script que está vinculado à página, visto que não há forma de referenciá-lo diretamente do HTML. O seguinte código registra o service-worker em browsers compatíveis:

```
if ('serviceWorker' in navigator) {
    navigator.serviceWorker
    .register('./service-worker.js')
    .then(function() {
        console.log('Service Worker Registered');
    }, function(error){
        console.error(error);
    });
}
```
