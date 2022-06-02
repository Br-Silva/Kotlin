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
