🗓️ Data: 16/10/2025

Na aula anterior, vimos que a lista é um dado **mutável**, e é o primeiro de um dos dados mutável que a gente vai aprender.
- Por que mutável?
  - Como vimos, podemos **acessar** o dado da lista e alterar a qualquer momento.
Uma outra coisa interessante também é o **GRUD**. Grud significa: Criar (Create), Ler (Read), Alterar (Update) e Deletar (Delete).

---

## Apagando item da lista

Para apagar um item da lista, iremos utilizar a instrução `del`:
[[82-Inserindo itens em qualquer índice da lista com insert (Tipo list)]]
```python
lista = [10, 12, 15, 23, 40]
del lista[2]

print(lista) # Saída: [10, 12, 23, 40]
print(lista[2]) # Saída: 23
```

No código acima, veja que na linha 1 temos uma lista de números inteiros, sendo que seu segundo índice (2) é o `15`. Na linha 2, estamos passando a instrução `del lista[2]`, que irá **DELETAR** o valor do índice 2.

- Ou seja, o índice 2 `15` será deletado.
- Na linha 4, exibimos a lista completa, que imprime: `[10, 12, 23, 40]` SEM o `15`, já que foi deletado.
- Na linha 5, imprimimos o índice 2 da lista, o que **ANTES** era o número 15, agora que foi deletado, o terceiro índice, que era o `23`, passa a ser o índice 2, e assim sucessivamente.
- Resumindo, quando um índice é deletado, todos os índices que estavam na frente dele são movidos.

Agora, imagine que você tem uma lista com 10 mil itens, e você apaga o segundo item da lista. Agora, o Python vai mover todos os 9.998 elementos da lista para **frente**, e isso requer muito processamento, seu programa vai ficar lento e provavelmente você não vai saber o motivo. De acordo com o professor, **EVITE** ter que fazer os índices da lista serem reescritos.

O ideal de uma lista é você **adicionar** ou **retirar** coisas do **FINAL** da lista. Existem outros tipos de dados em que é mais útil fazermos esse tipo de movimentação, tirar do começo, do meio ou do final.

Resumindo, de acordo com o professor, em uma lista o interessante é que trabalhamos somente no **fim** dela.

---

## Adicionando item na lista

Como já sabemos, tudo em Python é um objeto, sendo um objeto, existem **métodos** que realizam ações dentro dessa lista. Para adicionar um item na lista, você deve utilizar o método `.append()` em uma lista:

```python
lista = [10, 12, 15, 23, 40]
lista.append(50)
print(lista) # Saída: [10, 12, 15, 23, 40, 50]
```

No código acima, veja que existem 5 elementos ou itens. Na linha 2, estamos **adicionando** o número inteiro `50` na lista, e na linha 3, estamos exibindo a lista, como dá para ver, o que antes tinha 5 itens, com o `.append(50)`, a lista passou a ter 6 itens.

- Como deu pra ver, ele **sempre** adiciona no **final da lista**. O único trabalho que o Python teve foi somar +1, não teve que mover nenhum elemento, e isso não requer tanto processamento.
- O que pode ser diferente se tivermos uma lista com 10 mil itens e adicionarmos um item no primeiro índice, onde todo o restante dos itens terá que ser movido, necessitando de muito processamento.

---

## Removendo o último item da lista

O método `.pop()` é responsável por sempre **remover** e **retornar** o **ÚLTIMO** item de uma lista (sem argumento):

```python
lista = [10, 12, 15, 23, 40]

lista.append(50) # A lista virou [10, 12, 15, 23, 40, 50]
lista.pop() # Removeu o último índice da lista, que é o 50

print(lista) # Saída: [10, 12, 15, 23, 40]
```

Como dá pra ver, definimos a lista com 5 itens, depois adicionamos +1 item (50), onde, na linha 3, a lista tem 6 itens ao invés de 5. Depois, na linha 4, **removemos** o último item da lista, que seria o 50 que adicionamos anteriormente, e, por fim, na linha 6, imprimimos a lista completa.

- De primeira, talvez você pense que não houve mudanças, mas houve. Como na linha 3 adicionamos o item `50`, o `.pop()` removeu exatamente esse mesmo item, por isso exibiu a mesma lista definida na linha 1.

```python
lista = [10, 12, 15, 23, 40]

lista.append(50) # A lista virou [10, 12, 15, 23, 40, 50]
valor_removido = lista.pop()

print(lista, f'Removemos o item {valor_removido}') # [10, 12, 15, 23, 40] Removemos o item 50
```

Para ficar mais claro, adicionamos o item removido com o `.pop()` e armazenamos o valor na variável `valor_removido`. Depois, na linha 6, imprimimos a lista e o valor da variável, que é exatamente `50`.

- O `.pop()` sem argumentos remove sempre o último item da lista, mas você também pode especificar o índice passando o número do índice como argumento, por exemplo: `.pop(3)`, que removeria o índice 3.
- Importante ressaltar também que, no código acima, o `lista.pop()` retorna **sempre** o valor removido, no caso ali em cima, retornou o `50`, mas se, ao invés de `50`, fosse uma string, armazenaria o valor removido (string) na variável `valor_removido`.

---

## Limpando a lista

Um outro método, que não exige muita explicação, é o `.clear()`, que **limpa todos os elementos/itens de uma lista**:

```python
lista = [10, 20, 30, 40]
lista.clear()
print(lista) # Saída: [] (lista vazia)
```

---

