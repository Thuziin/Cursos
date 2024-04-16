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