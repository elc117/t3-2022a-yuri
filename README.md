# Trabalho 3 - Python e a programação  funcional!

#### Yuri Morais

## Motivação
Aprender programação funcional é de extrema importância para um desenvolvedor, independente de qual a linguagem. Ela faz com seja possível escrever códigos mais limpos, escaláveis e que possam ser reaproveitados de outras maneiras, evitando assim linhas desnecessárias.

Nas últimas semanas aprendemos programação funcional em Haskell, que é uma linguagem puramente funcional. Neste trabalho, será contado como foi meu primeiro contato com programação funcional em Python.

## Desenvolvimento

Assim como em Haskell, nas funções em Python é possível receber outras funções como parâmetros, e existem algumas funções de alta ordem disponíveis também (alguns exemplos estão abaixo). Entretanto, no quesito velocidade, o haskell se sai melhor, tendo em conta que Python é uma linguagem interpretada, enquanto haskell é uma linguagem compilada.

Neste exemplo é passado como parâmetro para a função uma lista de números aleatórios e uma outra função, que será aplicada nesta lista, sendo uma para calcular seno, e outra cosseno. 

```
import numpy as np
import random

numbers_list = random.sample(range(1, 100), 5)

def do_calc(l_numbers, function):
    return function(l_numbers)

sen_list = do_calc(numbers_list, np.sin)
cos_list = do_calc(numbers_list, np.cos)
```

### Lambda
O uso de funções lambda (arrow function) em Python é uma boa prática para pequenas funções. Neste exemplo será adicionado 10 ao parâmetro enviado a função:
```
x = lambda a : a + 10
```

### Map
Neste exemplo é gerada uma lista do quadrado dos números da lista aleatória. Além disso, também foi utilizada função lambda.
```
import random

lista = random.sample(range(0, 10), 5)
lista_quad = list(map(lambda x: x**2, lista))
```

### Filter
Utilizando filter juntamente da lambda, serão selecionados somente os números maiores que 5.  (O Filter também pode ser utilizado juntamente do MAP).
```
import random

lista = random.sample(range(1, 20), 5)
lista_filter = list(filter(lambda x: x > 5, lista))
```

### ZIP
Assim como em Haskell, a função ZIP retorna uma tupla formada a partir de duas listas. 
```
lista_zip = list(zip([1,2,3], [9,8,7]))
```

### List Comprehensions 
Em python também é possível o uso de List Comprehensions, e sua sintaxe é simples.
Neste exemplo é gerada uma lista do quadrado dos números de 0 até 4. Além disso, existe um condicional para selecionar somente os números pares.
```
lista_quad_par = [x**2 for x in range(5) if x%2 == 0]
```

### Recursividade 
Neste exemplo será calculado o fatorial de um número utilizando recursividade, o que faz com que não seja necessário o uso de um laço de repetição.
```
def fatorial(num):
    if num == 1:
        return 1
    return num * fatorial(num - 1)
    
fatorial(5)
```

## Experiência
No geral foi muito interessante ver como a programação funcional está presente também em Python, e por já ter aprendido em haskell, meu primeiro contato não tive tanta dificuldade, pois a sintaxe em python é bem amigável. Neste trabalho estão presentes somente alguns exemplos, mas existem diversos outros casos em que a programação funcional inspirou Python. 


### Referências
- (https://machinelearningmastery.com/functional-programming-in-python/)

- (https://www.freelancinggig.com/blog/2019/01/07/haskell-vs-python-what-you-need-to-know/)

- (https://acervolima.com/programacao-funcional-em-python/)
