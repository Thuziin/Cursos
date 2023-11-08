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

+ [Documentação Mozilla](developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide)

+ [Documentção Ecma](https://www.ecma-international.org/publications-and-standards/standards/ecma-262/)

<em>OBS: Para acessar o node eu acesso o meu terminal (nativo ou no vscode) e digito 'node'. Para sair digito '.exit'</em>


## Fundamentos

As váriaveis podem ter três tipos de declarações distintas:

	var nomeVar (permite redeclaração);
	let nomeLet (não perimite redeclaração);
	const nomeConst (não permite alteração de valores);
	
JS é um linguagem fracamente tipada, ou seja, uma mesma variável pode receber diretentes tipos de dados:

	let teste = 'olá'
	teste = 1
	
Assim como nas demais linguagem JS possui tipo de dados básicos:

<code>Number:</code>

    const peso = 1;
    const peso1 = Number('2.0')

<code>String:</code>

    const nome = "Arthur";
    nome.charAt(3);
    nome.substirng(0,3)
    
<code>Boolean:</code>

    let isAtivo = true;
    isAtivo = false;
    console.log(!!isAtivo)

<code>Template Strings: </code>

	const nome = 'Layla'
	const concatenar = 'Ola' + nome + '!'
	const template = `Olá ${nome} !`
	console.log(`1 + 1 = ${nome})

<code>Arrays</code>

Em JS os Arrays tem a cabacidade de amarzenar informação que possuem várias tipos de dados, ou seja, são capazes de armazenar dados heterogênios.

	const valores = [0, 1, 2, 3]
	valores[4] // undefined
	valores.push({id: 3}, true, 'olá', null)
	valores.pop()
	delete valores[0]

<code>NULL e Undefined</code>

Embora não seja recorrente e indicado, em JS é possível inicializar variáveis com *null* e com o *undefined*

	let valor // não inicializada
	console.log(valor) // Undefined
	console.log(valor1) // Is not defined
	valor = null // ausencia de valor
	console.log(valor) // null

## Manipulação de dados:

O sinal de<code> mais(+)</code> pode servir tanto para concatenar como para adição, o que vai variar é o contexto que ta sendo utilizado

	Number.parseInt(VARIAVEL) // converte para int
	Number.parseFloat(VARIAVEL) // converte para float
	Number(VARIAVEL) // converte para um número, o JS verifica a melhor escolha
			
Assim como é possível converter uma *String* para *Number*, é possível fazer o caminho inverso também:

	String(VARIAVEL)
	VARIAVEL.toString()

A string possui bibliotecas que permitem manipulá-las e realizar:

	Contagem
	UpperCase
	LowerCase
	//...

Assim como as strings posso formatar de acordo com a minha necessidade os números também:

	var salary = 1500.5
	salary.toFixed(2)
	salary.ToFixed(2).replace('.',',')
	salary.toLocaleString('pt-BR', {style: 'currency', currency: 'BRL
				
### Operadores:

<code>Aritmeticos:</code>

	▸ mais (+)
	▸ menos (-)
	▸ multiplicação (*)
	▸ divisão (/)
	▸ módulo (%)
	▸ potência (**)

<code>Atribuição:</code>

	▸ var n = 3;
	▸ n = n + 4 // n += 4
	▸ n = n - 2 // n -= 2
	▸ n = n * 2 // n *= 2
	▸ n = n / 2 // n/= 2
	▸ n = n ** 2 // n **= 2
	▸ n = n % 10  // n %= 10
	▸ n = n += 1 // n++ ou ++n
	▸ n = n - 1 // n-- ou --n

<code>Relacionais:</code>

	▸ maior que (>)
	▸ menor que (<)
	▸ maior ou igual (>=)
	▸ menor ou igual (<=)
	▸ igual (==) // JS não teste o tipo de dado (5 == '5')
		- 5 === '5' (false)
	▸ diferente (!=)

<em>obs: Sempre gera um resultado booleano como resultado da comparação!</em>

<code>Lógicos:</code>

	▸ ! (negação)
	▸ && (conjução/e)
	▸ || (disjunção/
				
<code>Ternários:</code>

	▸ ? : 
	teste ? true : false
    
	media >= 7 ? 'Aprovado' : 'Fica pra proxima'

	var n = 8
	var resultado = n % 2 == 0 ? 5 : 9

## Funções

Função são escopos separados que realizam determinada atividade programada pelo o usuário, por terem escopos próprios às vezes é necessário passar parâmetros para que sejam capazes de lidar com dados e afins. Em JS podemos ter funções de várias formas, como por exemplo:

<code>Função sem retorno:</code>
			
	function imprimeSoma(a, b) {
		console.log(a + b)
	}

<code>Função com retorno:</code>

	function soma (a, b = 1) {
		return a + b
	}

<em>obs: b recebe um valor padrão para o caso de seu valor não ter sido passado por parametro</em>

<code>Função anonima:</code>

	const imprimirSoma = function (a, b) { 
		console.log(a+b)
	}

<code>Arrow function:</code>

	const soma = () => {
		console.log(a+b)
	}

<code>Com retorno implicito:</code>

	const subtracao = (a,b) => a - b

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
				
### Callback:

É uma função passada como parametro de uma outra função, que será invocada dentro de uma função externa para completar uma ação/rotina. Ex:

<code>Sem callback:</code>

	function myDisplayer (some) {
    	document.getElementById("demo").innerHTML = some;
	}

	function myCalculator(num1, num2) {
		let sum = num1 + num2;
	 	myDisplayer(sum);
	}

	myCalculator(5, 5);

<code>Com callback:</code>

	function myDisplayer(some) {
		document.getElementById("demo").innerHTML = some;
	}

	function myCalculator(num1, num2, myCallback) {
		let sum = num1 + num2;
		myCallback(sum);
	}

	myCalculator(5, 5, myDisplayer);

<code>Outro exemplo:</code>

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


## Eventos com a DOM