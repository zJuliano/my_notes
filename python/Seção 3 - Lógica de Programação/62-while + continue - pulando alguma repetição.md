🗓️ Data: 09/10/2025

Assim como vimos recentemente, o `break` serve para parar uma execução forçada de um laço de repetição `while`. Mas, além do `break`, também existe o `continue`.

O contrário do `break`, o `continue` serve para **PULAR** o restante da iteração atual e vai para a próxima a validação da condição. Ou seja, se houver um código logo abaixo do `continue`, ele será pulado.

```python
contador = 0

while contador < 10:
	contador += 1

	if contador == 6:
		continue

	print(contador)
```

No código acima, temos um laço de repetição `while` que será executado **enquanto** a variável `contador` for **MENOR** que `10`.

* Temos uma operação composta, somando a variável `contador` mais `1` em cada repetição.
* Temos uma condição `if` dentro do laço. **SE** o contador for igual a 6, faz exatamente esse `continue`. O que isso significa?
  * Isso significa que, no momento em que o `contador` for `6`, ele vai pular toda a iteração do código abaixo dele. O `print` logo abaixo do `continue` não será executado, e a exibição do `print(6)` será **pulado**.
  * Ficando: 1, 2, 3, 4, 5, 7, 8, 9, 10. (pulando o 6)
  * E novamente, no momento em que `contador` for `10`, a condição do `while` será falsa e a repetição se encerra.
