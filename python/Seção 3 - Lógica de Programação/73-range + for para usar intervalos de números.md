🗓️ Data: 13/10/2025

O segundo iterável que vamos ver é a função **range()**. Essa função não depende do `for`, e nem o `for` depende do `range()`.

```
range(start, stop, step)
```

O `range()` gera uma sequência de números inteiros e possui três argumentos simples: o início, o final e o passo.

```python
numeros = range(10)

for i in numeros:
    print(i)  # Imprime números inteiros de 0 a 9
```

* Podemos passar apenas um argumento para o `range()`. Nesse caso, o `start` será `0` e o `step` será `1`.

No código acima, o `range(10)` está armazenando um objeto que representa uma sequência de números de 0 até 9 na variável `numeros`. No `for`, estamos iterando por cada **número** desse objeto armazenado na variável.

Não precisamos armazenar o `range()` em uma variável; podemos fazer a iteração direto no `for`. Veja o exemplo abaixo:

```python
for i in range(10):
    print(i)  # Imprime números inteiros de 0 a 9
```

```python
range(10)        # Vai do 0 até o 9
range(0, 10)     # Vai do 0 até o 9, mas especificando o start
range(0, 10, 2)  # Vai do 0 até o 9, e o "2" indica que vai pular de dois em dois
```

---

## Exemplo visual

```python
print(list(range(1, 10, 2)))  # Saída: [1, 3, 5, 7, 9]
print(list(range(10)))        # Saída: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

Veja o código acima: é como se fosse uma lista, onde ele gera números de 0 a 9. É importante ressaltar que o número final (10) **nunca** é incluído.

---

## Passo negativo

```python
range(0, 10, -2)  # Retorna um range vazio
```

Lembra da aula 46 quando falamos sobre fatiamento de strings com passo negativo? Aqui funciona de forma parecida.

No exemplo acima, o início é `0` e o fim é `10`. Como o passo é `-2` (indo para trás), ele **não consegue encontrar nenhum número**, porque estamos tentando ir do menor para o maior “indo para trás”. Por isso o resultado é um range vazio.

Para que o passo negativo funcione, o **início precisa ser maior que o fim**, assim ele realmente vai “para trás”:

```python
range(0, -10, -2)  # Saída: [0, -2, -4, -6, -8]
```

---