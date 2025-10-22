🗓️ Data: 14/10/2025

Agora vamos ver algo muito importante e muito utilizado, que é o tipo `list`. Atualmente só vimos a string, onde já sabemos que uma string é uma cadeia de caracteres onde podemos acessar cada caractere pelo índice, seja pelo índice negativo ou positivo.

```python
#        +01234
#        -54321
string = 'ABCDE'  # 5 caracteres (len)
```

O tipo `list` é uma lista de coisas, por exemplo, uma lista de nomes. Como a gente tem um pouco mais de afinidade com JavaScript, de acordo com o professor, o tipo `list` em Python seria o `Array` do JavaScript.

Assim como temos o `str(1)` que converte para string, também temos o `list()` que converte para uma lista. Importante ressaltar que nem tudo pode ser convertido pra lista, por exemplo, `list(123)` geraria um erro, porque números inteiros não são iteráveis.

A lista também é **MUTÁVEL**, ou seja, podemos mudar o valor dela. Com string, não podemos acessar o índice de uma string e alterar o valor dela, já com o `list` nós podemos.

```python
lista = []  # Lista vazia
print(type(lista))  # Saída: <class 'list'>
```

O código acima está imprimindo o tipo primitivo de `lista`, que é uma lista vazia. Assim como na string, uma lista vazia em `bool` é `False`.
Uma string com qualquer caractere (incluindo espaçamento) é `True`. Com listas funciona da mesma forma, uma lista vazia tem seu `bool` como `False`, e uma lista com algum valor é `True`.

```python
lista1 = ["Juliano"]  # Lista com valor
lista2 = []  # Lista sem valor
print(bool(lista1))  # Saída: True
print(bool(lista2))  # Saída: False
```

Em uma lista, podemos armazenar qualquer coisa, incluindo todos os valores que aprendemos até agora.

```python
#         0    1       2        3   4
#        -5    -4      -3      -2   -1
lista = [123, True, "Juliano", 1.2, []]
print(lista)  # Saída: [123, True, 'Juliano', 1.2, []]
```

Aqui no código acima, temos uma lista onde sua ordem é: `int`, `bool`, `str`, `float` e `list`.
(Também podemos ter listas dentro de listas).

E diferente da string, quando acessamos o índice pegamos o **caractere** da string. Já com `list`, nós pegamos o **valor** ou **elemento** da lista.

```python
#         0    1       2        3   4
#        -5    -4      -3      -2   -1
lista = [123, True, "Juliano", 1.2, []]
print(lista[2], type(lista[2]))  # Juliano <class 'str'>
```

- No código acima, nós definimos a lista.
- No `print`, no seu primeiro argumento, estamos pegando o valor da lista do índice `2`, que é a string "Juliano".
- Depois, no segundo argumento, estamos exibindo o **TIPO** de dado primitivo do índice `2`, que é uma string.

---

## Alterando valor da lista

Lembra que comentamos sobre alterar o valor da lista? Então:

```python
#         0    1       2        3   4
#        -5    -4      -3      -2   -1
lista = [123, True, "Juliano", 1.2, []]
lista[2] = "Maria"
print(lista[2], type(lista[2]))  # Maria <class 'str'>
```

- No código acima, estamos definindo a lista novamente.
- Veja que na declaração da lista existe a string "Juliano".
- Na linha abaixo, estamos **acessando o índice 2 da lista**, que é "Juliano", e **trocando** o valor desse índice **em específico** para "Maria".

Ou seja, no `print` irá exibir, como primeiro argumento, o item do índice `2` (trocado), que é "Maria", e depois mostrar o tipo de dado primitivo de "Maria", que, como já sabemos, é uma string.

---
