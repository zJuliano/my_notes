🗓️ Data: 21/10/2025

O método `.split()` divide uma string em determinado caractere passado como argumento.

```python
frase = "olha só que, coisa interessante"
lista_frases = frase.split(",")
lista_frases2 = frase.split()

print(lista_frases) # ['olha só que', ' coisa interessante']
print(lista_frases2) # ['olha', 'só', 'que,', 'coisa', 'interessante']
```

- Veja que seu retorno é uma lista, no primeiro `lista_frases`, passei como argumento a virgula (`","`), e o método dividiu a frase em 2 itens de uma uma lista e a vírgula **não foi incluída**
- No segundo `lista_frases`, não passamos argumento nenhum, e por **padrão** quando não há argumento ele divide a string com espaçamentos

Perceba também que, quando definimos como argumento do `.split(",")` a vírgula, toda a string depois da vírgula ficou com um espaçamento: `' coisa interessante'`.  Isso acontece porquê o split remove a vírgula, mas **não remove o espaço que vem depois dela**

Podemos remover espaçamentos com **OUTRO** método de string, que é o `.strip()`


