🗓️ Data: 11/10/2025

No Python, temos o método `count()` de uma string, onde retorna um número inteiro da quantidade de caracteres que uma string possui.

```python
frase = "Olá, como você está?"
quantidade = frase.count("o")
print(quantidade) # Saída: 3
```

Lembrando, letras maiúsculas e minúsculas fazem diferença. Veja, no código acima, existe 1 letra maiúscula e 3 letras minúsculas. Eu pedi o `count("o")` da letra minúscula, então retornou `3`. Agora, se eu pedisse `count("O")`, retornaria `1`.

Uma forma de resolver esse problema é convertendo a string toda para minúsculo ou para maiúsculo, com o método `lower()` para converter em minúsculo ou `upper()` para converter para maiúsculo.

```python
frase = "Olá, como você está?".lower()
quantidade = frase.count("o")
print(quantidade) # Saída: 4
```

---

## Checando quantidade de letras

```python
frase = "O Python é uma linguagem de programação multiparadigma. Python foi criado por Guido Van Rossum"

i = 0
qtd_vezes = 0

while i < len(frase):

    letra = frase[i]
    quantidade = frase.count(letra)

    print(letra, quantidade)

    i += 1
```

Aqui, no código acima, estamos **iterando** pela string. Não vou comentar todo o processo do while, porque a gente já sabe. Então, basicamente, cada repetição:

* `letra` recebe `frase[i]`: Armazena a letra individual de cada índice durante cada repetição.
* `quantidade` recebe `frase.count(letra)`: Conta quantas vezes que `letra` atual, durante a repetição, aparece na string, retorna um número inteiro e armazena em `quantidade`.
* `print(letra, quantidade)`: Imprime a letra atual da repetição e a quantidade de vezes que ela aparece.
* `i += 1`: Faz a operação de soma composta.

Resumindo, vai imprimir no console a letra atual coletada na repetição e quantas vezes ela aparece.

---

## Verificando qual é a maior letra da string

Agora, a única coisa que precisamos fazer para saber qual letra apareceu mais vezes é fazer uma condição verificando se a quantidade de letras atual, durante a repetição, é **maior** que a quantidade de letras da repetição **anterior**.

```python
frase = "O Python é uma linguagem de programação multiparadigma. Python foi criado por Guido Van Rossum".lower()

i = 0
qtd_vezes = 0

while i < len(frase):

    letra = frase[i]
    quantidade = frase.count(letra)

    if qtd_vezes < quantidade:
        qtd_vezes = quantidade
        
    i += 1
print(qtd_vezes)
```

Primeiro, declaramos uma variável **fora** do bloco do while.

* `qtd_vezes` recebe `0`.

  * Por quê? No momento da repetição, a variável será alterada. `0` porque será um número inteiro, que é o retorno do `count()`.
* Depois, fizemos a verificação: **SE** `qtd_vezes` for **MAIOR** que `quantidade`:

  * A variável `qtd_vezes` é alterada com o valor da quantidade de caracteres, ou seja, deixando de ser o número `0` para a quantidade de vezes que o caractere verificado existe dentro da string.
  * No caso acima, a letra "o" é o segundo caractere que mais tem, 10 vezes. O primeiro é o espaçamento (` `), que aparece exatas 14 vezes.
  * Ou seja, na primeira repetição, `qtd_vezes` irá armazenar o número 10 da letra "o", e na segunda repetição, irá verificar o próximo caractere, que é o espaço vazio. O espaço vazio está presente 14 vezes, ou seja, a condição será verdadeira por `qtd_vezes` ser **MENOR** que `quantidade` e irá armazenar o número `14` na variável `quantidade`.
  * E ficará nesse **loop** até o fim da repetição. Como o caractere mais presente é o espaço vazio, em todas as outras verificações da condição durante a repetição, o `if` será falso, e o valor final de `qtd_vezes` será `14`.
* No final do loop, existe um print que imprime `qtd_vezes`, que só irá imprimir o valor da variável, que é `14`.

---

### Removendo o espaçamento como caractere

Agora, vamos remover a exibição desse caractere vazio. Queremos contar letras e não o espaço vazio. Para isso, acima da condição `if qtd_vezes < quantidade:`, é só adicionar uma condição verificando se, durante a iteração, houver um espaço vazio na string. É só **pular**.

```python
if letra == ' ':
    i += 1
    continue
```

Então, no código acima, se durante a iteração `letra` for um espaço vazio, ele vai fazer a soma composta e depois vai dar um `continue` (pular esse laço).

* Por quê antes do `continue` está fazendo a operação composta?

  * Porque, se não, o `i` sempre será `0`. Consequentemente, a condição do `while i < len(frase):` sempre será **verdadeira** e ficará em um loop infinito.
  * E, como está **pulando** a repetição, não está chegando na operação composta no final do while. Vai ficar sempre checando o mesmo índice, que é o espaçamento, e ficando no loop infinito.

---

### Código completo:

```python
frase = "O Python é uma linguagem de programação multiparadigma. Python foi criado por Guido Van Rossum".lower()

i = 0
qtd_vezes = 0
letra_vezes = ''

while i < len(frase):

    letra = frase[i]
    quantidade = frase.count(letra)

    if letra == ' ':
        i += 1
        continue

    if qtd_vezes < quantidade:
        qtd_vezes = quantidade
        letra_vezes = letra

    i += 1
print(f'A letra "{letra_vezes}" apareceu {qtd_vezes} vezes')
```

No código acima, definimos uma variável de string vazia `letra_vezes` fora do bloco do while, e na condição de verificar `if qtd_vezes < quantidade`, além de mudar o valor da variável `qtd_vezes`, também estamos fazendo a atribuição da letra atual com a string vazia. Ficando:

```
Saída do print: A letra "o" apareceu 10 vezes.
``