🗓️ Data: 09/10/2025

```python
contador = 0
contador = contador + 1
```

Na aula passada, vimos essa atribuição, onde a variável `contador` recebe ela mesma mais 1.

Isso é uma operação tão comum que existe operações de atribuição prontas para fazer exatamente a mesma coisa.

| Operador | Exemplo   | Equivalente completo | Explicação rápida                                |
| -------- | --------- | -------------------- | ------------------------------------------------ |
| `+=`     | `x += 1`  | `x = x + 1`          | Soma e atribui                                   |
| `-=`     | `x -= 1`  | `x = x - 1`          | Subtrai e atribui                                |
| `*=`     | `x *= 2`  | `x = x * 2`          | Multiplica e atribui                             |
| `/=`     | `x /= 2`  | `x = x / 2`          | Divide e atribui (resultado com ponto flutuante) |
| `//=`    | `x //= 2` | `x = x // 2`         | Divide e atribui (resultado inteiro)             |
| `%=`     | `x %= 2`  | `x = x % 2`          | Módulo e atribui (resto da divisão)              |
| `**=`    | `x **= 2` | `x = x ** 2`         | Exponenciação e atribui                          |

Então, ao invés de fazer a atribuição e soma do jeito comum, pode utilizar esses operadores.

```python
contador = 0

contador += 1
print(contador) # Saída: 1
```

E isso não funciona apenas para números, também funciona com strings.

```python
contador = "1"

contador += "2"
print(contador) # Saída: 12
```

No código acima, está concatenando `1 + 2`.

Mesma coisa com multiplicação com string:

```python
contador = 10

contador *= "2"
print(contador) # Saída: 2222222222
```

Veja que segue o padrão: primeiro vem o operador aritmético, como `+`, `-`, `*`, etc... E depois vem o operador de atribuição `=`
