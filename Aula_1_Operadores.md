# Aula 1 - Tipos, Operadores e Entrada e Saída

Python é uma linguagem de programação multiparadigma de alto nível e dinamicamente tipada. O código em python parece muito com pseudo-código, permitindo expressar ideias com poucas linhas de código, ainda sendo legível. Abaixo segue o exemplo do Bubble Sort em python:
``` python
def bubble_sort(lista):
    elementos = len(lista) - 1
    ordenado = False
    while not ordenado:
        ordenado = True
        for i in range(elementos):
            if lista[i] > lista[i + 1]:
                lista[i], lista[i + 1] = lista[i + 1], lista[i]
                ordenado = False        
                print(lista)
    return lista
```
Python dispõe de dois modos, um modo interativo, acessível utilizando o executável `python` na linha de comando, e um modo de execução de scripts, disponível através de `python <caminho do script> <argumentos>`. Em windows o modo interativo deve aparecer desse modo:
``` console
C:\Users\Tiago>python
Python 3.6.8 (tags/v3.6.8:3c6b436a57, Dec 24 2018, 00:16:47) [MSC v.1916 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> 
```

Nativamente alguns tipos de dados básicos são acessíveis: inteiros, reais, strings e lógicos. 
``` 
1, 2, 19, 3000 podem ser inteiros, não tem parte real
1.56, 5.01, .4, 0.0005 são reais, já que tem parte de ponto flutuante
"tiago", "labvis", "computação" são strings, um tipo de texto
True, False são lógicos, indicando verdadeiro e falso
```

Para todos os tipos de dados o operador `=` é utilizado para realizar atribuição de um valor para um espaço de memória, uma variável.
Os operadores para números são: 
* `+`, `-`  para adição e subtração (`+` também pode ser utilizado para concatenar strings)
* `*`, `**` para multiplicação e potenciação
* `/`, `//`, `%` para divisão real, inteira e módulo

Para variáveis lógicas:
* `and`, `&` para `e` 
* `or`, `||` para `ou`
* `not`, `!` para `não`  

Para comparações de números (retorna um valor lógico):
* `==` para o sinal de igual (vale para strings)
* `<`, `<=`, `>`, `>=` para menor que, menor e igual que, maior que e maior e igual que.

Algumas operações podem ser descritas em pequenos trechos de código e reutilizadas em formas de funções. Uma função em python é utilizada na forma `<nome_da_função>(<argumentos>)`. O símbolo `#` indica um comentário, ou seja, tudo após o símbolo não é incluído na execução dos comandos, e é utilizado para apontar algum detalhe dentro do código. Abaixo algumas funções comuns nativas da linguagem:
``` python
print(<arg>) # apresenta <arg> na tela
input(<arg>) # espera uma entrada do usuário e mostra <arg>  na tela
float(<arg>) # converte <arg> em um número real
int(<arg>) # converte <arg> em um número real
str(<arg>) # converte <arg> em uma string
```

Abaixo algumas operações utilizando o modo interativo. 
``` python
>>> x = 3
>>> print(x)
3
>>> print(x + 1)
4
>>> print(x - 1)
2
>>> print(x * 2)
6
>>> print(x ** 2)
9
>>> x += 1 # equivale a x = x + 1
>>> print(x)
4
>>> x *= 2 # equivale a x = x * 2
>>> print(x)
8
>>> y = 2.5
>>> print(y, y + 1, y * 2, y ** 2)
2.5 3.5 5.0 6.25
>>> nome = "tiago"
>>> print(nome)
tiago
>>> print(x > y)
True
>>> print(x == y)
False
>>> print(x == 2 or y == 8)
False
>>> print("python" == "javascript")
False
>>>     
```

Para utilizar scripts, crie um arquivo com a extensão `py` e utilize o executável `python` com o script como argumento. Em python, para utilizar uma string sem declarar variável basta escrever o texto entre `""`. Crie o arquivo aula_1.py com o seguinte conteúdo:

``` python
a = 10
b = 20
print("a + b == ", a + b)
```
Na mesma pasta do script execute o seguinte comando no terminal: `python aula_1.py`. Para receber a entrada de um usuário utilize a função `input()`.

``` python
a = input("Digite o primeiro número\n") # \n é utilizado para gerar uma nova linha
a = float(a)
b = input("Digite o segundo número\n")
b = float(b)
print("Soma: ", a, " + ", b, " = ", a + b)
```

# Exerícios


1. Utilizando o modo interativo escreva `Olá mundo <nome>` trocando `nome` por seu nome.

2. Utilizando o modo interativo declare duas variáveis e multiplique-as.

3. Utilizando o modo interativo calcule a área de um retângulo de altura 10 e largura 15. (Area = altura x largura)

4. Escreva um script que receba uma entrada do usuário e escreva `Bem vindo <nome>`, trocando o nome pela entrada.

5. Escreva um script que receba dois números do usuário e multiplique um pelo outro.

6. Escreva um script que receba `x` e calcule `y = 3*x + x**4`

7. Escreva um script que receba três nomes e mostre na tela da ordem reversa da entrada.

8. A tabela verdade de valores lógicos apresenta o resultado de um conjunto de operações baseado em todas as possíveis entradas. A seguinte tabela verdade expressa a operação lógica `E`:

| a | b | E |  
| --- | --- | --- |  
| V | V | __V__ |  
| V | F | __F__ |  
| F | V | __F__ |  
| F | F | __F__ |  

Escreva um script que realize as operações e apresente o resultado da tabela verdade do operador `OU`.

9. Escreva um script que receba 3 valores e imprima a média entre eles.

10. Escreva um script que receba um valor entre 0 e 60 e imprima seu sucessor, sabendo que nesse problema o sucessor de 60 é 0.

11. Escreva um script que receba um número e escreva na tela a tabuada de multiplicação dele.

12. Escreva um script que receba o valor do salário de um funcionário e o valor do salário mínimo. Calcule e mostre quantos salários mínimos ganha esse funcionário.

13. Escreva um script que receba o salário de um funcionário, calcule e imprima o valor do imposto de renda a ser pago, sabendo que o imposto equivale a 5% do salário.

14. Sabe-se que o quilowatt de energia custa 2% do salário mínimo. Escreva um script que receba o valor do salário mínimo e a quantidade
de quilowatts gasta por uma residência. Calcule e imprima:
* o valor, em reais, de cada quilowatt;
* o valor, em reais, a ser pago por essa residência;
* o novo valor à ser pago por essa residência, se for dado um desconto de 15%

15. Escreva um script que receba 4 números e apresente o somatório deles.

16. Escreva um script para calcular e mostrar o valor da conversão de uma quantia em dólares para reais. Crie variáveis para
guardar o valor da cotação do dólar do dia, o valor em dólares e o valor do resultado da conversão.

17. Escreva um script que receba um número no format CDU e converta para UDC (ex. 321 vira 123). 

18. Escreva um script que receba o valor de um produto, e para cada R$ 100,00 dê um desconto de 0,05%.

19. Escreva um script que receba uma temperatura em graus Celsius e converta para graus Fahrenheit. (`F = (9*C + 160) / 5`)

20. Um trem se locomove há 150 km/h, e funciona por 20 horas por dia. A cada 2.000 km ele deve parar 6 horas para manutenção. Cada manutenção custa R$ 2.000,00 e a cada 3 dias é cobrada uma taxa de R$ 5.000,00 de uso da ferrovia. Escreva em um script que receba o número de dias e escreva na tela um relatório, com o número de kilômetros percorridos e manutenções realizadas, assim como o custo total.

