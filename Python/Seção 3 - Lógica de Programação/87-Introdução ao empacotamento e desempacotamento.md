🗓️ Data: 18/10/2025

```python
lista = ["Juliano", "Maria", "Helena"]
```

A gente sabe que o código acima é uma **lista** de nomes, ou seja, um "pacote" de valores, uma espécie de "sacola" que guarda esses nomes. Quando a gente **desempacota**, está basicamente extraindo os valores dessa lista e atribuindo cada um deles em uma variável diferente. Isso funciona com **qualquer tipo de iterável**, não só listas.

```python
lista = ["Juliano", "Maria", "Helena"]
nome1, nome2, nome3 = lista
print(nome1, nome2, nome3) # Juliano Maria Helena
```

No código acima, `nome1` recebeu o primeiro elemento, que é "Juliano", `nome2` recebeu o segundo, "Maria", e assim sucessivamente. Nós extraímos os valores da lista e atribuímos a variáveis diferentes.

```python
nome1, nome2, nome3 = ["Juliano", "Maria", "Helena"]
print(nome1, nome2, nome3) # Juliano Maria Helena
```

No outro exemplo acima acontece exatamente a mesma coisa. A diferença é que dessa vez não estamos pegando a lista através de uma variável, e sim extraindo os valores diretamente de uma lista literal.

### Erro de ValueError

Agora, digamos que a gente queira extrair somente dois valores dessa lista que possui três itens. Se você tentar fazer:

```python
nome1, nome2 = ["Juliano", "Maria", "Helena"] # ERRO
```

Gera um **erro** do tipo `ValueError: too many values to unpack (expected 2)` (muitos valores para desempacotar). Isso acontece porque há **mais valores** na lista do que variáveis para recebê-los.

Se invertermos, ou seja, colocarmos **mais variáveis** do que valores, o Python também vai gerar erro: ``ValueError: not enough values to unpack (expected 4, got 3)``

Isso significa que não há **valores suficientes** para preencher todas as variáveis.

---

### Extraindo valores específicos

Como já deu pra perceber, não dá pra colocar menos variáveis sem o mesmo número de valores. Então, se quisermos pegar apenas alguns valores e ignorar o resto, podemos usar o operador `*`.

```python
lista = ["Juliano", "Maria", "Helena"]
nome1, *resto = lista

print(nome1) # Juliano
print(resto) # ['Maria', 'Helena']
```

- `nome1` recebe o primeiro valor "Juliano"
- `*resto` empacota o **restante dos valores** em uma única variável (no caso, uma lista)
- O `*` indica que o **resto dos valores será empacotado** em uma variável

Resumindo, sempre que quisermos pegar um valor (ou alguns valores) e guardar o restante, podemos usar o `*`, como em `*resto`.

---

### Usando `_` para valores não utilizados

Porém, segundo o professor (e de acordo com boas práticas), **não é legal criar variáveis que não serão usadas**. Por isso, muitos desenvolvedores Python usam o **underline** (`_`) para indicar que aquela variável não será utilizada.

```python
lista = ["Juliano", "Maria", "Helena"]
nome1, *_ = lista
```

Nesse caso, o `*_` indica que o resto dos valores será empacotado, mas **não será usado**. O underline é apenas uma convenção para indicar isso.

```python
lista = ["Juliano", "Maria", "Helena"]
_, _, nome3, *_ = lista
print(_) # Saída: [] (lista vazia)
```

Aqui, os dois primeiros valores são ignorados com `_`, `nome3` recebe "Helena" e o `*_` empacota o resto, que nesse caso é uma **lista vazia**, já que não há mais valores sobrando.

---
