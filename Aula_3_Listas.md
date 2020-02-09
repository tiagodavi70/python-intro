# Aula 3 - Listas e funções

Python oferece estruturas de dados específicas para manipulação de dados, assim como meios de retutilizar trechos de código. Nessa aula alguns desses métodos serão apresentados. Os termos lista e vetor são utilizados de forma intermitante pra se referir a lista.


## Estrutura de dados
A lista é a estrutura de dados mais versátil em python, e descreve os itens como valores separado por vírgula. Listas podem conter itens de tipos diferentes, mas normalmente tem o mesmo tipo.
Assim como uma string, é possível acessar os valores individuais de uma lista através de um índice. Índices em python começam a contagem em 0. 

``` python
>>> xs = [3, 1, 2]    # Cria uma lista
>>> print(xs, xs[2])  # Mostra a lista toda e apenas o terceiro elemento.
[3, 1, 2] 2
>>> print(xs[-1])     # Indíces negativos contam do fim da fila
2
>>> xs[2] = 'foo'     # Outro tipo
>>> print(xs)
[3, 1, 'foo']
>>> xs.append('bar')  # Adiciona um novo item ao fim da fila
>>> print(xs)
[3, 1, 'foo', 'bar']
>>> x = xs.pop()      # Retira o último elemento da lista
>>> print(x, xs)
bar [3, 1, 'foo']
>>> len(x)            # Função para descobrir o tamanho de uma lista (importante para iteração em um laço for)
3
>>> xs.append(5)      # Função para adicionar elemento na lista      
>>> print(xs)
[3, 1, 'foo', 5]      
```

Assim como uma lista pode ter tipos diferentes, também pode conter outras listas. A construção dessas listas
com tipos numericos nos permite a construção de matrizes.
``` python
>>> a = [[1,2,3],[4,5,6],[7,8,9]]
>>> print(a)
[[1, 2, 3], [4, 5, 6], [7, 8, 9]]
>>> print(a[1])
[4, 5, 6]
>>> print(a[1][1])
5
>>> a[2].append(10)
>>> print(a[2][-1])
10
```

Em adiçao ao acesso individual dos elementos de uma lista, python dispõe de uma sintaxe de acesso de sublistas.
Essa técnica é conhecida como slicing.
``` python
>>> nums = list(range(5))     # criando uma lista de inteiros
>>> print(nums)
[0, 1, 2, 3, 4]
>>> print(nums[2:4])          # Sublista do índice 2 até 4 (fechado)
[2, 3]
>>> print(nums[2:])           # Sublista de 2 até o fim
[2, 3, 4]
>>> print(nums[:2])           # Sublista do início até 2 (exclusivo)
[0, 1]
>>> print(nums[:])            # Lista = Sublista
[0, 1, 2, 3, 4]
>>> print(nums[:-1])          # Índices podem ser negativos
[0, 1, 2, 3]
>>> nums[2:4] = [8, 9]        # Atribui novos valores para a sublista
>>> print(nums)
[0, 1, 8, 9, 4]      
```

Além das listas, python dispõe também de mais duas importantes estruturas de dados: dicionarios e tuplas.
Um dicionário é uma estrutura chave-valor, em que as chaves tem que ser únicas. Uma tupla é uma sequência imutável, e funciona como uma lista, inclusive com indexação e slicing.

``` python
>>> dic = {"nome":"Tiago", "idade":27}
>>> print(dic["nome"], dic["idade"])
Tiago 27
>>>
>>> tupla1 = (1, 2, 3)
>>> tupla2 = ('ufpa', 'labvis', [1,2], 5)
>>> print(tupla1[2])
3
>>> print(tupla2[0], tupla2[2:])
ufpa ([1, 2], 5)
```

Seguem exemplos com vários conceitos aplicados:
* Soma de dois vetores
``` python
>>> a = [1,2,3]
>>> b = [4,5,6]
>>> c = [] # resultado da soma
>>> if len(a) == len(b): # verifica se os vetores tem o mesmo tamanho
...     for i in range(len(a)): # laço de 0 até o tamanho do vetor
...         soma = a[i] + b[i]
...         c.append(soma)
...
>>> print(c)
[5, 7, 9]
```
* Soma de um escalar em uma matriz (`a + M`)
``` python
a = [[1,2],[3,4]]
b = 5
for i in range(len(a)):          # iteração na primeira lista
    for j in range(len(a[i])):   # iteração em cada lista subsequente
        a[i][j] += b

print(a)
```
* Escreva um script que faça um cadastro de funcionários de uma empresa, e mostre um relatorio com folha de pagamento.
``` python
funcionarios = [] # inicia um vetor para salvar os funcionários 
opcao = 1
while opcao != 0:
    print("Digite o código para uma ação")
    print("1 - Cadastrar funcionário")
    print("2 - Gerar relatório")
    print("0 - Sair")
    opcao = int(input("Opção: "))
    if opcao == 1:
        nome = input("Digite o nome do funcionário: ")
        salario = float(input("Digite o salário do funcionário: "))
        funcionarioNovo = {"nome": nome, "salario": salario}
        funcionarios.append(funcionarioNovo)
    elif opcao == 2:
        if len(funcionarios) == 0:
            print("Sem funcionários para gerar relatório")
        else:
            somaSalarios = 0
            for i in range(len(funcionarios)):
                somaSalarios += funcionarios[i]["salario"]
                print(  "Nome: ", funcionarios[i]["nome"],
                        "| Salario: R$ ", funcionarios[i]["salario"])
            print("Total: R$", somaSalarios)
    print()
```

## Função e módulos

Uma função é um trecho de código que recebe argumentos, tem uma saída e pode ser reutilizado. 
Algumas funções nativas de python já foram apresentadas aqui, como `print()`, `int()`, `str()`, `float()` e `range()`.
Além de utilizar as funções nativas do python, é possível declarar as próprias funções do seguinte modo:
``` python
def nomeDaFuncao(argumentos):
    <bloco funcao>
```
Exemplos:
* Retornar o maior número entre dois números:
``` python
def max(a,b):
    if a >= b:
        return a
    else:
        return b

>>> print(max(15,20))
20
>>> print(max(5,33))
33
>>> print(max(-15,8))
8
>>> print(max(105,-20))
105
>>> print(max(13,2))
13
```
* Verificar nomes em uma lista.
``` python
def verificarNomes(nome, lista):
    for n in lista:
        if nome == n:
            print(nome + " está na lista")
            return # return sem parâmetro encerra a função
    print(nome + " não está na lista")

>>> lista = ["anderson", "yvan", "rodrigo", "gustavo", "diego"]
>>> verificarNomes("tiago",lista)
tiago não está na lista
>>> verificarNomes("nelson",lista)
nelson não está na lista
>>> verificarNomes("yvan",lista)
yvan está na lista
>>> verificarNomes("diego",lista)
diego está na lista
```

Além das funções nativas, python também oferece alguns módulos de forma nativa. Uma bibilioteca é um conjunto de funções e classes que podem ser reutilizados, são declarados em arquivos diferentes e devem ser referenciados. Um módulo deve ser importado utilizando a palavra chave `import` seguindo do nome do módulo. O módulo `random` pode gerar valores aleatórios entre `[0.0, 1.0[`. 

``` python
>>> import math
>>> import random
>>> print(math.sqrt(64))
8.0
>>> random.random()
0.6394674400753039
```
Depois de importar o módulo, é possível acessar os elementos da classe com `.`. Assim como as funções, é possível criar os próprios módulos. Seguindo o exemplo:
``` python
# em uma pasta, crie um arquivo com nome modulo.py com essa função
def hello(nome):
    print("Olá " + nome + "!")

def bye(nome):
    print("Até mais " + nome + "!")
```
Utilizando `import modulo` a função `hello` fica disponível para utilização tanto por scripts quanto no modo interativo.
``` python
# na mesma pasta crie outro arquivo, ou no modo interativo
>>> import modulo
>>> modulo.hello("Tiago")
Olá Tiago!
>>> modulo.bye("Tiago")
Até mais Tiago!
```

De forma alternativa, sem importar todas as funções do módulo:
``` python
>>> from modulo import hello
>>> hello("Tiago")
Olá Tiago!
```

## Exercícios

1. Escreva um script que receba dez nomes do usuário, armazene-os em uma lista e ao final mostre a listagem, indicando a ordem de entrada de cada nome.

2. Escreva um script que crie um vetor com 10 posições e receba seus valores do usuário. Ao final deverá mostrar somente os valores acima da média.

3. Escreva um script que crie uma lista com 5 nomes para guardar. O vetor deve ser preenchido pelo usuário e ao
final deve ser feita uma consulta com um novo nome para saber se ele está ou não cadastrado.

4. Escreva uma função que dado um crie um vetor com `n` posições aleatórias.

5. Escreva um script que mostre na tela os quadrados de 1 até 15.

6. Escreva um script que crie um vetor com 20 valores inteiros aleatórios (entre 0 e 999).

7. Escreva um script que dado dois vetores indique os elementos que estão presentes nos dois vetores.

8. Escreva uma função que dado um vetor calcule sua somatório e média.

9. Escreva uma função que adicione um valor em um vetor somente se ele não estiver presente.

10. Escreva um script que receba um vetor e normalize seus valores entre `[0.0, 1.0[`

11. Escreva um script que receba um valor `n` de altura e desenhe um triângulo dessa altura na tela
```
Altura: 3
  *
 ***
*****
Altura: 4
   *
  ***
 *****
*******
```

12. Escreva uma funçao que multiplique dois vetores.

13. Escreva um script quer faça o controle de estoque de uma loja. Em um menu deve ter as opções:
    * cadastrar produto
    * editar produto
    * vender pruduto
    * gerar relatório
Na opção de cadastro o usuário deve entrar com:
    * nome do produto
    * preço
    * tipo  
Para cada produto cadastrado deve ser gerado um código.  
Na opção de editar deve permitir atualização do nome do produto.  
Na opção vender produto deve registrar uma venda do produto.  
E na opção gerar relatório deve mostrar o valor total ganho e 


14. Escreva uma função que dado uma tupla `(m,n)` retorna uma matrix `M` com `m` linhas 
e `n` colunas de valores aleatórios.

15. Escreva um script que receba uma matrix `(m,n)` e calcule seu somatório e média.

16. Escreva um script que receba uma matrix `(m,n)` e para cada linha retorne minínimo e máximo.

17. Escreva uma função que receba uma matrix `(m,n)` e para cada linha retorne média e somatório.

18. Escreva um script que receba uma matrix `(m,n)` e crie um vetor de tamanho `n` com os maiores valores de cada coluna.

19. Escreva um script que receba uma matrix `(m,n)` e crie um vetor de tamanho `m` com o menor valor de cada linha.

20. Escreva um script que dado 3 matrizes `A`, `B` e `C` calcule `A + B + 4 + C`.

21. Escreva um script que crie uma matriz `(3x6)` com valores aleatórios reais. Ao final deverá:
    * mostrar os valores da matriz;
    * pedir um valor real do usuário;
    * multiplicar todos os valores pelo valor fornecido pelo usuário;
    * mostrar novamente os valores da matriz.

22. Escreva um script que crie uma matriz 4x4 com valores aleatórios reais. Ao final deverá:
    * Mostrar os valores da matriz;
    * Mostrar o valor e a posição do maior elemento;
    * Mostrar o valor e a posição do menor elemento.

23. Escreva um script que dado uma matriz `(3x3)` retorne:
    * a diagonal principal
    * diagonal secundária
    * o maior valor
    * o menor valor
    * todos os elementos acima da diagonal principal

24. Escreva uma função que multiplique duas matrizes. 

25. Escreva uma função que ordene os elementos de um vetor em ordem crescente.  
