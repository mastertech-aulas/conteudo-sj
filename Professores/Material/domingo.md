# Material de Apoio - Domingo

### Objetivos

## Introdução a programação e a Lógica

### O que é um algoritmo
Um algoritmo é uma sequência de passos para realizar uma tarefa. Essa sequência deve ser correta, completa e clara.

A ideia de sequência é que os passos do algoritmo tem ordem para serem executados, e essa ordem deve ser preservada.

Correta significa que a sequência de passos deve, com certeza, atingir o objetivo. Um algoritmo é considerado correto se, após o último passo ser executado, chega-se ao resultado esperado.

Completa significa que a sequência não deve ter nenhum passo faltando. Todas as informações e instruções para chegar ao objetivo devem estar no passo-a-passo. Quem lê e executa os passos não deve ter que "inferir" nenhum passo, nem preencher nenhuma lacuna.

Clara significa que não pode haver ambiguidade em nenhum dos passos. As informações e instruções devem estar descritas de uma maneira que não gerem dúvidas: a natureza das informações deve ser específica e não pode haver duas maneiras distintas de executar uma instrução. Além disso, quem lê ou executa o algoritmo deve chegar ao resultado fazendo exatamente o que a sequência de passos define.

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


## Javascript (1 hora)
