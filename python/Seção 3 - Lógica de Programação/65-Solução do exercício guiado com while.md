🗓️ Data: 09/10/2025

Esse é um exercício simples, onde julguei importante anotar a lógica aqui, pois criar uma string a partir do índice fez eu sentir um pouco demais o meu cérebro.

Consegui apenas iterar e imprimir cada índice da string com o `while`, agora criar uma nova string a partir de cada índice eu não consegui. Por isso, estou anotando.

```python
nome = "Juliano"

indice = 0
novo_nome = ''

while indice < len(nome):
	letra = nome[indice]
	novo_nome += f'{letra}'

	indice += 1
    
print(novo_nome)
```

* Variável `nome` recebe a string `"Juliano"`, que contém 7 caracteres e tem 6 índices.
* Variável `indice` recebe o valor de 0, e `novo_nome` apenas uma string vazia.
* Depois iniciamos uma condição `while`. **Enquanto** `indice` (0) for menor que `len(nome)`, que é 7:
    * Entra no bloco do `while`.
    * A variável `letra` é criada, onde ela recebe cada letra do índice **individualmente** em cada repetição. Começando com "J" (0), "u" (1), "l"(2), etc...
    * Depois fazemos a concatenação composta, onde `novo_nome`, que era apenas uma string vazia declarada fora do bloco `while`, irá concatenar, na primeira repetição, sua string vazia + a primeira letra do índice, que é "J". Ou seja: `'' + 'J'`, o que irá resultar em `novo_nome` sendo `"J"` como string, ao invés de vazia.
    * Depois, irá fazer a soma composta com `indice += 1`, onde o `indice` passará a ser 1.
- Como de costume, irá voltar para a condição do `while`. **Enquanto** o `indice` (que virou 1) for menor que `len(nome)`, que é 7, a condição será verdadeira e entrará novamente no bloco.
    * `letra = nome[indice]` irá receber a letra do índice 1, que é "u".
    * A variável `novo_nome`, que agora tem apenas a letra "J", irá concatenar com "u", resultando em "Ju".
    * E isso será repetido até completar o laço de repetição `while`, transformando `novo_nome`, que no começo era uma string vazia, para `"Juliano"`.
    * E no final, quando a condição do `while` for falso, irá executar o código fora do bloco: `print(novo_nome)`, imprimindo `Juliano` como saída.
