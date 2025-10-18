🗓️ Data: 18/10/2025

Tupla é uma lista, assim como a lista que já vimos, só que **imutável**. Ou seja, não podemos alterar o valor dela.

As listas carregam métodos que **alteram elas**, certo? `.pop()` para remover, `del` para deletar, `append()` ou `insert()` para adicionar, `extend()` para juntar duas listas, etc. Vários métodos que sempre **ALTERAM** a lista de alguma forma.

Já a tupla, não. Tupla é imutável, e o valor dela não pode ser alterado.

O jeito mais simples de definir uma tupla é simplesmente separando os valores por vírgula:

```python
nomes = "Juliano", "Maria", "Helena"
print(nomes[-1]) # Saída: Helena
```

Quando não colocamos colchetes, em Python, estamos criando um tipo de dado que é uma **tupla**, e como sabemos, uma tupla **NÃO É** mutável. Ou seja:

```python
nomes = "Juliano", "Maria", "Helena"
nomes[-1] = "Luiz"
print(nomes[-1]) # TypeError: 'tuple' object does not support item assignment
```

No código acima, estamos tentando alterar o valor do último índice da lista, que é "Helena", para "Luiz", e isso gera um erro informando que **não é possível modificar elementos de uma tupla**. Isso acontece porque essa estrutura **já é uma tupla**.

---

### Representação de uma Tupla e conversão de lista para tupla

Se quisermos ser mais específicos, podemos criar uma tupla usando parênteses:

```python
nomes = ("Juliano", "Maria", "Helena")
print(nomes[-1]) # Helena
```

Isso não muda **absolutamente nada** no código, **apenas a escrita**.

E digamos que nós queiramos converter uma **lista** para uma tupla, podemos usar a função **tuple()**:

```python
nomes = ["Juliano", "Maria", "Helena"]
print(tuple(nomes)) # ('Juliano', 'Maria', 'Helena')
```

Veja que o retorno de `tuple()` é `('Juliano', 'Maria', 'Helena')`, com os parênteses. Uma tupla pode ser definida dessa maneira, mudando apenas a forma de escrita. Mesmo que você não use os parênteses, apenas valores separados por vírgula, ainda assim será uma tupla igual.

Também podemos fazer o inverso. Ou seja, converter uma **tupla** para uma **lista** usando a função `list()`:

```python
nomes = ("Juliano", "Maria", "Helena")
print(list(nomes)) # ['Juliano', 'Maria', 'Helena']
```

Ressaltando que no código acima colocamos os parênteses, mas como vimos, **com ou sem eles**, ainda assim seria uma tupla.

* Listas são mutáveis
* Tuplas são imutáveis

---
