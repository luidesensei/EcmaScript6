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

let finalSemana = ['sábado','Domingo']
console.log(finalSemana[0])
finalSemana.push('sexta-feira')
console.dir(finalSemana)

```
> Saída no console

sábado
[ 'sábado', 'Domingo', 'sexta-feira' ]


# Métodos Auxiliares
Os métodos auxiliares nos permite iterar um array de forma muito mais clara e simples. Vamos ver os 5 que existe: forEach, map, filter, find, every, some e o reduce. Sendo que cada um tem uma função bem específica. Abaixo, segue um exemplo de como utilizá-los:

## forEach

Utilizamos para quando precisamos passar por todos os nossos itens de um Array. 

Exemplo: exibir todos os seus itens no console.

```javascript
var nomes = ['fulano','sicrano','beltrano']

nomes.push('jose')

nomes.forEach(function (nome){
  console.log(nome)
})

```
>Saída no console  fulano sicrano beltrano jose

## map

Usado para quando precisamos não somente passar por todos os itens, mas fazer algo com eles. 

Exemplo: dobrar todos os valores.

```javascript

var numeros = [1,2,3,4,5]
var dobro = numeros.map(function(numero){
    return numero * 2
});
 
console.log(dobro)

```
> Saída no console  [ 2, 4, 6, 8, 10 ]

## filter

Ótima para filtrar itens da nossa lista. 

Exemplo: listar somente os números pares.

```javascript
var numeros = [1,2,3,4,5]
var pares = numeros.filter(function(numero){
    return numero % 2 === 0
})
 
console.log(pares)

```
> Saída no console  [ 2, 4]

## find

Se estiver procurando um item da lista, utilize o find. Lembrando que ele só devolve apenas a primeira ocorrência do item que bate com a condição da busca. 

Exemplo: encontrar o número dois.

```javascript

var numeros = [1,2,3,4,5]
var valor = numeros.find(function(numero){
    return numero == 2
})
 
console.log(valor) 

```
>Saída do console 2

## every
Essa função é excelente para quando precisamos validar se todos os itens da lista atendem a um critério em comum.

Exemplo: validar se todos os valores são menores que 10

```javascript
var numeros = [1,2,3,4,5]
var todosMenoresQueDez = numeros.every(function(numero){
    return numero < 10
})
 
console.log(todosMenoresQueDez)

```
> Saída do console  true


## some
Esta função valida se há pelo menos um item que atende a um critério.

Exemplo: validar se há algum número três na lista

```javascript 
var numeros = [1,2,3,4,5]
var peloMenosUmNumeroTres = numeros.some(function(numero){
    return numero === 3
})
 
console.log(peloMenosUmNumeroTres)
```
> true

## reduce

O reduce faz a redução dos itens de um array.

Exemplo: calcular a soma de todos os itens da lista

```javascript
    var numeros = [1,2,3,4,5]
    var soma = numeros.reduce(function(soma,numero){
        return soma + numero
    },0)
     
    console.log(soma) 
```
>15

#  Iteradores e Iteráveis

A iteração é definida por dois conceitos centrais: iteradores e iteráveis.

Definimos como um iterador um objeto que sabe como acessar, um a um, os itens de um iterável, enquanto mantém o status da sua posição atual na estrutura. Esses objetos oferecem o método next, que retorna o próximo item da estrutura do iterável sempre que invocado. Um objeto é definido como iterável se ele define explicitamente o seu comportamento de iteração. Para isso, é necessário que ele implemente o seu iterador na propriedade de chave Symbol.iterator. No JavaScript, alguns tipos já são iteráveis por padrão:

    Arrays
    Strings
    Maps
    Sets

Para cada vez que chamamos o método next, ele nos retorna um objeto com duas propriedades: value e done. A primeira contém o valor armazenado na estrutura que foi recuperado. A segunda é um booleano que nos diz se todos os itens da estrutura foram acessados.

Apesar de não ser a melhor maneira de utilizá-lo, podemos acessar o iterator da estrutura diretamente para utilizá-lo no código.

Exemplo: recuperar o nome de cada um 

```javascript

var funcaoSeletor = function (pessoa){
  var cargos = ['analista','programador','gerente de projeto','BDA']
  var cargo = cargos[Math.floor(Math.random()*cargos.length)]
  
  console.log(`Nome ${pessoa} | Cargo: ${cargo} `)
  
}

var pessoas = ['Fulano', 'Sicrano', 'Beltrano']

//Vamos escolher os cargos das pessoas
var iterador = pessoas[Symbol.iterator]()
var done = false
var proximo = iterador.next()

do{
  var pessoa = proximo.value
  funcaoSeletor(pessoa)
  proximo = iterador.next()
  
}while(!proximo.done)

```
> Exemplo de saída do console  Nome Fulano | Cargo: analista 
Nome Sicrano | Cargo: BDA 
Nome Beltrano | Cargo: gerente de projeto 
=> { value: undefined, done: true }

# for ... of

É um laço de repetição: o laço for...of.  Este tipo de laço foi criado para percorrer um objeto se, e somente se, ele for iterável. Seu funcionamento é bem simples. Sua sintaxe é:

```javascript

    for (variavel of iteravel) {
      // corpo
    }

```
A variavel representa uma variável de auxílio que assume valores diferentes a cada iteração, e o iteravel é o objeto que será iterado. O caso de uso mais recorrente deste tipo de laço é para passar por todos os valores contidos em um Array, Set ou um Map. 

Sua utilização é muito simples.

Exemplo: iterar uma lista de números

```javascript
    var numeros = [1,2,3,4,5]
    for(var numero of numeros) {
      console.log(numero)
    }

```

E assim como em outros laços de repetição, o break e o continue também funcionam dentro de laços for...of. Usamos o break para interromper a execução de um laço.

Exemplo: Interrromper se houver um número maior que 3


```javascript
    var numeros = [1,2,3,4,5]
for(var numero of numeros) {
  if(numero > 3) {
    break
  }
  console.log(numero)
}

/*
sáida do console
1
2
3
*/

```
Já o continue usamos para indicar que o laço deve ser continuado, passando imediatamente para o próximo item. 

Exemplo: Colocar uma condição no laço para nunca imprimir no console o número dois

```javascript
var numeros = [1,2,3,4,5]
    for(var numero of numeros) {
      if(numero === 2) {
        continue
      }
      console.log(numero)
    }
    // 1 3 4 5
```
> Obs:Este exemplo veio do material do curso de ECMAScript6 do professor Diego Martins de Pinho. Dica caso queira se aprofundar no assunto super indicado seu curso da platafoma Udemy.

# Set

O Set é uma estrutura de dados que nos permite ter listas com valores que nunca se duplicam e que mantém a ordem de inserção dos seus itens. Sua utilização também é muito simples. Seus principais métodos são: add, delete, clear e o has.

```javascript
    var set = new Set()
    set.add(1) // adiciona um item
    set.has(1) // verifica se o item já foi inserido
    set.delete(1) // deleta
    set.clear() // remove todos os itens

```
E como o Set também é um objeto iterável, podemos usar o for...of nele:

```javascript
    var set = new Set([1,2,3,4,5]) // inicializando o set no construtor
     
    for (const valor of set) {
        console.log(valor)    // 1 2 3 4 5
    }

```
# Template Strings

O ES6 trouxe o conceito de Template Strings. Há dois tipos:

* Template strings simples;
* Template strings marcardos (tags).

Esses Templates são estruturas que nos permite formar expressões com strings usando funcionalidades como interpolação e multilinhas. 


## Template strings simples

Para utilizar, basta utilizarmos as crases (`) ao invés das aspas (simples ou duplas). Com ela, podemos inserir diretamente o valor de variáveis dentro de uma string e manter a sua formação sem fazer uso de escapes, como neste exemplo: 

```javascript
const n1 = 1, n2 = 2
console.log(`${n1} + ${n2} = ${n1 + n2}`)
// 1 + 2 = 3
```
Para interpolar os valores, utilizamos as chaves ({}). Qualquer expressão que é jogada lá dentro é resolvida e então inserida dentro da string, como fizemos neste exemplo.

## Template strings marcadas

Ao marcar uma Template String, conseguimos modificar seus valores com uma função. Como neste exemplo:

```javascript

function soma(n1,n2) {
  let resultado = `${n1} + ${n2} = ${n1+n2}`;
  console.log(resultado);
}

soma(1,2)

//1 + 2 = 3

```

# Arrow Functions


Com o ES6, nós ganhamos mais uma maneira de declarar funções: através das Arrow Functions (em tradução livre, seria algo como "funções de seta"). Esta estrutura é uma notação simplificada criada para facilitar a implementação de funções por expressão no JavaScript. A definição de uma Arrow Function é bem simples e segue esta ordem:

    Parâmetros dentro de parênteses (...);
    Fat arrow (=>);
    Corpo da função entre chaves ({...}).

Veja a sintaxe:

```javascript
    (param1, param2 …, param n) => {
        // corpo da função
    }
```

Esta nova notação possui duas vantagens em relação a antiga maneira de declararmos expressões de função.

São menos verbosas: Arrow Functions nos permite escrever funções menos verbosas. Veja como podemos tornar o código mais enxuto:

```javascript
    // ES5
    var boasVindas = function(nome) {
        return "Seja bem-vindo, " + nome;
    }
     
    // ES6
    const boasVindas = nome => `Seja bem-vindo, ${nome}`;
    boasVindas("Luiz"); // Seja bem-vindo, Luiz
 ```

O contexto de execução é diferente: Sempre que executamos uma função no JavaScript, ela é associada a um contexto de execução. Esse contexto possui uma propriedade denominada ThisBinding, que pode ser acessada a qualquer momento através da palavra reservada this. O valor do this, que chamamos de contexto da função, é constante e existe enquanto este contexto de execução existir. As Arrow Functions foram projetadas para conseguirmos capturar o this do seu contexto delimitador (chamamos isso de escopo léxico da função), como no exemplo a seguir:

```javascript
    const equipe = {
      nome: 'Soldados x',
      membros: ['Cicrano', 'Beltrano', 'Fulano'],
      membrosDaEquipe: function() {
        this.membros.forEach(membro => {
          console.log(`${membro} é da equipe ${this.nome}`);
        })
      }
    }
     equipe.membrosDaEquipe()
```

Ao executar o equipe.membrosDaEquipe novamente, continuamos tendo a saída esperada:

```javascript
  Cicrano é da equipe Soldados x
  Beltrano é da equipe Soldados x
  Fulano é da equipe Soldados x
  ```

Como as Arrow Functions conseguem fazer a associação (bind) do this de forma automática, referenciar o this do contexto da execução delimitadora para o escopo da atual função deixou de ser um problema.

