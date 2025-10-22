🗓️ Data: 16/10/2025

Agora, imagine que temos uma lista A e uma lista B, o que pode ocorrer tranquilamente, e a gente queira **JUNTAR** essas duas listas em uma só. Ou seja, **concatenar** essas duas listas.

Primeiro, você pode utilizar o método tradicional, que é a concatenação:

```python
lista_a = [1, 2, 3]
lista_b = [4, 5, 6]

lista_c = lista_a + lista_b

print(lista_c) # Saída: [1, 2, 3, 4, 5, 6]
```

O que isso vai fazer é **concatenar** a `lista_a` com a `lista_b`, retornar a lista concatenada e armazenar na variável `lista_c`.

---

## Método .extend()

A outra maneira é utilizando o método `.extend()` da lista:

```python
lista_a = [1, 2, 3]
lista_b = [4, 5, 6]

lista_a.extend(lista_b)

print(lista_a) # Saída: [1, 2, 3, 4, 5, 6]
```

Os dois métodos fazem essa concatenação, só tem algumas pequenas diferenças:

- Utilizando o método `.extend()`, aplica uma ação **diretamente** na variável `lista_a`. Veja que na linha 6, estamos imprimindo o valor da variável `lista_a`, e não estamos armazenando em nenhuma variável diferente.
- Já utilizando a concatenação tradicional, a concatenação **retorna** a lista e é necessário armazenar em uma variável para poder utilizar essa lista completa.

Um outro detalhe do `.extend()` é que se tentar armazenar em uma variável, o seu retorno será `None`. Veja o código abaixo de exemplo:

```python
lista_a = [1, 2, 3]
lista_b = [4, 5, 6]

lista_c = lista_a.extend(lista_b)

print(lista_c) # None
```

- Por quê retornou `None`?

  - Como já sabemos, o `None` é o "Sem valor", e como vimos, o `lista_a.extend(lista_b)` executa uma ação **diretamente** na variável `lista_a`, e o retorno de `None` é porque o `.extend()` não retorna nada, ou seja, ele faz uma ação mas não te entrega nenhum valor
  - Resumindo: O `lista_a.extend(lista_b)` está realizando o `.extend()` **diretamente** na `lista_a`, por isso não faz sentido armazenar em uma variável

---