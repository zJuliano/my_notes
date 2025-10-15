🗓️ Data: 08/10/2025 ás 03:50

```python
condicao = False
passou_no_if = None
  
if condicao:
	passou_no_if = True
	print("Faça algo")
else:
	print("Não faça algo") # Saída: Não faça algo
	
print(passou_no_if is None) # Saída: True
```

No código acima, a variável `condicao` está com o valor `False`, então o bloco dentro do `if` não é executado. Isso significa que o `passou_no_if = True` **não acontece**, e a variável continua com o valor `None`, que foi o valor atribuído a ela antes do `if`

`(passou_no_if is None)`, está **verificando** se a variável `passou_no_if` é exatamente igual a `None`. E como ela realmente é `None`, o retorno desse `print` é `True`

---

```python
print(passou_no_if is not None) # Saída: False
```


Já o `is not None` é o **inverso do `is None`**, ou seja, ele verifica se a variável **NÃO é** `None`, ou seja, se ela tem **qualquer outro valor** diferente de `None`, o seu retorno será `False`

No caso acima, o retorno é `False` porque a variável `passou_no_if` **É** `None`. Como ela não é diferente de `None`, o resultado dessa verificação é `False`.

---

* `passou_no_if is None`: vai retornar `True` **se a variável for exatamente `None`**. Caso ela não seja `None`, retorna `False`.
* `passou_no_if is not None`: vai retornar `True` **se a variável for qualquer valor diferente de `None`**, como por exemplo `True`, `False`, `0`, `""`, `[]`, `"texto"`, etc... Agora, se for exatamente `None`, o retorno será `False`

---

Resumindo: 

* `passou_no_if is None` → Retorna `True` se for exatamente `None`
* `passou_no_if is not None` → Só retorna `True` se for qualquer valor **diferente** de `None`