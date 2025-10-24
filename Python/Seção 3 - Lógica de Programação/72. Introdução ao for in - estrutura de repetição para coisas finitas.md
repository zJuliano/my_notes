🗓️ Data: 12/10/2025

`for` é outro laço de repetição no Python. Nas últimas aulas, vimos o laço de repetição de forma mais "complicada" para que pudéssemos aprender a lógica e como a repetição funciona. Aqui vai o código abaixo:

```python
palavra = "Python"
i = 0
while i < len(palavra):
    print(palavra[i], i)
    i += 1
```

Esse é um código onde estamos iterando pela variável `palavra`, pegando e imprimindo cada índice da string. O controlador desse `while` é a variável `i`, que no final do loop realiza uma operação de soma composta (`i += 1`) até o `i` ser igual a `len(palavra)`, onde, após isso, o while seria falso e ocorreria o fim da repetição.

De acordo com o professor, **não é comum** utilizar o `while` com coisas que a gente sabe onde termina. Nesse código, a gente sabe **claramente** quantas repetições serão executadas. O tamanho da string `palavra` tem 6 caracteres, então terão 6 execuções. Essa quantidade de repetições nunca vai mudar, terão sempre 6 execuções, começando com `i = 0` até o `i` virar `6`, onde, no `6`, o while seria falso e não executaria.

Em alguns momentos, isso pode ser aleatório. O código pode ser mudado dinamicamente durante a execução e a gente não vai saber quantas execuções de código teremos. Então, **nesses casos**, onde a gente não sabe quantas repetições nós teremos, utilizamos o `while`.

Aqui vai um exemplo logo abaixo:

```python
senha_salva = "12345"
senha_digitada = ''
repeticoes = 0

while senha_digitada != senha_salva:
    senha_digitada = input(f"Sua senha ({repeticoes}x): ")

    if senha_digitada == senha_salva:
        print("Login realizado!")
        break
    
    print("Senha incorreta!")
    repeticoes += 1
```

Nesse caso, imagine que `senha_salva` está vindo de uma base de dados e, **enquanto** o usuário digitar a senha incorreta, irá ficar no **loop**, perguntando a senha de novo e de novo. Somente quando o usuário digitar a senha correta, o login é realizado e o laço de repetição é parado. Então, **nesses casos**, onde não sabemos quantas repetições teremos, utilizamos o `while`.

## Repetição com for

O `for` já é para aquelas vezes onde sabemos quantas repetições serão executadas:

```python
palavra = "Python"

for letra in palavra:
    print(letra) # Imprime cada letra do índice
```

`letra` no `for` é uma variável declarada por você mesmo, onde ela vai conter o índice de cada letra da string. Um jeito mais simples e fácil, diferente de precisar usar `palavra[i]`, como visto no código acima com `while`.

`for` significa **para**. Aí podemos ler: `PARA` cada `LETRA` `EM (IN)` `PALAVRA`, imprima a letra.

Resumindo, agora você não precisa controlar a repetição, fazer operação de soma composta, etc. O `for` vai fazer exatamente a mesma repetição, só que na quantidade de caracteres da variável `palavra`, sem precisar especificar com `len()`, verificar se `i` é menor que `len(palavra)`, etc.

E mais uma coisa que é importante ressaltar, diferente do `while` que pega o **ÍNDICE**, com o `for` nós pegamos o **VALOR**
