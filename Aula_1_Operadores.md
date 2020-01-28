# Aula 1 - Tipos, Operadores e Entrada e Saída

Python é uma linguagem de programação multiparadigma de alto nível e dinamicamente tipada. Código em python parece muito com pseudo-código, permitindo expressar ideias com poucas linhas de código, ainda sendo legível. Abaixo segue o exemplo do Bubble sort em python:
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

```
C:\Users\Tiago>python
Python 3.6.8 (tags/v3.6.8:3c6b436a57, Dec 24 2018, 00:16:47) [MSC v.1916 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> 
```

Nativamente alguns tipos de dados básicos são acessíveis: inteiros, reais, strings e lógicos. Para todos os tipos de dados o operador `=` é utilizado para realizar atribuição de um valor para um espaço de memória, uma variável.
Os operadores para números são: 
* `+`, `-`  para adição e subtração
* `*`, `**` para multiplicação e potenciação
* `/`, `//`, `%` para divisão real, inteira e módulo

Para variáveis lógicas:
* `and`, `&` para `e` 
* `or`, `||` para `ou`
* `not`, `!` para `não`
 
Abaixo algumas operações utilizando o modo interativo
``` bash
x = 3
print(type(x)) 
print(x)       
print(x + 1)   
print(x - 1)   
print(x * 2)   
print(x ** 2) 
x += 1
print(x)  
x *= 2
print(x)  
y = 2.5
print(type(y)) 
print(y, y + 1, y * 2, y ** 2)  
nome = "tiago"
print(type(nome))
```

# Exerícios

1. 

2. 

3. 

4.

5.

6.

7.


