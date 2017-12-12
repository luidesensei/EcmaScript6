# EcmaScript6
Exemplos praticos das melhorias de ES6 na programação 
## O que é
O ECMAScript é a especificação da linguagem de script que o JavaScript implementa. Isto é, a descrição de uma linguagem de script, sendo padronizado pela Ecma International — associação criada em 1961 dedicada à padronização de sistemas de informação e comunicação — na especificação ECMA-262. Mas se não ficou satisfeito com a definição de forma resumida podemos dizer que :  
ECMAScript 6(ES6) ou ES2015, é simplesmente a mais nova versão do JavaScript. 
## ECMAScript x JavaScript x ES
Depois desta explicação algumas pessoas devem ficar com uma dúvida bem comum é o porquê dessa mudança do nome.
Na verdade não houve nenhuma mudança: JavaScript é como nós chamamos a linguagem, só que esse nome é um trademark da Oracle (que veio após a compra da Sun). O nome oficial da linguagem é ECMAScript. E ES é simplesmente uma abreviação do mesmo.
## Objetivos do ES6
O TC39* focou em alguns objetivos no desenvolvimento do ES6:
- Ser uma linguagem melhor para construir aplicações complexas
- Resolver problemas antigos do JavaScript
- Facilidade no desenvolvimento de libraries

Esses objetivos ficarão mais claros quando olharmos na prática as features do ES6.

> Obs: * É o comitê formado por especialistas de grandes companhias da área de tecnologia, tais como: Apple, Google, Microsoft e Mozilla. Este comitê se reúne a cada dois meses, normalmente na Califórnia, para discutir o futuro da especificação.

## Quais as novidades do ES6

Agora que já sabemos o que é o ES6 , podemos então ver as features* que ele adicionará na linguagem e seus benefícios.
Vamos ver exemplos de:
- 1 Declaração de variáveis - let e const
- 2 Métodos Auxiliares
- 3 Iteradores e Iteráveis
- 4 for … of | for … in
- 5 Novas estruturas de dados
- 6 Template Strings
- 7 Arrow Functions
- 8 Melhorias em objetos literais
- 9 Valores Padrões
- 10 Operadores Rest e Spread
- 11 Desestruturamento
- 12 Classes
- 13 Módulos
- 14 Funções Geradoras
- 15 Promises

De agora em diante vou apenas expor os exemplos não irei entrar em explicações teórica sobre o assunto, caso queira isto só entrar nos links abaixo.

- "1": https://medium.com/@matheusml/o-guia-do-es6-tudo-que-voc%C3%AA-precisa-saber-8c287876325f
- "2": https://www.casadocodigo.com.br/products/livro-ecmascript6

>* “Uma nova funcionalidade ou uma nova característica”

#  1 Declaração de variáveis - let e const
Usaremos o const nas variáveis que não esperamos que mudem de valor com o decorrer do tempo/execução do programa dentro de um escopo. Se tentarmos atribuir um outro valor para a variável, vai ocorrer um erro

## const
```javascript

const codigo = 1334543543

console.log(codigo)

```
## let 
Podemos considerar o let como o verdadeiro substituto do var. Idealmente ele deve ser usado para declarar variáveis que esperamos que mudem com o valor e com o tempo/execução do programa. Entretanto, ao contrário do que acontecia com o var, se uma mesma variável, dentro de um mesmo escopo, é declarada duas vezes, tomamos erro de sintaxe. Isso acontece tanto para o let quanto para o const.

A sua principal diferença em relação ao var, é que o var tem escopo de função, enquanto os novos tipos tem escopo de bloco.

```javascript



```

