# TypeScript

## Instalation

Existem duas formas de si instalar o [typescript](https://www.typescriptlang.org/download). Ambas são possíveis de se fazer seguindo o passo a passo presente na documentação oficial do *TypeScript*

### TypeScript on my project

Primeiramente preciso inicializar o meu projeto, para isso faço (com npm):
```
npm init -y
```

Após a inicialização podemos instalar o *TypeScript* localmente como depedência de desenvolvimento com o seguinte comando:
```
npm install typescript --save-dev
```

Após a intalação é necessário criar um arquivo de configuração do typescript. Todas as configurações do type ficam em uma arquivo chamado *tsconfig.json* e para criá-lo é necessário fazer:
```
npx tsc --init
```

OBS: o arquivo criado possui as configurações e as explicações de cada "tópico"

A configuração estar realizada, para "executar" nosso projeto usamos:
```
npm init
```

### Globaly instaling TypeScript

A instalação global do TypeScript é mais interessante quando se tem um 'compromisso' a longo termo, ou seja, quando será utilizado em mais de um projeto, sendo assim podemos usar o comando <code>tsc</code> em qualquer no nosso terminal que será reconhecido. Para isso basta executar o comando:
```
npm install -g typescript
```

Assim como na instalação do ambiente local criaremos o nosso projeto com
```
npm init -y
```

Podemos também criar o arquivo de configuração com:
```
npm  tsc --init
```

E inicializaremos o nosso projeto com:
```
npm init
```

Para podermos executar agora o nosso arquivo .ts usaremos o seguinte comando:
```
npx tsc
```

Este comando compilará o nosso arquivo .ts de acordo com o <code>tscongif.json</code>

Para podermos agora transcrever o nosso código de <code>TypeScript</code> para <code>JavaScript</code> usaremos o seguinte comando: 
```
node 'nomedoarquivo.js'
```
## Tipo básicos e Inferência de tipos

Assim como no *JS* os tipos de dados básicos em *TypeScript* são:
<ul>
    <li> string;</li>
    <li> number</li>
    <li> boolean</li>
</ul>
Em ambas as linguagens não é necessário informar o tipo de dado que a minha variável irá armazenar, no entando em *Type* podemos "forçar" isso para evitar algum bug por exemplo, para isso podemos fazer:

```
let nome: string
nome = 'Arthur'
```
O código acima faz com que minha varável <strong>nome</strong> receba informações somente do tipo string.<br>
Além de conseguirmos indicar que tipo queremos que nossa váriavel seja podemos também deixar o *Type* 'deduzir' em que tipo que ela se encaixa. Observe:
```
let numero = 3
```
Ao fazer isso e se passar o mouse sobre o comando veremos que o *Type* deduziu que <strong>numero</strong> fosse do tipo number e caso tentemos fazer ela receber uma string receberemos um erro

Assim como as váriaveis de tipos de dados básicos, é possível atribuir para outras 'funcionalidades' do *typescript* seus tipos de dados, como:

### Array

```
let nome: string[]
let nome1: Array<string>

let teste: Array<boolean>
```

### Tupla
```
let aluno: [string, number, boolean]
aluno = ['Arthur', 20, true]

let aluno1: any[]
```

### Objeto

```
let objeto: objectx

let objeto1: Record<string, number/string/boolean>
objeto1 = {nome:'Arthur', idade: 10, ehLegal: true}

let objeto2: {nome: string, idade: number, ehLegal: boolean}
objeto2 = {nome:'Arthur', idade: 10, ehLegal: true}

```

### Função

```
function nada() : void {}

function soma(a: numer, b: number): number {
    return a + b
}

function soma1(a: numer, b: number) {
    return a + b
}

function fale(): string {
    return 'olá'
}

const soma2 = (a: number, b: number): number => a + b
```

## Union

Vamos supor que estamos montando o front-end da nossa aplicação e queremos mostrar um *id*, no entanto esse *id* vem do nosso *banco de dados* e em um deles está salvo como <code>Number</code> e no outro como <code>String</code>. Podemos criar uma váriavel que conseguirá receber essa informação e que receberá este *id* dentro deste dois tipos.

```
let id = number | string
```

## Type alias

Considerando a mesma situação anterior, só que dessa vez temos vários *ids*, em vem de fazer um <code>Union</code> para cada um podemos criar um tipo e em seguida tiparmos eles.

```
type Id = number | string | ...

let id1: Id
let id2: Id
let id3: Id
let id4: Id
let id5: Id

let Usuario = {nome: string; idade: number}

let user: Usuario
```

*obs: podemos criar um <code>Type alias</code> para qualquer um dos tipos já vistos, desde objetos à boolean*

## Interface

No exemplo acima criamos um <code>Type Alias</code> para criar um objeto, no entao existe uma outra forma de se fazer isso, que seria com o <code>Interface</code>

```
interface Usuario {
    nome: string
    idade: number
}

let user: Usuario
```

*obs 1: Como padronização normalmente se utiliza o <code>Interface</code> para tipar objetos e o <code>Union/Type Alias</code> para tipos básicos*

*obs 2: As vezes se coloca um T antes do nome do nosso Type Alias e um I antes do Interface para ajudar a indeticar com qual estamos lidando*

## Extendendo Interface e tipos

Um recurso que o *TypeScript* fornece é a capacidade de exterdemos um intarface para outra, ou um tipo para outra.

### Extendendo Interface

```
interface Pessoa {
    nome: string
    idade: number
}

inteface Aluno extends Pessoa {
    curso: string
    nsg: number
}

let aluno: Aluno // agora o aluno tem acesso as informações de Pessoa e Aluno
```

### Inteface e Type

```
type Pessoa = {
    nome: string
    idade: number
}

interface Aluno extends Pessoa {
    curso: string
    idade: number
}
```

Assim como de Interface para Interface o Inteface para Type também funciona, nesse exemplo o Aluno terá também as propriedades de Pessoa

### Extendendo Type

Para extender de um tipo para o outro a lógico é diferente, no entanto o funcionamento do código será o mesmo, veja:

```
type Pessoa = {
    nome: string
    idade: number
}

type Aluno = Pessoa & {
    curso: string
    idade: number
}
```

### Propriedade Opcional

Nos exemplos acimas criamos objetos onde todos os campos são usado, mas pode acontecer de existir algum campo que não seja obrigatório de preencher, por isso temos o recurso de indicar que ele é opcional sem corrermos o risco de algum erro acontecer.

```
type Pessoa = {
    nome: string
    idade: number
    carro?: string
}

type Aluno = Pessoa & {
    curso: string
    idade: number
}

let aluno: Aluno
aluno = {
    nome: 'Arthur'
    idade: 20
    curso: 'Engenharia da Computação'
    nsg: 3.5
}
```
Ao tentarmos criar o objeto aluno não teremos erros, pois indicamos que o carro em pessoa é uma propriedade opcional, ou seja, não é obrigatória de ser preenchida

## Generics

Anteriormente vimos que:

```
let nome1: Array<string>
```
Desta forma criávamos um <code>Array</code> usando <code>Generics</code>.

Veremos que também podemos fazer isso com os tipos de dados que criarmos, da seguinte forma:

```
interface Pessoa<T = undefined> {
    nome: string
    idade: number
    profissao: T
}

type Aluno = {
    matricula: string
}

interface Engenheiro {
    crea: string
}

interface Medico {
    crm: string
}

let pessoa: Pessoa
let aluno: Pessoa<Aluno>
let engenheiro: Pessoa<Engenheiro>
let medico: Pessoa<Medico>
```

*obs: é válido tanto para interfaces como para type*

Além de podermos criarmos nossos dados assim também reduzimos a quantidade de *extensions* no código
