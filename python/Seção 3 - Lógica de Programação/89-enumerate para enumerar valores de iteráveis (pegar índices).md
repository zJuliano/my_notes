🗓️ Data: 20/10/2025

```python
lista = ['Maria', 'Helena', 'Luiz']
indices = range(len(lista))

for i in indices:
    print(i, lista[i], type(lista[i]))
```

No código acima, estamos fazendo um `for` em `indices`, que contém um `range` com o total de itens da lista. A variável `i` do `for` representa o **índice**.

---

### Função `enumerate[[73-range + for para usar intervalos de números]]()`

Nesta aula, o que vamos aprender é a função **`enumerate()`**, que serve para **enumerar iteráveis automaticamente**, pegando **o índice e o valor** de cada elemento sem precisar criar o `range(len(lista))`.

```python
teste = "Juliano"

for i in enumerate(teste):
    print(i)
```

**Saída:**

```
(0, 'J')
(1, 'u')
(2, 'l')
(3, 'i')
(4, 'a')
(5, 'n')
(6, 'o')
```

Repare que a saída é uma **tupla**, e com apenas **uma variável** no `for`, o Python retorna cada elemento no formato `(índice, valor)`.
Por exemplo: `(0, 'J')`, `(1, 'u')`, `(2, 'l')` e assim por diante.

---

### Usando duas variáveis no `for`

Se utilizarmos **duas variáveis**, o Python faz o **desempacotamento automático** dessa tupla:

```python
nome = "Juliano"

for i, valor in enumerate(nome):
    print(i, valor)
```

**Saída:**

```
0 J
1 u
2 l
3 i
4 a
5 n
6 o
```

Com **duas variáveis** no `for`, a primeira (`i`) representa o **índice**, e a segunda (`valor`) é o **elemento do iterável**.

---

### Aplicando o desempacotamento manualmente

Também podemos fazer o desempacotamento de forma manual, usando apenas **uma variável** no `for` e dividindo os valores dentro do loop:

```python
nome = "Juliano"

for tupla in enumerate(nome):
    indice, valor = tupla
    print(indice, valor)
```

Esse código faz **exatamente a mesma coisa** do exemplo anterior.
A diferença é que aqui fazemos o desempacotamento **dentro do loop**, enquanto o outro método desempacota **direto na estrutura do `for`**.

---

### Forma mais moderna e utilizada

De acordo com o professor, os desenvolvedores do Python pensaram:
"Por que adicionar uma linha extra se podemos fazer tudo direto no `for`?"

Por isso, o modo mais moderno, legível e utilizado é este:

```python
for i, valor in enumerate(nome):
    print(i, valor)
```

Essa forma é **a mais prática e atual** para percorrer iteráveis com seus respectivos índices.

---

💡 **Resumo:**

* `enumerate()` adiciona automaticamente um contador (índice) em cada item do iterável.
* Ele retorna uma **tupla (índice, valor)**.
* Podemos usar uma variável só (e desempacotar manualmente) ou duas variáveis diretamente no `for`.
* A forma `for i, valor in enumerate(iterável):` é a mais moderna e recomendada.

---