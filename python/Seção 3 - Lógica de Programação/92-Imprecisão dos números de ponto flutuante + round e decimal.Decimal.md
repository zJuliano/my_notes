🗓️ Data: 20/10/2025

```python
numero_1 = 0.1
numero_2 = 0.7
numero_3 = numero_1 + numero_2
print(numero_3)
```

Veja o código acima, um códigos simples que soma `0.1` + `0.7` e imprime a sua soma que é `0.7999999999999999`. Um número do tipo `float` com várias casas decimais
Nós já vimos como formatar esse número ocultando as casas decimais com f-string, que é utilizando o `f"{numero_3:.2f}"`. Ou seja, a gente formata o resultado final direto na string

Mas também existe uma outra maneira em Python que é utilizando uma função chamada `round()`. Ao invés de formatar na string, você iria formatar utilizando a função

---

## Função `round()`

A função `round()` é responsável por **arredondar** números flutuantes para o valor mais próximo.

* Seu primeiro argumento, deve ser o número que será arredondado
* Segundo argumento, a limitação de casas demais
* Com apenas o primeiro argumento, arredonda para um número inteiro mais próximo

```python
numero_1 = 0.1
numero_2 = 0.7
numero_3 = numero_1 + numero_2
print(numero_3, round(numero_3, 5)) # 0.8
print(round(3.2923298, 2)) # 3.29233
```

No caso do primeiro print, a sua soma de `0.1` + `0.7` é `0.7999999999999999`. O que a função `round(numero_3, 5)` está fazendo é **arredondar** para o mais próximo, que é 0.8

* Se forçarmos a exibição das casas decimais com f-string, `f"{numero_3:.5f}"` irá exibir `0.80000`.
* Veja que depois do 8 é sempre 0, e por isso, mesmo que passamos `round(numero_3, 5)` informando que terá 5 casas decimais, como depois do 8 é sempre zero, ele vai mostrar sempre 0.8 independente da quantidade de casas que você tentar limitar.
* Agora, se passar somente um argumento, ele vai exibir imprimir `1`, como vimos, com apenas um argumento ele arredonda para o número inteiro mais próximo dele, que é 1.

---

## Módulo decimal

Quando lidamos com o tipo `float`, o Python armazena os números em **formato binário (base 2)**. O problema é que alguns números decimais simples, como `0.1` e `0.7`, **não podem ser representados exatamente em binário**, o que causa pequenas imprecisões. Por isso, a soma de `0.1 + 0.7` resulta em `0.7999999999999999` ao invés de `0.8` de forma exata.

O módulo `decimal` resolve esse problema porque trabalha com **base 10**, assim como fazemos na matemática comum. Com ele, o Python trata `0.1` e `0.7` como valores exatos, sem aproximações. Para que essa precisão funcione corretamente, é importante criar o número a partir de uma string, e não de um float.

Exemplo:

```python
from decimal import Decimal

numero_1 = Decimal("0.1")
numero_2 = Decimal("0.7")
numero_3 = numero_1 + numero_2
print(numero_3) # 0.8
```

Note que agora a soma é **exata**, pois não há conversão prévia para `float` e portanto, não existe o erro de representação
