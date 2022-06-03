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

### Empty x Blank
- Se o **tamanho da string for 0 está empty e blank** (se não há nada dentro da string, na atribuição foi abrido e fechado aspas sem nada dentro)
- Se o **tamanho for > 0**, mas todos os caracteres forem espaços em branco, **está blank, mas não está empty**;

## Funções
- Prefixo Fun (de function) nomeDaFunção(nome:Tipo):TipoRetorno{}
- Funções anônimas, single-line, inline, extensões, Lambdas, ordem superior;

                                private fun getFullName(name:String, lastName:String):String{
                                        val fullName = "$name $lastName"
                                        return fullname
                               }
                               
                               private fun getFullName(name:String, lastName:String):String{
                                        return "$name $lastName"
                               }
                               
                               private fun getFullName(name:String, lastName:String) = "$name $lastName"
                               
### Funções ordem superior
- Recebem outra função ou lambda por parâmetro;
- Bastante úteis para a generalização de funções e tratamento de erros;

                                val x = calculate(12,4,::sum)
                                val y = calculate(12,4){a,b -> a*b }
                                
### Funções single-line
- Prefixo **Fun nomeDaFunção(nome:Tipo)=retorno**;
- Função de uma única linha;
- Infere o tipo de retorno;

                                private fun getFullName(name:String, lastName:String) = "$name $lastName"
                                
### Funções/extensões
- Prefixo **Fun Tipo.nomeDaFunção()**;
- Cria uma função que só pode ser chamada por um tipo específico, cujo o valor pode ser referenciado dentro da função através da palavra **this**;

                                fun String.randomCapitalizedLetter() = 
                                        this[(0..this.length-1).random()].toUpperCase()
                                        
### Estruturas de controle
- if/else, when, elvis operator;
- Pode ser utilizado tanto para controle quanto para atribuição;
- Pode ser encadeado com múltiplas estruturas;

if/else

        if(expressão){
                //bloco de código
        }else if (expressão2){
                //bloco de código
        }else{
                //bloco de código
        }
        
when 

        when {
                case1 -> {}
                case2 -> {}
                case3 -> {}
                else -> {}
        }
        
elvis operator  

        val a:Int? = null
        var number = a ?: 0
        
### Atribuição
- O valor atribuído tem que estar na última linha do bloco;
- A condicional pode não usar chaves se só fizer a atribuição

        val maxValue = if (a > b) a else if (a < b) b else b
                val minValue = if (a > b){
                        println("b($b) é o menor valor")
                        b
                }else if(a < b){
                        println("a($a) é o menor valor")
                        a
                }
                
### When 
- Equivalente ao switch de outras linguagens;
- Aceita tanto valores quanto condicionais;
- Aceita range como case;

        when {
                a > b -> {}
                a != b && a > c -> {}
                b == 0 -> {}
                else -> {}
        }
        
<br>

        when(year) {
          -4000..475 -> //Antiguidade
          476..1452 -> //Medieval
          1453..1789 -> //Moderna
          currentYear -> //ano atual
        }
        
### Elvis Operator
- O mais próximo que a linguagem possui de um operador ternário;
- Verifica se um valor é nulo e apresenta uma opção caso seja;
- Pode ser encadeado;

        val a:Int? = null
        val c:Int? = 9
        var number = a?: b?: 0
      
<br>
Nesse caso, se o valor de **a não for nulo**, number **recebe a**.
Se o valor de **a for nulo** e **b não for nulo**, number **recebe b**.
Se **a e b forem nulos**, number recebe 0.

## Estruturas de Repetição
- While, do..while, for e forEach;
- Estruturas similares às convencionais em outras linguagens;
- Aceita os comandos **in, range, untill, downTo e step**;

        while(Condição){
        }
  
<br>

        do{
           //bloco
        } while(Condição)
        
<br>

        for(i in 0..20 step 2){
                println(i)
        }
### For
- **for**(variavelIndexadora **in/untill/downTo** faixa de valores/condicional **step** intervalo)
- **in**: conta do valor inicial até o valor final estabelecido
- **untill**: conta do valor atual até o valor estabelecido menos 1;
- **downTo**: conta de maneira decrescente;
- **step**: determina o intervalo da contagem;

        for(i in 0..20 step 2){
                println(i)
        }
        
<br>

        for(i in 10 downTo 0){
                println(i)
        }
        
<br>

        for(i in 0 untill 10){
                println(i)
        }
    
<br>

        var text= "Kotlin"
        for(letter in text){
                println(letter)
        }
<br>
