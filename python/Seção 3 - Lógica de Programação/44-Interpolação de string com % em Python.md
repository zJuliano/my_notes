🗓️ **Data:** 24/09/2025

Interpolação de strings estilo C é basicamente a mesma coisa que fizemos com `.format()`, só que com uma sintaxe diferente. Os **tipos são importantes** na interpolação básica.

| Código       | Tipo esperado        | Exemplo             |
| ------------ | -------------------- | ------------------- |
| `%s`         | string               | `'%s' % "Juliano"`  |
| `%d` ou `%i` | int                  | `'%d' % 20`         |
| `%f`         | float                | `'%.2f' % 3.14159`  |
| `%x`         | int → hexa minúsculo | `'%x' % 255` → `ff` |
| `%X`         | int → hexa maiúsculo | `'%X' % 255` → `FF` |

---
## Exemplo simples

```python
nome = 'Juliano'
variavel = 'Seu nome é %s' % nome
print(variavel)  # Saída: Seu nome é Juliano
```

* `%s, %d, %f, etc...` é o **formato da string**, esperando um valor do tipo correspondente.
* O operador `%` faz a **interpolação**, inserindo o valor no lugar do placeholder.
* `nome` é o argumento que substitui `%s`, assim como argumentos no `.format()` (posicionais ou nomeados).

---

## Mais de um valor

Quando há mais de um valor, use **parênteses**:

```python
nome = 'Juliano'
preco = 1000.95897643
variavel = '%s, o preço é R$%f' % (nome, preco)
print(variavel)  # Saída: Juliano, o preço é R$1000.95897643
```

* A interpolação segue **a ordem dos argumentos passados**, não é possível chamar pelo índice como no `.format()`.

---

## Formatação de casas decimais

```python
variavel = '%s, o preço é R$%.2f' % (nome, preco)
print(variavel)  # Saída: Juliano, o preço é R$1000.96
```

* `%.2f` formata o número float com **duas casas decimais**.
* No estilo C, usamos `.2` entre `%` e `f` para limitar as casas decimais.

---

## Hexadecimal

```python
print("O hexadecimal de %d é %x" % (15, 123456))
# Saída: O hexadecimal de 15 é 1e240
```

* O primeiro argumento (`15`) substitui `%d`.
* O segundo argumento (`123456`) substitui `%x` e é convertido para **hexadecimal minúsculo**.

### Tabela rápida de 0 a 15 em hexadecimal

| Decimal | Hexadecimal |
| ------- | ----------- |
| 0       | 0           |
| 1       | 1           |
| 2       | 2           |
| ...     | ...         |
| 10      | a           |
| 11      | b           |
| 12      | c           |
| 13      | d           |
| 14      | e           |
| 15      | f           |

---

## Definir largura mínima de caracteres

```python
print("O hexadecimal de %d é %05x" % (15, 10))
```

* `%05x` → `0` preenche com zeros à esquerda.
* `5` define a **largura mínima** de caracteres.
* `x` converte o número para **hexadecimal**.

Se o número convertido for menor que a largura mínima, ele **preenche com zeros ou espaços** até atingir a largura.

```python
print("%05x" % 123456)  # Saída: 1e240
print("%5x" % 10)       # Saída:     a (com espaços à esquerda)
```

* Sem o `0`, o preenchimento é feito com **espaços** ao invés de zeros.
