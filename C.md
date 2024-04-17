# C
## Panorama histórico
A linguagem C surge em 1972 nos laboratórios da Bell, sendo que a mesma foi projetada para ser uma linguagem de propósito geral.

A lingaugem foi padronizada pela ISO, pois um grande número de implementações e compiladores foram criados.

C é uma das linguagens mais importante, pois ajudou na contrução de milhares de softwares, além de inspirar a criação de outras linguagens de programação

## Características
- É uma linguagem imperativa: baseada em comandos e dados;
- Uma linguagem estruturada: os programas são baseados em sequências de comandos e decisões;
- Compilada: um compilador é utilizado para gerar programas executáveis

### Compilador
O compilador é um software básico da computação que tem por objetivo ler um programa escrito em uma linguagem fonte e gerar um programa equivalente em uma linguagem alvo.

O programas em C são arquivos com extensão `.c`. A compilação dele gera um executável `.exe`. 

Para compilarmos os programas gerados usamos compiladores, algum deles são:
- GCC
- Clang
- IBM

## Tipos de dados
|Tipos                   |Palavra chave         |
|------------------------|----------------------|          
| caracterere            | char                 |
| inteiro                | int                  |
| real (precisão simples)| float                |
| real (precisão dupla)  | double               |
| void                   | void                 |             

### Modificadores

|Modificador             |Descrição         |
|------------------------|------------------|          
| signed            	 | char             |
| unsigned               | int              |
| long 					 | float            |
| short   				 | double           |

### Operadores aritiméticos

|Operador      |Operação        |
|--------------|----------------|          
| -            | troca de sinal |
| -            | subtração      |
| +            | soma           |
| *            | multiplicação  |
| /            | divisão        |
| %            | módulo         |
| ++           | incremento     |
| --           | decremento     |

## Programas Sequenciais
Abaixo um programa sequencial em **C** com o uso de dados apresentados acima e com entrada e saída de dados.
```C
#include <stdio.h>

void main () {
	int a, b, soma;
	printf("Digite o primeiro numero: "); // Saida de dados
	scanf("%d", &a) // Leitura e armazenamento do dado

	printf("Digite o segundo numero: ")
	scanf("%d", &b);

	soma = a + b;

	printf("A soma de %d e %d e igual a %d", a, b, soma);
}
```

## Comandos condicionais
### Operadores relacionais

|Operador      |Descrição       |
|--------------|----------------|          
| >,>=,<,<=>   | comparação     |
| ==           | igualdade      |
| !=           | diferença      |

### Operadores lógicos

|Operador      |Operador        |
|--------------|----------------|          
| !            | negação        |
| &&           | AND            |
| \|\|         | OR             |

*Obs:* A ordem de precedência dos operadores é negação, E e OU.

### if (se)

Em uma condição com <code>if</code> a "resposta" será uma valor lógico (true ou false)

```C
if (condicao) comando;

if (condicao) {
	lista de comando
}
```

Um exemplo seria um programa que ler um valor inteiro e informa se o número é positivo:

```C
#include <stdio.h>

void main () {
	int dado;

	printf("Informe um valor inteiro: ");
	scanf("%d", &dado);

	if (dado > 0) // caso seja uma valor logico verdadeiro executa o bloco abaixo
		printf("\nE positivo");
}
```

### if-else (se-senao)

```C
if (condicao) comando;
else comando;

if (condicao) {
	lista de comando;
} else {
	lista de comando
}
```

Um exemplo de uso seria o comando a seguir:
-Um programa para ler a nota final e a frequência de um aluno e informar se ele foi aprovado ou reprovado. Para ser aprovado, o aluno deve ter a nota maior ou igual a 60 e a frequência maior ou igual a 75. Caso contrário, o aluno é reprovado.

```C
#include <stdio.h>

void main(){
	float nota, freq;

	printf("Digite a nota do aluno: ");
	scanf("%f", &nota);

	printf("\nDigite a frequencia do aluno: ");
	scanf("%f", &freq);

	if ( nota >= 60 && freq >= 75)
		printf("\nFoi aprovado.");
	else
		printf("\nNao foi aprovado.");
}

```

### switch-case
Quando se é necessário verificar o valor de uma variável **inteira** ou **caractere** é igual a um conjunto conhecido e finito de
valores, pode-se utilizar o comando <code>switch-case</code>.

O comando switch-case corresponde a uma sequência de comandos do tipo <code>if-else</code>


A vantagem de usá-lo em vez do <code>if-else</code> é que torna o código mais legível. A sua sintaxe é:

```C
switch (expressao) {
	case expressao: comandos;
		break; // necessário para que as demais clausulas nao sejam executadas também
	case expressao: comandos;
		break;
	default: comandos // caso nenhuma das outras cláusulas seja verdadeira
}
```

## Comandos de repetição
Uma repetição (ou loop, ou iteração, ou laço) é um sequência de passos executadas repetidas vezes até que uma determinada condição de parada ocorra.

Em <code>C</code>, há três tipos de comandos de repetição:
- do-while
- while
- for

### do-while
A sintaxe do <code>do-while</code> é:
```C
do 
	comando;
while (condicao);

do {
	lista de comandos;
} while (condicao); // Resulta em um valor lógico (true ou false)
```

Exemplo: um programa para ler o raio de círculos e informar a área deles. O programa deverá ser encerrado quando o usuário informar que não deseja continuar

```C
#include <stdio.h>
#include <math.h>

void main () {
	float raio, area;
	char resp;

	do {
		system("cls"); // limpar a tela no windows

		printf("\nDigite o raio: ");
		scanf("%f", &raio);

		if (raio > 0) {
			area = M_PI * pow(raio, 2);
			printf("\nA área é: %.2f", area);
		}
		else printf("\nRaio invalido");

		printf("\nDesejea continuar: (S/N): ");
		sflush(stdin);
		scanf("%c", &resp);
		
	} while (resp == 'S' | resp == 's');
}
```

### while
A sintaxe do <code>while</code> é:
```C
while (condicao) // Resulta em um valor lógico (true ou false)
	comando;

while (condicao) {
	lista de comandos;
} 
```

Obeseve que no comando **do-while**, o teste é realizado ao final, ou seja, os comandos são executados pelo menos uma vez.

Por sua vez, no comando **while**, o teste é realizado no início.

Exemplo: um programa para ler um sequência de números inteiros e positivos da entrada. O último número a ser informado deverá ser menor ou igual a zero. O programa deverá mostrar a soma dos números, a quantidade de números digitados e a média deles. 
```C
#include <stdio.h>

void main () {
	int numero, soma = 0, contador = 0;
	float media;

	printf("\nInforme o número para teste: ");
	scanf("%d", &numero);

	while ( numero > 0) {
		contador++; // contador = contador + 1
		soma += numero // soma = soma + numero

		printf("\nInforme o número para teste: ");
		scanf("%d", &numero);
	}

	if ( contador > 0) {
		media = float(soma) / contador;
		printf("\nA soma dos números é: %d", soma);
		printf("\nA quantidade de números válidos é: %d", contador);
		printf("\nA media dos números é: %.2f", media);
	}
}
```

### for
Quando se sabe previamente a quantidade de vezes que a repetição será realizada, pode-se usar um comando com a estrutura do tipo **para-cada**. Em **C** o comando <code>for</code> tem essa estrutura.

A sintaxe desse comando é a seguinte:
```C
for (comando_inicio; expressao; comando_fim)
	comando;

for (comando_inicio; expressao; comando_fim) {
	lista de comandos
}
```

comando-inicio:
 - é o comando realizado na entrada do bloco for;
 - em geral, ele é utilizado para definir o valor inicial de uma variável de controle do laço (um contador)


expressão: 
- é a condição que deve ser satisfeita para a repetição continuar

comando-fim:
- é o comando realizado na saída do bloco, antes da expressão ser avaliada;
- em geral, ele é utilizado para incrementar/decrementar a variável de controle do laço

Exemplo: Um programa para calcular o fatorial de um número. O fatorial é definido para os números inteiros maiores ou igual a zero da seguinte forma:
- Fatorial de 0 (0!) é igual a 1.
- Fatorial de N (N!) é dado por: N x Fatorial de N-1

```C 
#include <stdio.h>

void main () {
	unsigned long fat = 1;
	int num, i;

	printf("Digite um número: ");
	scanf("%d", &num);

	if ( num < 0 )
		printf("Não existe fatorial para o número");
	else if (num == 0 || num == 1)
		printf("Fatorial de %d e %d", num, 1);
	else {
		// calculo do fatorial
		for (i = 2; i < num; i++)
			fat *= i; // fat = fat * i;

		printf("Fatorial de %d é %d", num, fat);
	}
}
```