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

## Javascript (1 hora)

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

Não podemos redeclarar uma variável, pois isso gera um erro de execução. Para alterar o valor de uma variável já, basta utilizar o operador **=** sem a necessida da palavra **let**

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
| array  | armazena diversos valores organizados por posição|

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

**TODO: Incluir exemplos de exercícios**
**TODO: Conversão de valores**

### Condicionais

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

> Apresentar o comando alert como uma forma de exibir os valores no browser.
