🗓️ Data: 24/10/2025

O método `.split()` divide uma string em determinado caractere passado como argumento.

```python
frase = "olha só que, coisa interessante"
lista_frases = frase.split(",")
lista_frases2 = frase.split()

print(lista_frases) # ['olha só que', ' coisa interessante']
print(lista_frases2) # ['olha', 'só', 'que,', 'coisa', 'interessante']
```

* Veja que seu retorno é uma lista. No primeiro `lista_frases`, passei como argumento a vírgula (","), e o método dividiu a frase em 2 itens de uma lista, e a vírgula não foi incluída.
* No segundo `lista_frases`, não passamos argumento nenhum, e por padrão, quando não há argumento, ele divide a string com espaçamentos.

Perceba também que, quando definimos como argumento do `.split(",")` a vírgula, toda a string depois da vírgula ficou com um espaçamento: `' coisa interessante'`. Isso acontece porque o split remove a vírgula, mas não remove o espaço que vem depois dela.

```python
lista_frases = frase.split(", ") 
print(lista_frases) # ['olha só que', 'coisa interessante']
```

Agora, no código acima, estamos separando a frase com vírgula e um espaço vazio, que seria o espaço que vem depois dela. E aí, toda vez que tiver uma vírgula e um espaço, ele vai cortar e dividir a string, como já vimos, e não vai ficar `' coisa interessante'`.

---

## Remover espaçamentos

Podemos remover espaçamentos com outro método de string, que é o `.strip()`. O método `.strip()` por padrão remove espaçamentos da esquerda e da direita, ou seja, dos dois lados.

Mas também temos:

* `.lstrip()` - Remove os espaçamentos da esquerda.
* `.rstrip()` - Remove os espaçamentos da direita.

```python
frase = "  olha só    que,    coisa    interessante  "
lista_frases = frase.split(",")

print(lista_frases) # ['  olha só    que', '    coisa    interessante  ']
```

No código acima, estamos dividindo a `frase` pela vírgula. Perceba que contém muitos espaçamentos na string.

```python
frase = "  olha só    que,    coisa    interessante  "
lista_frases = frase.split(",")

for i, valor in enumerate(lista_frases):
    lista_frases[i] = lista_frases[i].strip()

print(lista_frases) # ['olha só    que', 'coisa    interessante']
```

E agora, no código acima, estamos fazendo um for enumerado pela `lista_frase`, onde no momento da repetição, `lista_frases` recebe ela mesma, porém aplicando o `.strip()`, ou seja, removendo os espaçamentos tanto da esquerda quanto da direita.

Veja que sua saída contém os espaçamentos da esquerda e da direita removidos.

### `.lstrip()`

Agora, o mesmo código acima, porém utilizando o `.lstrip()`, sua saída é:

```
['olha só    que', 'coisa    interessante  ']
```

Perceba que o espaçamento da esquerda `"  olha"` foi removido, e o da direita continua com espaçamento.

### `.rstrip()`

Com o `.rstrip()` é ao contrário, o espaçamento da esquerda é mantido, e o da direita é removido:

```
['olha só    que', 'coisa    interessante  ']
```

---

## Observação importante sobre mutações

```python
frase = "  olha só    que,    coisa    interessante  "
lista_frases = frase.split(",")

for i, valor in enumerate(lista_frases):
    lista_frases[i] = lista_frases[i].strip()

print(lista_frases) # ['olha só    que', 'coisa    interessante']
```

Voltando nesse código, onde estamos iterando pela `lista_frases` e alterando o valor dela mesma, só que com os espaçamentos removidos com o método `.strip()`.

De acordo com o professor, não é legal alterar os valores dessa forma profissionalmente, pois muito provavelmente em algum momento você pode precisar dos valores antigos dessa lista. E no código acima não está tendo essa possibilidade, pois estamos alterando o valor dela mesma.

Então, o ideal no caso acima seria passar os valores da lista antiga para uma lista nova.

```python
frase = "  olha só    que,    coisa    interessante  "
lista_crua = frase.split(",")

lista_frases = []
for i, valor in enumerate(lista_crua):
    lista_frases.append(lista_crua[i].strip())

print(lista_crua) # ['  olha só    que', '    coisa    interessante  ']
print(lista_frases) # ['olha só    que', 'coisa    interessante']
```

No código acima, veja que mudamos o que antes era `lista_frases` padrão para `lista_crua`, criamos uma `lista_frases` vazia, e depois, no momento da iteração com for, passamos o valor de `lista_crua` para a nova `lista_frases` com os espaçamentos removidos.

E agora temos os valores antigos com `lista_crua` e a lista nova com `lista_frases`, e com os espaçamentos removidos.

## Unindo string com o método `.join()`

* O método `.join()` sempre começa com uma string, pois é a string que define qual será o separador.
* Como argumento do `.join()`, você vai passar algum iterável, como tuplas, listas, string, etc. (Se tentar passar um número, que não é iterável, vai dar erro.)

```python
frases_unidas = "-".join("abc")
print(frases_unidas) # Saída: 'a-b-c'
```

* Veja o código acima, definimos o separador `-` e passamos como argumento literal uma string (que já sabemos que é um iterável).
* E, para cada iterável, o join acrescentou o separador `-`, ficando `a-b-c`.

```python
frase = "  olha só    que,    coisa    interessante  "
lista_crua = frase.split(",")

lista_frases = []
for i, valor in enumerate(lista_crua):
    lista_frases.append(lista_crua[i].strip())

frases_unidas = "-".join(lista_frases)
print(frases_unidas) # olha só    que-coisa    interessante
```

Agora, no código acima, cortando todo o processo do for, removendo espaçamentos, etc., na linha 8, onde estamos passando `"-".join(lista_frases)`:

* O que estamos fazendo é acrescentando o separador `-` para cada iterável de `lista_frases`.
* Que já sabemos que é `olha só    que` e `coisa    interessante`.
* Resultando em `olha só    que-coisa    interessante`.

---
