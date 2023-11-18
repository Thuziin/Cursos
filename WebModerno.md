# Web Moderno

## Fundamentos
		As váriaveis podem ter três tipos de declarações distintas:
			- var nomeVar (permite redeclaração);
			- let nomeLet (não perimite redeclaração);
			- const nomeConst (não permite alteração de valores);
			
		JS é um linguagem fracamente tipada, ou seja, uma mesma variável pode receber diretentes tipos de dados:
			- let teste = 'olá'
			- teste = 1
			
		Assim como nas demais linguagem JS possui tipo de dados básicos:
			- Number:
				+ const peso = 1;
				+ const peso1 = Number('2.0')
			- String:
				+ const nome = "Arthur";
				+ nome.charAt(3);
				+ nome.substirng(0,3)
			- Boolean:
				+ let isAtivo = true;
				+ isAtivo = false;
				+ console.log(!!isAtivo)
			- Template Strings:
				+ const nome = 'Layla'
				+ const concatenar = 'Ola' + nome + '!'
				+ const template = `Olá ${nome} !`
				+ console.log(`1 + 1 = ${nome})
				
		Um Array em JS diferentemente de outras linguagens permite armazenar tipos de dados (heterogenios), sendo que os mesmos são vistos como objeto em JS
			- const valores = [0, 1, 2, 3]
			- valores[4] // undefined
			- valores.push({id: 3}, true, 'olá', null)
			- valores.pop()
			- delete valores[0]
			
		Funções  são os presidentes do JS, ou seja, quase tudo no JS é visto como objeto. Os mesmo podem ser inclusives criados dinamicamente.
		Os mesmos são compostos por uma coleão: chave, valor. Ex:
			- const prod = {}
			- prod.nome = 'Samsung'
			- prod.preco = 4999.00
			- prod['DescLegal'] = 0.40
			
		Null e Undefined:
			- let valor // não inicializada
			- console.log(valor) // Undefined
			- console.log(valor1) // Is not defined
			- valor = null // ausencia de valor
			- console.log(valor) // null
			
		OBS: evitar setar o valor de uma variável como undefined, deixe a linguagem fazer isso
		OBS:
			- const a = {name: 'Teste'} // a recebe o endereço do obj
			- const b = a // recebe o endereço de a
			- let d = 3 // tipo primitivo da linguagem
			- let c = d // copia por valor, ou seja, c = 3
		
		⋆ Destructuring:
			Usamos o  'Destructuring' para desestruturar um dado de um objeto, array ou outros. Por exemplo:
				const pessoa {
					nome = 'Arthur',
					idade = 20,
					endereco : {
						logradouro: 'Alguma rua ai',
						numero: 1001
					}
				}
				
				const {nome, idade} = pessoa
				const {sobrenome, bemHumorada = true } = pessoa
				const {endereco: {logradouro, numero} } = pessoa
				const [n1, , n3, , n5, n6 = 0] = [ 10, 7, 9, 8]
				
			A lógica de acessar um objeto usando  Destructuring é a mesma usando um array dentro de array (matriz)
			É possível passar  Destructuring como parametro de funções, exemplo:
				function rand ({mix = 0, max = 1000 }) {
					const valor = Math.random() * (max - min) + min
					return Math.floor(valor)
				}
				const valor = {min = 0, max = 9}
				console.log(rand(valor))

		Operador Ternário:
			const resultado = nota => nota >= 7 ? 'Aprovado' : 'Reprovado'

## Funções
		• As função em JS podem em algumas ocasiões ter parâmetros. Os tipos de dados desses parâmetros podem ir dos tipos primitivos, a arrays e até mesmo dados definidos pelo user (objetos).
		• O Hoisting não funciona somente para variáveis, funcionam também para funções, no entanto ela precisam seguir uma sintaxe específica para funcionar (function funcNome(){ })
		• As funções podem invocar elas mesmas (recursividade) ou serem até mesmo definidas se e somente se uma determinada condição for verdadeira.
		• Funçoões:
			▸ Função sem retorno:
			
				function imprimeSoma(a, b) {
					console.log(a + b)
				}
			▸ Função com retorno:
				function soma (a, b = 1) {
						return a + b
				}
				obs: b recebe um valor padrão para o caso de seu valor não ter sido passado por parametro
			▸ Função anonima:
				const imprimirSoma = function (a, b) { 
					console.log(a+b)
				}
			▸ Arrow function:
				const soma = () => {
					console.log(a+b)
				}
			▸ Com retorno implicito:
				const subtracao = (a,b) => a-b	
		
		• Funções são definidas em escopos, isso faz com que uma função declarada no escopo GLOBAL tenha acesso as variáveis do GLOBAL, no entanto, o GLOBAL não tem acesso as variáveis do escopo da minha função. Caso minha função PAI tenha uma função FILHA, a função FILHA terá acesso as todas as variáveis que minha função PAI.
		• Uma função recursiva é aquele onde a função chama ela mesma. EM JS ela pode referir a si mesma de três formas:
			▸ function name
			▸ arguments.callee()
			▸ variavel no escopo que se refere a função (foo())
				var foo = function bar () {
					
				}
		• Closure:
			+ Closure é um escopo criado quando uma função é declarada. Esse escopo permite a função acessar e manipular variáveis externas à função:
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
				
		• Callback:
			+ É uma função passada como parametro de uma outra função, que será invocada dentro de uma função externa para completar 					 uma ação/rotina. Ex:
				▸ Sem callback:
					function myDisplayer (some) {
						document.getElementById("demo").innerHTML = some;
					}

					function myCalculator(num1, num2) {
						let sum = num1 + num2;
					 	myDisplayer(sum);
					}

					myCalculator(5, 5);
				▸ Com callback:
					function myDisplayer(some) {
						document.getElementById("demo").innerHTML = some;
					}

					function myCalculator(num1, num2, myCallback) {
						let sum = num1 + num2;
						myCallback(sum);
					}

					myCalculator(5, 5, myDisplayer);
				▸ Outro exemplo:
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
		
		Construtoras:
			+ 
					
					
		this: objetos atuais da minha função/classes.
			Objeto referenciado dentro da minha função, podendo ser a global ou uma local
		O 'this' é JS é confuso, ele varia de acordo com o contexto (???)
					
					
					
					
					
					
					
					
					
					
					
					
					
					
					
					
					
					
					
					
					
