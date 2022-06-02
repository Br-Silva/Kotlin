# Sintaxe Básica Kotlin
### Tipos de dados
- String
- Int
- Long
- Float
- Double
- Array
- Boolean
- Char
- Byte
- Short
- Null! 

### Convertendo tipos de dados
- toString()
- toByte()
- toInt()
- toShort()
- toLong()
- toFloat
- toDouble()
- toChar()

### Declaração de Variável
**var** (Valor mutável, camelCase)<br>
**val** (Valor imutável, camelCase)<br>
**const val** (Valor imutável, SNAKE_CASE) é declarada fora da função main

#### Monstrando elementos no console
Println ()

### Nullability
Qualquer tipo pode ser nulo, porém isso deve ser explicitado na declaração de variável através do uso da interrogração (?);<br>
A inferência de tipo não atribui nullability; 

        var month: Int? = null<br>
        //Atribui valor corretamente a month

        var month: Int = null<br>
        /*Erro de compilação
        "Null can not be a value of a non-null type Int */

## Operadores
### Operadores Aritméticos
| Função       | Expressão | Comando  | Atribuição* | 
|--------------|-----------|----------|-------------|
|Soma          |a + b      |a.plus(b) |a+=b         |
|Subtração     |a - b      |a.minus(b)|a-=b         |
|Multiplicação |a * b      |a.times(b)|a*=b         |       
|Divisão       |a / b      |a.div(b)  |a/=b         |
|Resto         |a % b      |a.mod(b)  |a%=b         | 

*Atribui a operação do valor a e b ao valor a

- Os operadores podem ser chamados tanto como expressão quanto como comando. O resultado será o mesmo
- A função de soma também funciona para concatenar Strings

### Operadores Comparativos
|Função    | Expressão | Comando |
|--- | --- | --- |
|maior/menor | a>b ou a<b | a.compareTo(b)>0 ou a.compareTo(b)<0 |
|maior/menor igual | a>=b ou a<=b | a.compareTo(b)>=0 ou a.compareTo(b)<=0 |
|igual | a==b | a.equals(b)
|diferente | a!=b | !(a.equals(b)) | 

- Os comandos **compareTo** retornam os **valores -1 (menor que), 0 (igual) ou 1 (maior)**. Já os operadores retornam **valores booleanos**.
- O comando **equals** retorna um **boleano**.

### Operadores Lógicos
|Função e Expressão | Comando |
|--- | --- |
|E (&&) | (expressão1) and (expressão2) |
|Ou (\|\|) | (expressão1) or (expressão2) |
- Quando utiliza-se o comando, é recomendado colocar a expressão entre parenteses

### Operadores In e Range
|Função e Expressão |
|---|
|contém (In) | 
|não contém (!in) |
|range/faixa de valores (Int..Int) | 
- Se o valor está presente em uma lista ou em uma faixa (range) de valores
- Range cria um intervalo de valores que inicia no primeiro parâmetro e acaba no segundo

## Manipulação de Strings
- Strings possuem diversos métodos associados;
- indexação, concatenação, comparação, formatação; 
- pode ser concatenada com plus/+;
- também é tratada como um array de Char

### Indexação
- String como array;
- First(), last(), String.length, String\[index\];

                                val s = "Olá, mundo!"
                                
                                println(s[0])
                                println(s.first())
                                //imprime O
                                
                                println(s[s.length-1])
                                println(s.last())
                                //imprime !
                                
### Concatenação
- Para concatenar duas strings o plus/+ pode ser utilizado;
- Para concatenar uma variável a uma String, os simbolos ${} devem ser inseridos;

                                val name = "Ana"
                                val s = "Olá"
                                
                                println(s + name)
                                //imprime OláAna
                                println("${s}, ${name}!")                               
                                //imprime Olá, Ana! 
                                println(Bem vinda(o), $name!")
                                //imprime Bem vinda(o), Ana!
                                
### Formatação 
|Nome | Função | Métodos |
|--- | --- | --- |
|Capitalização de Strings | Alterar a formatação entre letras minúsculas e maiúsculas | capitalize(), toUpperCase(), toLowerCase(), and decapitalize() |
|Remoção de espaços | Remove espaços vazios e caracteres inadequadas para impressão | trimEnd(), trimStart(), trim() |
|Substituição de caracteres | Substituir caracteres por outros | replace (x, y)
|Formatação | Formatar outros valores para um padrão de string | "padrão ${valor}".format(valor) |

