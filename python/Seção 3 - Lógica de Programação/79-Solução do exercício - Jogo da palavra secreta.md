🗓️ Data: 13/10/2025

Estou anotando a solução desse exercício e explicando toda a lógica dele, pois foi um exercício que eu consegui fazer, mas não consegui desenvolver toda a lógica sozinho. O que travou bastante foi o uso do `for`, onde eu não sabia o que fazer para transformar a string em `a*a*a**` ao digitar a primeira letra "a".

```python
PALAVRA_SECRETA = "abacaxi"
digitado = ""

while True:

    pergunta = input("Digite uma letra: ")

    if len([[80. Tipo list - Introdução às listas mutáveis em Python]]pergunta) > 1:
        print("Digite somente UMA letra!")
        continue
    
    if pergunta in PALAVRA_SECRETA:
        digitado += pergunta
        print("Você acertou!")
    else:
        print("Você errou!")

    palavra_formulada = ""
    for letra in PALAVRA_SECRETA:
        if letra in digitado:
            palavra_formulada += letra
        else:
            palavra_formulada += "*"
    print(palavra_formulada)
    
    if palavra_formulada == PALAVRA_SECRETA:
        print("Parabéns! Você acertou!")
        break
```

- Primeiro, declaramos as duas primeiras variáveis globais, fora do bloco do while, onde sua primeira é `PALAVRA_SECRETA = "abacaxi"` e sua segunda é `digitado` com uma string vazia.
  - Por quê string vazia? Porque ela será alterada durante a execução do while.
- Depois, de forma bem resumida, fizemos a pergunta da letra, e se `len(pergunta)` for maior que `1`, imprime uma mensagem dizendo para digitar somente uma única letra e realiza o `continue` do while.
- Outra condição, se a letra digitada estiver em `PALAVRA_SECRETA`, `digitado` recebe ele mesmo mais a letra digitada (`digitado += pergunta`), assim ele vai acumulando todas as letras acertadas, e imprime "você acertou". Caso a condição seja falsa, só imprime "você errou".
- Aí que vem o chefão dessa lógica onde quebrei a cabeça, o `for`. Primeiro declaramos a variável `palavra_formulada` com string vazia, onde ela será a variável que irá imprimir a string formatada.
  - Fizemos a iteração com `for letra in PALAVRA_SECRETA`, onde `letra` seria o valor de cada índice.
  - Dentro do laço, fizemos uma condição:
    - Se a letra do `for` estiver em `digitado`, a variável que está armazenando a letra acertada, `palavra_formulada`, concatena com a letra do `for`.
    - Caso contrário, concatena com `*`.
  - O `for` percorre cada letra da palavra secreta e decide se deve mostrar a letra real ou um `*`, dependendo se ela já foi digitada ou não.
- Depois, no final do `for`, exibiria a `palavra_formulada`.
- E depois a última condição, se `palavra_formulada` for igual a `PALAVRA_SECRETA`, irá imprimir "Parabéns! Você acertou!" e realizaria o `break` do while.
