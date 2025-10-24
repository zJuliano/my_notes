🗓️ Data: 16/10/2025

Agora vamos ver o método `.insert()`, que é utilizado para **inserir** um valor em um determinado índice.
- É quase que nem o `.pop()`, mas o `pop` **remove** e **retorna** o último item da lista caso não tenha nenhum argumento. Se você passar o índice da lista que deseja remover como argumento, ele vai remover o item daquele índice em específico.
No `.insert()`, você vai inserir algo em um determinado índice e **REORDENAR** os índices:

```python
lista = [10, 20, 30, 40]
lista.insert(0, 5)
print(lista) # Saída: [5, 10, 20, 30, 40]
```

No código acima, os dois argumentos literais do `.insert()` são `0` e `5`:

- `0` é o **ÍNDICE** em específico onde iremos inserir
- `5` é o **VALOR** que será inserido
- Ou seja, no índice `0` estamos **INSERINDO** o **VALOR** `5`
- Como estamos inserindo no **PRIMEIRO** índice da lista, todos os itens posteriores são reordenados
- Ou seja, ao invés de ficar `10, 20, 30, 40`, vai ficar: `5, 10, 20, 30, 40`

Se nós passarmos um índice que **não existe** como argumento do `.insert()`, por exemplo: `.insert(100, 5)`, ele vai tentar adicionar o valor literal `5` no índice `100`. No código acima, esse índice **não existe**, nesse caso, ele vai ver o **ÚLTIMO** item da lista e vai somar +1, adicionando no último índice.

---
