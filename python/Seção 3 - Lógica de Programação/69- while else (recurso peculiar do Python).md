🗓️ **Data: 11/10/2025**

De acordo com o professor, o uso do `else` com `while`, `for` e outros laços é um **recurso exclusivo do Python**, que **não existe em outras linguagens**.
Ele também comentou que é um recurso **raro de ser usado**, ensinou apenas por conhecimento, porque em sua experiência, **nunca precisou usar**

```python
string = 'Qualquer valor'

i = 0
while i < len(string):
    letra = string[i]
    print(letra)  # Imprime cada letra do índice
    i += 1
else:
    print("O while foi executado")  # Também executa esse print
```

Quando o `while` é executado **por completo** e sua condição se torna `False`, o bloco `else` **também é executado**.

Isso é semelhante ao `if/else`: quando o `if` é falso, o `else` é executado.
Aqui, o papel do “if” é o `while`, e quando ele termina (vira `False`), o `else` é acionado.

**Resumindo:**

* Enquanto o `while` for verdadeiro, ele executa o seu bloco.
* Quando o `while` se torna falso (ou seja, termina naturalmente), o `else` é executado.

---

## Particularidade: uso com`break`

Existe uma particularidade nesse comportamento:
Se você **interromper** o laço com um `break`, o bloco `else` **não será executado**

```python
string = 'Qualquer valor'

i = 0
while i < len(string):
    letra = string[i]

    if letra == ' ':
        break

    print(letra)
    i += 1
else:
    print("Não encontrei nenhum espaço na string")  # Não executa
```

Nesse exemplo, o `if` verifica se há um espaço na `string`.
Como o valor é `"Qualquer valor"`, existe um espaço, então o `break` é executado e o `while` é **interrompido antes de terminar**.
Por isso, o `else` **não é executado**.

Agora, se a `string` fosse `"Qualquervalor"` (sem espaço), o `if` seria falso e o laço seria concluído até o final.
Nesse caso, o `while` terminaria naturalmente, e o `else` **seria executado**, imprimindo “Não encontrei nenhum espaço na string”

---

**Resumindo:**

* Se o `while` for **interrompido** (por `break` ou erro), o `else` **não executa**.
* Se o `while` for **concluído normalmente**, o `else` **executa**.

---
