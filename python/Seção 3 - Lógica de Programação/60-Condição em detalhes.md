🗓️ Data: 09/10/2025

Na aula anterior, como vimos, o `while` é executado **ENQUANTO** a condição for verdadeira. E passamos um exemplo onde a condição era sempre verdadeira. Mas, para que a condição seja encerrada naturalmente, sem forçar com `break`, em algum momento a condição deve ser alterada para `False`.

```python
contador = 0

while contador < 10:
	contador = contador + 1
	print(contador)
```

* No código acima, veja que a variável `contador` está recebendo o valor de `0`.
* Depois, temos um `while contador < 10`, que verifica: **ENQUANTO** `0` for MENOR que `10`:
* Executa `contador = contador + 1`, que é a própria variável recebendo a soma dele mesmo mais 1. Ou seja, começa com zero, vai pra 1, 2, 3, etc... até o número `10`.
* E, depois dessa mudança de valor, exibe `print(contador)`, começando com `1`. Isso porque, na primeira execução, irá fazer `0 + 1`, resultando em `1`.
* No exato momento em que a variável `contador` receber o valor de `10`, a condição será falsa. Isso porque `10` **NÃO** será MENOR que `10`, e, como resultado, a repetição se encerra por ser falsa.

---