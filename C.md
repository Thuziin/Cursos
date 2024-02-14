# Arquivos
## Abertura de Arquivos
A abertura de um arquivo existente num suporte magnético a uma variável do nosso programa. No entanto, C possui apenas tipos *char*, *int*, *float* e *double*, sendo que eles não se referem a arquivos.
Para podermos usar um arquivos precisamos declarar uma variável do tipo <code>FILE</code> (presente na biblioteca <code><stdio.h></code>

```
FILE* arquivo; // Declaramos um ponteiro para o arquivo
```

A abertura de fato do arquivo se dá pelo o uso da função <code>fopen</code>
```
FILE * fopen(nomeArquivo, operacaoSobreArquivo);
```

### Modos de abertura
Existem três modo de abertura de arquivos:
	<ul>
		<li>r</li>
		<li>w</li>
		<li>a</li>
	</ul>
O modo <strong>r</strong>:

É o modo de leitura, tenta ler um arquivo e caso não consiga retorna <code>NULL</code>

O modo <strong>w</strong>:

Abre um arquivo para a escrita, se existir um arquivo com o mesmo nome apaga o antigo e cria um novo com mesmo nome e novos dados. Caso não consiga realizar a operação retorna <code>NULL</code>

O modo <strong>a</strong>:

Abre o arquivo para acrescentar informação. Este modo acrescenta informção ao final do arquivo que teve nome passado como parametro, se o arquivo não existir cria um novo e escreve os dados no inicio do arquivo. Caso não consiga realizar a operação retorna <code>NULL</code>
		
Além destes três modos básicos existe a possibilidade de abrir um arquivo simultaneamente para a leitura e escrita, sendo os modos:

<ul>
	<li>
		<code>r+</code>
	</li>
	<li>
		<code>w+</code>
	</li>
	<li>
		<code>a+</code>
	</li>
</ul>

#### Modo de Texto e Modo Binário
Por padrão qualquer arquivo em C quando aberto é considera do tipo texto, ou seja, o conteúdo em seu interior consiste em carateres que não estão presentes na tabela ASCII. Por sua vez os arquivos binários tem como conteúdo informações que achariamos na tabela ASCII e será lido byte a byte.

Para poder realizar a leitura de um arquivo binário precisamos indicar ao nosso programa que realizará tal ação da seguinte forma:

```
rb;
wb;
ab;
a+b;
...
```
## Fechamento de um arquivo
Sempre que estamos lidando com arquivos é considerado um bom hábito fechar o arquivos que estava sendo lidado, por mais que isso seja realizado automaticamente ao finalizar um programa.

Para podermos realizar tal tarefea usamos a função <code>fclose</code>

```C
fclose(FILE *arquivo)
```

Exemplos usando abertura, operação e fechamento de um arquivo:
```C
#include <stdio.h>

int main () {
	FILE *fp;
	char s[100];
	
	puts("Nome do arquivo: ");
	gets(s);
	
	fp = fopen(s, "r");
	
	if (fp == NULL) {
		printf("Não foi possível ler o arquivo\n");
	} else {
		printf("Leitura realizada com sucesso\n");
		fclose(fp);
	}
	return 0;
}
```

## Leitura de caractere

Para realizar a leitura de caracteres presentes em um arquivos usamos a função <code>fgetc(arquivo)</code>

Exemplo:
```C
#include <stdio.h>
#include <stdlib.h>

int main (int argc, char *argv[]) {
	FILE *arquivo;
	int ch; // inteiro para ler caracteres
	
	if (argc != 2) {
		exit(1);
	}
	
	arquivo = fopen(argv[1], "r"):
	
	if (arquivo == NULL) {
		printf("Impossível de ler o arquivo\n");
		exit(2);
	}
	
	while ((ch=fgetc(arquivo) != EOF) {
		putchar(ch);
	}
	fclose(arquivo);
	return 0;
}
```

No código acima temos tratamento de erros (encerrando) o programa caso não seja possível ler o arquivo. Caso consigamos ler o arquivo mostramos na tela caractere a caractere até "chegarmos" ao 'EOF'

*OBS: o nome do arquivo é passado como parametro pro meio do <code>argv</code>, ou seja, na hora de exercutarmos o código no terminal*

## Escrita de um carcatere em um arquivo

Assim como podemos ler os caracteres de um arquivo podemos também escrever caracteres em um arquivo. A escrita pode ser realizada por meio da função <code>fputc()</code>

```C
#include <stdio.h>
#include <stdlib.h>

int main (int argc, char *argv[]) {
	FILA *fin, *fout;
	int ch;
	
	if (argv != 3){
		exit(1);
	}
	
	fin = fopen(argv[1], "rb");
	if (fin == NULL) {
		printf("Impossível ler o arquivo\n");
		exit(2);
	}
	
	
	if ((fout = fopen(argv[2], "wb") == NULL) {
		printf("Impossível de criar arquivo para escrita\n"):
		exit(3);
	}
	
	while (ch = fgetc(fin) != EOF) {
		fpuct(ch, fin);
	}
	fclose(fin);
	fclose(fout);
	
	return 0;
}
```
