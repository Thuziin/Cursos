# JavaScript

## Client x Server:

JS é uma tecnologia que é focada no lado do cliente (mas pode ser usada no lado do servidor também)
Aplicações com JS:

	+ Google
	+ Youtube
	+ Linkedin
	+ Netflix
	+ Facebook
	

JavaScript surge em 1995;

ECMAScript padroniza o JS em 1997

Tecnologias que surgiram:

	+ JQuery (biblioteca)
	+ Angular (FrameWork)
	+ React (Biblioteca do Facebook)
	+ Vue (FrameWork)
	+ Electron (FrameWork)
	+ Ionic
	+ Cordova

<h4>Bibliografia:</h4>

+ JavaScript: o guia definitivo

+ JavaScript: guia do programador

+ [Documentação Mozilla](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide)

+ [Documentção Ecma](https://www.ecma-international.org/publications-and-standards/standards/ecma-262/)

<em>OBS: Para acessar o node eu acesso o meu terminal (nativo ou no vscode) e digito 'node'. Para sair digito '.exit'</em>


## Fundamentos

As váriaveis podem ter três tipos de declarações distintas:

	var nomeVar (permite redeclaração);
	let nomeLet (não perimite redeclaração);
	const nomeConst (não permite alteração de valores);
	
JS é um linguagem fracamente tipada, ou seja, uma mesma variável pode receber diretentes tipos de dados:

```JS
let teste = 'olá'
teste = 1
```

Assim como nas demais linguagem JS possui tipo de dados básicos:

`Number:`

```JS
const peso = 1;
const peso1 = Number('2.0')
```

`String:`

```JS
const nome = "Arthur";
nome.charAt(3);
nome.substirng(0,3)
```

`Boolean:`

```JS
let isAtivo = true;
isAtivo = false;
console.log(!!isAtivo)
```

`Template Strings: `

```JS
const nome = 'Layla'
const concatenar = 'Ola' + nome + '!'
const template = `Olá ${nome} !`
console.log(`1 + 1 = ${nome}`)
```

`Arrays`

Em JS os Arrays tem a cabacidade de amarzenar informação que possuem várias tipos de dados, ou seja, são capazes de armazenar dados heterogênios.

```JS
const valores = [0, 1, 2, 3]
valores[4] // undefined
valores.push({id: 3}, true, 'olá', null)
valores.pop()
delete valores[0]
```

`NULL e Undefined`

Embora não seja recorrente e indicado, em JS é possível inicializar variáveis com `null` e com o `undefined`

```JS
let valor // não inicializada
console.log(valor) // Undefined
console.log(valor1) // Is not defined
valor = null // ausencia de valor
console.log(valor) // null
```

## Manipulação de dados:

O sinal de `mais(+)` pode servir tanto para concatenar como para adição, o que vai variar é o contexto que ta sendo utilizado

```JS
Number.parseInt(VARIAVEL) // converte para int
Number.parseFloat(VARIAVEL) // converte para float
Number(VARIAVEL) // converte para um número, o JS verifica a melhor escolha
```

			
Assim como é possível converter uma *String* para *Number*, é possível fazer o caminho inverso também:

```JS
String(VARIAVEL)
VARIAVEL.toString()
```

A string possui bibliotecas que permitem manipulá-las e realizar:

	Contagem
	UpperCase
	LowerCase
	//...

Assim como as strings posso formatar de acordo com a minha necessidade os números também:

```JS
var salary = 1500.5
salary.toFixed(2)
salary.ToFixed(2).replace('.',',')
salary.toLocaleString('pt-BR', {style: 'currency', currency: 'BRL'})

```
				
### Operadores:

`Aritmeticos:`

	▸ mais (+)
	▸ menos (-)
	▸ multiplicação (*)
	▸ divisão (/)
	▸ módulo (%)
	▸ potência (**)

`Atribuição:`

	▸ var n = 3;
	▸ n = n + 4 // n += 4
	▸ n = n - 2 // n -= 2
	▸ n = n * 2 // n *= 2
	▸ n = n / 2 // n/= 2
	▸ n = n ** 2 // n **= 2
	▸ n = n % 10  // n %= 10
	▸ n = n += 1 // n++ ou ++n
	▸ n = n - 1 // n-- ou --n

`Relacionais:`

	▸ maior que (>)
	▸ menor que (<)
	▸ maior ou igual (>=)
	▸ menor ou igual (<=)
	▸ igual (==) // JS não teste o tipo de dado (5 == '5')
		- 5 === '5' (false)
	▸ diferente (!=)

<em>obs: Sempre gera um resultado booleano como resultado da comparação!</em>

`Lógicos:`

	▸ ! (negação)
	▸ && (conjução/e)
	▸ || (disjunção)
				
`Ternários:`

	▸ ? : 
	teste ? true : false
    
	media >= 7 ? 'Aprovado' : 'Fica pra proxima'

	var n = 8
	var resultado = n % 2 == 0 ? 5 : 9

## Funções

Função são escopos separados que realizam determinada atividade programada pelo o usuário, por terem escopos próprios às vezes é necessário passar parâmetros para que sejam capazes de lidar com dados e afins. Em JS podemos ter funções de várias formas, como por exemplo:

`Função sem retorno:`

```JS			
function imprimeSoma(a, b) {
	console.log(a + b)
}
```

`Função com retorno:`

```JS
function soma (a, b = 1) {
	return a + b
}
```

<em>obs: b recebe um valor padrão para o caso de seu valor não ter sido passado por parametro</em>

`Função anonima:`

```JS
const imprimirSoma = function (a, b) { 
	console.log(a + b)
}
```

`Arrow function:`

```JS
const soma = () => {
	console.log(a + b)
}
```

`Com retorno implicito:`

```JS
const subtracao = (a,b) => a - b
```

Como dito, funções possuem escopos, isso faz com que uma função declarada no escopo *global* tenha acesso as váriaveis presente neste escopo *global*.

Se eu tiver uma função <em>PAI</em>, e dentro dela uma função <em>FILHA</em>, a função <em>FILHA
</em> terá acesso a todas as váriaveis do *PAI*, que por sua vez terá acesso as todas variáveis do *global*, no entanto o contrário não é valido.


### Função Recursiva

Uma função recursiva é aquele onde a função chama ela mesma. EM JS ela pode referir a si mesma de três formas:

	▸ function name
	▸ arguments.callee()
	▸ variavel no escopo que se refere a função (foo())
        var foo = function bar () {
			foo ()
		}

### Closure:

Closure é um escopo criado quando uma função é declarada. Esse escopo permite a função acessar e manipular variáveis externas à função:

```JS
const x = 'Global'
function fora () {
	const x = 'Local'
	function dentro () {
	return x
	}
	return dentro
}
const minhaFuncao = fora()
console.log(minhaFuncao()) // Mostra 'Local' no console
```

### Callback:

É uma função passada como parametro de uma outra função, que será invocada dentro de uma função externa para completar uma ação/rotina. Ex:

`Sem callback:`

```JS
function myDisplayer (some) {
	document.getElementById("demo").innerHTML = some;
}

function myCalculator(num1, num2) {
	let sum = num1 + num2;
	myDisplayer(sum);
}

myCalculator(5, 5);

```	

`Com callback:`

```JS
function myDisplayer(some) {
	document.getElementById("demo").innerHTML = some;
}

function myCalculator(num1, num2, myCallback) {
	let sum = num1 + num2;
	myCallback(sum);
}

myCalculator(5, 5, myDisplayer);
```

`Outro exemplo:`
```JS
// Create an Array
const myNumbers = [4, 1, -20, -7, 5, 9, -6];

// Call removeNeg with a callback
const posNumbers = removeNeg(myNumbers, (x) => x >= 0);

// Display Result
document.getElementById("demo").innerHTML = posNumbers;

// Keep only positive numbers
function removeNeg(numbers, callback) {
	const myArray = [];
	for (const x of numbers) {
		if (callback(x)) {
			myArray.push(x);
		}
	}
	return myArray;
}
```

## Objetos

Objetos são coleção de dados e/ou funcionalidades (propriedades e métodos) relacionados. 
Como a maioria das coisas em JS, para criarmos um objeto precisamos inicializar uma variável. Ex:

``` JS
var pessoa = {}
console.log(typeof(pessoa))
```

Veremos que ao printarmos o tipo de pessoa teremos como retorno `[objecto Object]`

No exemplo acima criamos um objeto vazio, a seguir veremos uma forma de criar o objeto de forma literal

```JS
var pessoa = {
  nome: ["Bob", "Smith"],
  idade: 32,
  sexo: "masculino",
  interesses: ["música", "esquiar"],
  bio: function () {
    console.log(
      this.nome[0] +
        " " +
        this.nome[1] +
        " tem " +
        this.idade +
        " anos de idade. Ele gosta de " +
        this.interesses[0] +
        " e " +
        this.interesses[1] +
        ".",
    );
  },
  saudacao: function () {
    console.log("Oi! Eu sou " + this.nome[0] + ".");
  },
};
```

 Para acessar as propriedades e metodós de um objeto é simples. Veja:
```JS
console.log(pessoa.nome);
console.log(pessoa.nome[0]);
pessoa.bio()
```

Saindo do exemplo dado, o modo que criamos um objeto é simples, podendo separar seu atributos por meio de "," e seu nome e valor por meio de ":". A sintaxe padrão obedece a seguinte estrutura:

```JS
var nomeDoObjeto = {
  nomeMembro1: valorMembro1,
  nomeMembro2: valorMembro2,
  nomeMembro3: valorMembro3,
};
```

### Notação ponto

Acima usamos a notação ponto, que é uma forma de acessarmos as propriedades de um objeto

``` JS
pessoa.idade;
pessoa.interesse[1];
pessoa.bio();
```
Para que seja acessado primeiro nos referimos ao objeto, colocamos um ponto e após informamos o nome da propriedade.

### Sub-namespace

Com o uso de `sub-namespace` podemos alterar o valor de um membro de um objeto para outro, fazendo ele mudar de:

```JS
nome:['Bob', 'Smith'],
```

para

```JS
nome: {
	primeiro: 'Bob',
	ultimo: 'Smith'
},
```

Para conseguirmos acessar essas duas novas propriedades de `nome` precisaremos adicionar um poto ao final do outro ponto e assim acessaremos  a propriedade:

```JS
pessoa.nome.primero
```

<em>OBS: vale lembrar que ao realizar essa mudança precisaremos mudar todos os metódos que acessam essa propriedade que não utilizava do sub-namespace</em>


### Notação colchete

Além da notação ponto existe a possibilidade de usarmos a notação colchete para acessarmos as propriedades de um objeto.

```JS
pessoa["idade"];
pessoa["nome"]["primeiro"];
```

<em>CURIOSIDADE:
Essa maneira se parece muito com a forma com que acessamos `arrays`, utilizando indices, no caso do objeto, o nome associado a propriedade.
Essa caracteristica faz com que os objetos também sejam chamados de <bold>Arryas associativos</bold></em>

### Setando membros do objeto

Até o momento vimos como receber objetos, mas é possível setar (atualizar) seus valores. Para isso podemos utilizar tanto da notação colchete como da notação ponto.

```JS
pessoa.idade = 45
pessoa.["nome"]["ultimo"] = "Santos"
```

Além de atualizar valores do nosso objeto, podemos também criar propriedades e métodos.

```JS
pessoa["olhos"] = "castanho";
pessoa.despedida = function () {
  console.log("Adeus a todos!");
};
```

Um vantagem da notação colchete é que conseguimos criar dinamicamente o nome e o valor de um propridade e objeto, por exemplo.

```JS
var myDataName = 'nomePropriedade';
var myDataValue = 'valorPropriedade	';
pessoa[myDataName] = myDataValue;
```

<em>OBS: a notação ponto so permite a passagem de valores literais, por isso não é possível criar dados dinamicamente como na notação colchete</em>

### O que é o 'this'

O "this" é uma palavra chave utilizada para se referir ao objeto atual do código que está sendo escrito, ou seja, considerando os exemplos acima, o `this` seria equivalente a `pessoa`.
Quando criamos objeto literais o `this` acaba não sendo muito util, mas no caso da criação de mais de objeto, ele permite o uso de um mesmo método para cada objeto criado. Exemplo:

```JS
var pessoa1 = {
  nome: "Chris",
  saudacao: function () {
    console.log("Oi! Meu nome é " + this.nome + ".");
  },
};

var pessoa2 = {
  nome: "Brian",
  saudacao: function () {
    console.log("Oi! Meu nome é " + this.nome + ".");
  },
};
```

### Introdução aos constructors

A criação de objetos literais é boa quando temos que criar somente um objeto, mas imagine se tivessemos que criar mais de um (como no exemplo anterior), ou que quisessemos mudar ou acrescentar um propriedade a esses objetos. Seria mais trabalhoso.
Nós gostariamos de criar uma "forma" para o objeto e definir metodos e propriedades, e depois criamos quantos objetos quisessemos com base naquela "forma".
Uma forma que poderiamos fazer é com o uso de uma função:

```JS
function createPerson(name) {
	const obj = {};
	obj.name = name;
	obj.introduceSelf = function () {
		console.log(`Hi! I'm ${this.name}.`);
	};
	return obj;
}

const salva = createPerson("Salva");
salva.introduceSelf(); // Hi! I'm Salva.

const frankie = createPerson("Frankie");
frankie.introduceSelf(); // Hi! I'm Frankie.
```

Todas as vezes que invocamos essa função criamos um objeto vazio, com a propriedade "name" e com o método "introduceSelf()", e somente após inicializarmos o nosso objeto, retornamos ele.
Esse trabalho que fizemos é longo. Porém podemos utilizar do *construtor*, que também é uma função, que será invocada com o uso da palavra `new`. Ao chamar o construtor ele fará:
* Criar um objeto
* Marcar o `this` com o novo objeto, para que possa ser referenciado com o `this` no construtor
* Rodar o código no construtor
* Retornar o um novo objeto

Por convenção, os construtores começam com a primeira letra sendo maiúscula, e sendo nomeados de acordo com o tipo de objeto que está sendo criado. Reescrevendo o exemplo acima teriamos:

```JS
function Person(name) {
	this.name = name;
	this.introduceSelf = function () {
		console.log(`Hi! I'm ${this.name}.`);
	};
};

// Para chamar Person() como construtor usaremos o 'new'

const salva = new Person("Salva")
salva.name;
salva.introduceSelf(); // Hi! I'm Salva.
```