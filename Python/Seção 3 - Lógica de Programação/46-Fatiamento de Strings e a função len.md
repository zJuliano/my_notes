🗓️ Data: 26/09/2025
## Strings são iteráveis

Nós já vimos recentemente que strings são iteráveis, onde é possível coletar um caractere específico pelo índice de uma string como se fosse a string fosse uma lista.

```python
nome = "Juliano"
print(nome[0]) # Saída: J
```

Os índices começam sempre do zero, no caso do código acima, existem 7 caracteres, mas se tentar pegar o caractere `nome[7]`, **nesse caso** onde estamos tentando pegar um caractere específico, retornará um erro. Pois começa com zero para "J" e seu índice máximo é 6 para a letra "o".

| Caractere | índice    | Saída |
| --------- | --------- | ----- |
| J         | `nome[0]` | J     |
| u         | `nome[1]` | u     |
| l         | `nome[2]` | l     |
| i         | `nome[3]` | i     |
| a         | `nome[4]` | a     |
| n         | `nome[5]` | n     |
| o         | `nome[6]` | o     |

Também podemos chamar pelo índice negativo, onde começa com o `nome[-1]` sendo sua **última** letra da String, no caso acima, a letra "o". E nesse caso é simples, se começa com `-1` vai até o `-7`. E se `-1` é a sua última letra da string, `-7` é a primeira.

- Índices positivo: Começa com `[0]`
- Índices negativos: começa com `[-1]`

## Fatiamento

Como o nome já diz, "fatiamento", onde ele vai pegar uma **fatia** da string. Você tem que indicar o inicio e fim de uma string, onde a string vai começar a pegar **a partir** do inicio, até o fim que você definiu.

```python
nome = "Juliano"
print(nome[1:6]) # Saída: ulian
```

Veja o código acima: o `1` indica que vai começar a pegar a partir do índice 1, que é a letra "u". Depois vem um `:` que faz a separação, e logo após, tem `6`, que indica até onde vai o final da string. Só que tem alguns detalhes importantes:

- Quando você indicar o fim, vai sempre até UM a menos, então não vai do "u" até o "o", ficando "uliano". E sim do "u" até o "n", ficando "ulian". Então, ao invés de ir até o `6`, vai até o `5`. O final é sempre omitido.
- Quando você omitir o fim da string, ou seja, ficar somente `print(nome[1:])`, significa que você está indiciando o início, mas não indica o final. E o que isso significa? Ele vai começar a partir do índice `1` e vai até o final da string, ficando "uliano".
- Quando você omitir o início ( `print(nome[:5])` ) e indiciar somente o final, vai ser a mesma coisa, só que ao contrário. Ele vai começar a partir do primeiro índice (já que não indicou onde inicia) e vai até o final, e lembrando, o índice final é sempre omitido. Ou seja, ele não vai até o `5` e sim até o `4`.
- No Python, mesmo que você indique um final maior que o número de caracteres, ele vai até o final normalmente e não retorna nenhum erro. No caso acima, existem 7 caracteres, tendo o máximo de 6 índices. Então, se colocarmos `print(nome[:15])`, ele vai do índice 0 até o índice final normalmente, que é `6`.

### Também é possível fazer com índices negativos:

```python
nome = "Juliano"
print(nome[-6:-1]) # Saída: ulian
```

E novamente, o final ( `-1` ) que seria a última letra também é omitido. Ao invés de exibir a letra "o" que é o `-1`, ele exibiu até o `-2`.

## Função len()

A função `len()` retorna a quantidade de caracteres que uma string possui:

```python
nome = "Juliano"
print(len(nome)) # Saída: 7
```

Então, podemos juntar:

```python
print(nome[0:len(nome)])
```

No código acima, estamos fazendo um fatiamento na variável. Indicamos o seu início que é `0`, depois, `len(nome)` retornará o número de caracteres da variável que é `7`, e irá fazer o fatiamento de `0:7`. 

## Passo

Vimos anteriormente o fatiamento indicando `inicio:final`, mas existe mais um fatiamento que é o "passo". Onde sua estrutura é a mesma, `inicio:final:passo`.

"Passo" é basicamente de quantos em quantos índices ele vai "pular":

```python
print(nome[0:len(nome):2]) # Saída: Jlao
```

- Início é seu índice `0` e o final é o retorno de `len()`, que é `7`
- `0:7:2` esse "`:2`" significa que vai pular 1 e pegar o próximo
- Ou seja:
  - pega o índice `0`
  - pula o índice `1`
  - pega o índice `2`
  - pula o índice `3`
  - pega o índice `4`
  - e assim por diante...
- Se deixar o "passo" com valor de 1: `0:7:1`, ele imprimiria `Juliano` certinho, ou seja, não pula nada

### Passo negativo

```python
print(nome[0:len(nome):-1]) # Saída: String vazia
```

- Veja que o início é `0` e o fim é o retorno de `len()` que é `7`. Ou seja, aqui ele está indiciando `0:7`
- Porém, temos um passo com `:-1`, ficando: `0:7:-1`
- A partir do momento que indicamos um passo em negativo, ele percorre de **TRÁS** para **FRENTE**. Ou seja, ele vai tentar percorrer do índice **MAIOR** para o **MENOR** ao invés de **MENOR** para o **MAIOR**
  - Menor para o maior: `0:7`
  - Maior para o menor: `7:0`
- E nesse caso, o início é **MENOR** que 7. Ou seja, ele retorna uma string vazia. Agora, se fosse:

```python
print(nome[len(nome)::-1]) # Saída: onailuJ
```

- Nesse caso, o início é o retorno de `len()`, que é `7`, omitimos o final e temos um passo com `-1`
- O resultado é a string de trás para frente.



