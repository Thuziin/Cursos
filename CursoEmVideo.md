# Curso Em vídeo (JavaScript)

##  MODULO A:
	- Aula 1:
		Client x Server:
			JS é uma tecnologia que é focada no lado do cliente (mas pode ser usada no lado do servidor também)
			Aplicações com JS:
				+ Google
				+ Youtube
				+ Linkedin
				+ Netflix
				+ Facebook
	
	- Aula 2:
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

	- Aula 3:
		Bibliografia:
			+ JavaScript: o guia definitivo
			+ JavaScript: guia do programador
			+ developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide
			+ https://www.ecma-international.org/publications-and-standards/standards/ecma-262/
		Download: 
			+ Vscode;
			+ nodejs;
			+ npm;
			+ navegador;
	
	- Aula 4:
		Criação do nosso primeiro script na pasta "Curso em Video"

## MODULO B
	- Aula 1:
		Comentários:
			+ // : comments in inline 
			+ /* */ comments on block 
		Variáveis:
			+ var identificador = dado
				- var n1 = 5;
				- var s1 = 'Curso em video'/"JavaScript"/`Arthur`;
				- Os tipos de dados primitivos são:
					* number;
					* string;
					* boolean;
			
		OBS: Para acessar o node eu acesso o meu terminal (nativo ou no vscode) e digito 'node'. Para sair digito '.exit'
		OBS: JS é sensative case
		
	- Aula 2:
		Manipulação de dados:
			+ O sinal de mais (+) pode servir tanto para concatenar como para adição, o que vai variar é o contexto que ta sendo
			utilizado
			+ window.prompt: retorna por padrão uma string, se quiser que recebam 'Number' é necessário converter os valores:
				- Number.parseInt(VARIAVEL) // converte para int
				- Number.parseFloat(VARIAVEL) // converte para float
				- Number(VARIAVEL) // converte para um número, o JS verifica a melhor escolha, 
						no entato essa funcionalidade não anula as duas acimas
			
			+ Assim como é possível converter uma String para Number, é possível fazer o caminho inverso também:
				- String(VARIAVEL)
				- VARIAVEL.toString()
			+ Um recurso recente do ECMA é o template string, que funciona da seguinte forma:
				- var nome = 'Arthur'
				- var idade = 20
				- var nota = 100
				console.log(`O aluno ${nome} de idade ${idade} tirou a nota ${nota}`)
			+ A string possui bibliotecas que permitem manipulá-las e realizar:
				- Contagem;
				- UpperCase;
				- LowerCase;
				- ...;
			+ Assim como as strings posso formatar de acordo com a minha necessidade os números também:
				- var salary = 1500.5
				- salary.toFixed(2)
				- salary.ToFixed(2).replace('.',',')
				- salary.toLocaleString('pt-BR', {style: 'currency', currency: 'BRL'})
				
	- Aula 3:
		Operadores:
			- Aritmeticos:
				▸ mais (+)
				▸ menos (-)
				▸ multiplicação (*)
				▸ divisão (/)
				▸ módulo (%)
				▸ potência (**)
			- Atribuição:
				▸ var n = 3;
				▸ n = n + 4 // n += 4
				▸ n = n - 2 // n -= 2
				▸ n = n * 2 // n *= 2
				▸ n = n / 2 // n/= 2
				▸ n = n ** 2 // n **= 2
				▸ n = n % 10  // n %= 10
				▸ n = n += 1 // n++ ou ++n
				▸ n = n - 1 // n-- ou --n
			- Relacionais (sempre gera um resultado booleano):
				▸ maior que (>)
				▸ menor que (<)
				▸ maior ou igual (>=)
				▸ menor ou igual (<=)
				▸ igual (==) // JS não teste o tipo de dado (5 == '5')
					- 5 === '5' (false)
				▸ diferente (!=)
			- Lógicos:
				▸ ! (negação)
				▸ && (conjução/e)
				▸ || (disjunção/ou)
				
			- Ternários:
				▸ ? : (aparecem na mesma expressão)
					- teste ? true : false
						• media >= 7 ? 'Aprovado' : 'Fica pra proxima'
						• var n = 8
						• var resultado = n % 2 == 0 ? 5 : 9
			
## MODULO C
	- Aula 1:
		Introdução a DOM (Document Object Model)
			- Árvore DOM:
				img DOM TREE
			- Posso acessar os elementos da DOM diversas formas:
				+ tag:
					▸ document.getElementsByTagName()
				+ id:
					▸ document.getElementByIdName()
				+ name;
					▸ document.getElementsByName()
				+ class;
					▸ document.getElementsClassName()
				+ selector;
					▸ querySelector()
					▸ querySelectorAll()
		
	- Aula 2:
		Eventos DOM:
			- A 'configuração' do meu evento ocorre dentro do JS
			- Ações como a movimentação do mouse, cliques e entre outros são utilizados para disparar eventos:
				+ Para saber sobre os eventos olhar documentação da Mozilla
			- FUNÇÕES:
				+ function AÇÃO (param) {
					// ... codigo da função
				}
				
				+ Possível termos funções anônimas também, mas pode acontecer de ela não atender os nossos objetivos
			- Os eventos podem ser dispardos tanto de dentro do html, observando ações do user, como atráves do JS adicionar 'ouvidos' ao código
			
## MODULO D
				
