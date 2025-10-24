🗓️ Data: 09/10/2025

Como vimos anteriormente, por padrão, quando definimos um `while` único com uma condição, **enquanto** a condição for True, o `while` ficará voltando na verificação da condição até ela se tornar falsa.

Agora, vamos ver um pouco de `while` dentro de `while`, onde a lógica é a mesma.

```python
qtd_linhas = 5
qtd_colunas = 5

linha = 1
while linha <= qtd_linhas:
	coluna = 1
	while coluna <= qtd_colunas:
		print(f'{linha=} {coluna=}')
		coluna += 1

	linha += 1
```

* No código acima, temos 3 variáveis: `qtd_linhas` e `qtd_colunas`, com o valor 5, e `linha` com o valor 1.
* Depois temos um `while`. **Enquanto** `linha` for menor que `qtd_linhas`, entrará no bloco de código:
  * `coluna` recebe o valor de 1.
  * Depois temos uma nova condição de `while` *interno*, dentro do `while` *externo*.
  * **Enquanto** `coluna` for menor que `qtd_colunas`:
    * Imprime: `print(f'{linha=} {coluna=}')`.
    * Realiza a operação de soma composta do `while` *interno*: `coluna += 1`.
    * E aqui vem o detalhe: igual à explicação anterior, sempre ficará voltando na verificação da condição `while` atual até a repetição atual terminar.
  * Depois que a repetição interna terminar, irá fazer a operação de soma composta do `while` *externo*, que é `linha += 1`, e depois voltará para a validação do `while` *externo*.
  * Então, irá verificar **enquanto** `linha` (que será 2) for menor que `qtd_linhas` (5):
    * Novamente: `coluna` recebe o valor de 1.
    * Entrará novamente na condição do `while` *interno*, e irá realizar o mesmo procedimento anterior 5 vezes.

Resumindo: o `while` *externo* irá se repetir 5 vezes, e o `while` *interno* também irá se repetir 5 vezes **CADA VEZ** que a condição do `while` externo for verdadeira.

**No total, teremos 25 linhas impressas na tela (5 x 5).**

