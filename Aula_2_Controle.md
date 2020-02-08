# Aula 2 - Estruturas de controle

Como toda linguagem de programação, python também possui estruturas de controle de código, para garantir o fluxo de informação. 
Essas estruturas definem que blocos de códigos são executados, quantas vezes serão repetidos e reutilizados se necessário. Nessa aula veremos estruturas de decisão e repetição.

## Decisão
Execução condicional ou decisão refere a uma estrutura que permite executar parte de código baseado em uma condição lógica.
Python possui algumas estruturas de decisão, e a principal é o `if else`. Essa estrutura pode ter as seguintes formas:
* Com uma condição, duas execuções alternadas baseadas na condição ser verdadeira ou falsa
``` python
if <condição>:
  <bloco verdadeiro>
else:
  <bloco falso>
```
* Uma condição, execução baseada somente se a condição é verdadeira
``` python
if <condição>:
  <bloco verdadeiro>
```
* `N` condições, `n` execuções (o comando `elif` pode ser repetido quantas vezes forem necessárias)
``` python
if <condição 1>:
  <bloco 1>
elif <condição 2>:
  <bloco 2>
else:
  <bloco n>
```
Cada bloco é executado conforme a condição lógica, e o fluxo do programa muda conforme essas condições.
Perceba que agora a parte do dentro do bloco `if else` tem um recuo. Essa indentação indica que tudo dentro 
desse recuo pertence ao bloco da condição lógica. Python utiliza somente identação para separar os blocos,
no lugar das tradicionais chaves em outras linguagens (`{}`) tornando a leitura do código menos poluída.
Perceba também o uso de `:` para indicar o início do bloco lógico.  

Alguns exemplos de uso do `if`:
* Verificar se um número é maior que 10.
``` python
numero = input("Digite um numero\n")
numero = float(numero)
if numero > 10:
  print("o numero e maior que 10")
else:
  print("o numero nao e maior que 10") 
```
* Verificar se um nome é igual a um conjunto de usuários.
``` python
nome = input("Digite o nome\n")
if nome == "Tiago" or nome == "Rodrigo" or nome == "Anderson":
  print("Usuario no sistema")
print("Programa encerrado")
```
* Verificar se um número está entre 0 e 5, entre 6 e 10 e maior que 10.
``` python
numero = input("Digite um numero\n")
numero = float(numero)
if numero > 0 and numero <= 5:
  print("o numero esta entre 0 e 5")
elif numero > 6 and numero <= 10:
  print("o numero nao esta entre 6 e 10")
elif numero > 10:
  print("maior que 10")
else:
  print("fora dos intervalos")
```

## Repetição
Estruturas de repetição permitem que parte um código se repita de acordo com uma regra. 
Em python duas estruturas de repetição são utilizadas, uma baseada em lista e uma baseada em regra.
O `for` é uma estrutura de repetição que utiliza uma lista para fazer iterações. 
Listas vão ser melhor detalhados na aula seguinte, o importante agora é saber que é uma estrutura de dados
que tem forma sequencial. Em python são descritos com colchetes e separados por virgula.
O exemplo abaixo apresenta uma contagem de 1 até 3 utilizando uma lista com o `for`
``` python
for i in [1, 2, 3]:
    print(i)
```
O laço `for` utiliza uma variável que serve como iterador. Nesse exemplo `i` toma forma de cada um dos elementos da lista durante a execução do laço.  

O `while` é uma estrutura de repetição que utiliza um condicional para realizar iterações.
Abaixo a mesma contagem de 1 até 3 utilizando `while`.
``` python
i = 1
while i < 4:
    print(i)
    i += 1 # equivalente a i = i + 1
```
O laço executa enquanto a afirmativa for verdadeira, então deve-se tomar cuidado para não cair em uma situação de loop infinito, no qual a afirmativa sempre é verdadeira.  
Para ambos os casos, perceba o uso da indentação para separar os blocos.   

Para fins de otimização, para evitar computação inútil é possível controlar os laços com os comandos `break` e `continue`. 
O comando `break` para a execução do laço, e o comando `continue` ignora todo o resto do laço, mas continue
``` python
>>> for i in range(10):
...  if i == 3:
...    break
...  print(i)
...
0
1
2
>>> for i in range(5):
...  if i == 3:
...    continue
...  print(i)
...
0
1
2
4
```

Uma forma de criar listas é utilizando a função `range()`, que suporta até três parâmetros. Essa função auxilia na criação automtática de listas. 
* Mostra na tela a contagem de 0 até 9
``` python
# range(argumento) com 1 parâmetro: 0 até (argumento - 1), com passo 1 ([0,argumento[, intervalo fechado)
for i in range(10): 
    print(i)
```
* Mostra na tela a contagem de 1 até 10
``` python
# range(comeco,fim) com 2 parâmetros: comeco até (fim - 1), com passo 1 ([comeco,fim[)
for i in range(1,11):
    print(i)
```
* Mostra na tela a contagem de 0 até 10 de 2 em 2
``` python
# range(comeco, fim, passo_n) com 3 parâmetros: comeco até (fim - 1), com passo_n
for i in range(0,11,2):
    print(i)
```
 
## Exercícios

### Decisão
1. Escreva um script que diga se um número é par ou ímpar.

2. Escreva um script que receba dois números e imprima o menor dos dois.

3. Escreva um script que diga o conceito de um aluno baseado em uma nota.

4. Escreva um script que, para uma conta bancária, leio o seu número, o saldo, 
o tipo de operação a ser realizada (depósito ou retirada) e o valor da operação. Após, determine e mostre o novo saldo.

5. Escreva um script que receba três números e mostre na tela em ordem crescente

6. Escreva um script que receba um número e verifique se é divísivel por 6.

7. Escreva um script que receba um número e mostre qual o mês correspondente.

8. Escreva um script que receba o nome da capital do Brasil, assumindo várias grafias, e indique se está certo.

9. Escreva um script que receba cinco números e diga a quantidade de números negativos.

10. Escreva um script que receba a idade de um nadador e mostre na tela a sua categoria seguindo as regras:

| Caegoria | Idade |
| --- | --- |
| Infantil A | 5 - 7 anos |
| Infantil A | 8 - 10 anos |
| Juvenil A | 11 - 13 anos |
| Juvenil B | 14 - 17 anos |
| Sênior| maiores de 18 anos |

11. Escreva um script que recebe o nome de 2 times e o número de gols marcados na partida (para cada
time). Escrever o nome do vencedor, e caso não haja vencedor deverá ser mostrar a palavra EMPATE.

12. Um comerciante calcula o valor da venda, tendo em vista a tabela a seguir:

| Compra | Valor da Venda |
| --- | --- |
| menor que R$ 10 | Lucro de 70 % |
| entre R$ 10  e R$ 30 | Lucro de 50 % |
| entre R$ 30  e R$ 50  | Lucro de 40 % |
| maior que R$ 50 | Lucro de 30 % |

Escreva um script que possa entrar com nome do produto e valor da compra e imprimir o nome do produto e valor de venda.

13. Escreva um script que receba quatro notas de um aluno, calcule e imprima a média aritmética das notas e a mensagem de aprovado para média superior ou igual a 7.0 ou a mensagem de reprovado para média inferior a 7.0.

14.  Escreva um script para conversão de temperatura. O usuário deve escolher se
a conversão será de (1) grau Celsius para Fahrenheit ou de (2) Fahrenheit
para Celsius, e em seguida deve entrar com uma temperatura. As fórmulas de conversão estão descritas
abaixo:  
F : Temperatura em Fahrenheit; C :Temperatura em Celsius  
* Celsius-Fahrenheit: F = (9 * C + 160) / 5
* Fahrenheit-Celsius: C = (F - 32) * (5 / 9);

15. Escreva um script que implemente uma calculadora simples com 4 operações. Considere divisão por zero.


### Repetição

1. Escreva um script que mostre os números de 1 até 100, e de 100 até 1.

2. Escreva um script que mostre os todos os múltiplos de 10, de 1 até 10000.

3. Escreva um script que apresente na tela as tabuadas de 1 até 10.

4. Escreva um script que receba dois números e mostre o somatório dos números entre eles.

5. Escreva um script que mostre na tela a soma dos 200 primeiros ímpares.

6. Escreva um script que receba `n` números e tire a média entre eles.

7. Escreva um script que receba um número e mostre a média da soma de todos os números até ele.

8. Escreva um script que faça uma multiplicação entre dois números, através de sucessivas somas.

9. Escreva um script que receba um número indeterminado de valores, e conte os números entre 50 e 150.

10. Escreva um script que receba um número indeterminado de valores, e apresente o maior e menor entre eles.

11. Escreva um script que mostre todas as possibilidades de
que no lançamento de dois dados tenhamos o valor 7 como resultado da
soma dos valores de cada dado.

12. Escreva um script que mostre todos os possíveis lançamentos de três dados.

13. Escreva um script que escreva a sequência de Fibonacci até 1000.

14. Escreva um script que receba dados sobre 10 pessoas: nome, sexo (M ou F) e altura. Ao final apresente:
    * a maior e a menor altura de cada grupo
    * a media de altura das mulheres
    * o número de homens
    * o nome da mulher com a menor altura

15. Escreva um script que receba os dados sobre 15 pessoas: peso e idade. Ao final apresente:
    * média de peso
    * maior idade
Se houver alguma entrada com idade menor que 12, não deve ser considerada.

16. Escreva um script que receba a idade, a altura e o peso de 12
pessoas. Ao final apresente:
    * a quantidade de pessoas com idade superior a 50 anos
    * a média das alturas das pessoas com idade entre 10 e 20 anos
    * a porcentagem de pessoas com peso inferior a 40 quilos entre todas
as pessoas analisadas.

17. Escreva um script que receba o valor e o código de várias mercadorias vendidas em um determinado dia. Os códigos obedecem a lista abaixo:
    * "L" limpeza
    * "A" alimentação
    * "H" higiene  
Ao final apresente:
    * o total vendido naquele dia, com todos os códigos juntos
    * o total vendido naquele dia em cada um dos códigos

18. Dado um país A, com 5.000.000 de habitantes e uma taxa de natalidade de
3% ao ano, e um país B com 7.000.000 de habitantes e uma taxa de
natalidade de 2% ao ano, escreva um script que calcule o tempo necessário para que a
população do país A ultrapasse a população do país B.

19. Escreva um script que receba a idade e o estado civil (C-Casado, S-solteiro,
V-viúvo e D-divorciado) de várias pessoas. Calcule e imprima:
    * a quantidade de pessoas casadas
    * a quantidade de pessoas solteiras
    * a média das idades das pessoas viúvas
    * a porcentagem de pessoas divorciadas dentre todas as pessoas analisadas

20. Escreva um script que verifique se um número é primo ou não.

21. Escreva um script que calcule o fatorial de `n` (`n!`). Por definição `0! = 1` 

22. Uma rainha requisitou os serviços de um monge e disse-lhe que pagaria
qualquer preço. O monge, necessitando de alimentos, perguntou à rainha se
o pagamento poderia ser feito com grãos de trigo dispostos em um tabuleiro
de xadrez, de tal forma que o primeiro quadro contivesse apenas um grão e
os quadros subsequentes, o dobro do quadro anterior. A rainha considerou
o pagamento barato e pediu que o serviço fosse executado, sem se dar conta
de que seria impossível efetuar o pagamento. Escreva um script que calcule 
o número de grãos que o monge esperava receber.

23. Um marciano chegou a uma floresta e se escondeu atrás de uma das 100
árvores quando viu um caçador. O caçador só tinha cinco balas em sua
espingarda. Cada vez que ele atirava, e não acertava, é claro, o marciano
dizia: estou mais à direita ou estou mais à esquerda. Se o caçador não
conseguir acertar o marciano, ele será levado para Marte. Escreva um script para este
jogo, com dois jogadores, onde um escolhe a árvore em que o marciano irá
se esconder, e o outro tenta acertar.

