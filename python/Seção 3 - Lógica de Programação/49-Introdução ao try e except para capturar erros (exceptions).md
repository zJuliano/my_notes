🗓️ Data: 27/09/2025

`try` tenta executar determinado código, caso ocorra qualquer erro (com exceção de syntax) ele vai capturar o erro com `except` e fazer o que estiver dentro do bloco de código

Imagine que queiramos converter uma string para um número inteiro, o que não faz nenhum sentido. `int()` e `float()` converte somente números, float para int e int para float. Tentar converter uma string com `int("a")` ou `float("a")`claramente geraria um erro, mas não de syntax, e sim um erro de execução

```python
try:
    numero = int("a")
except:
    print("Ocorreu um erro") # Saída: Ocorreu um erro
```

O que o `try` está tentando fazer, é **TENTAR** executar o bloco de código dele, e caso **QUALQUER** erro seja capturado, ele vai executar o bloco `except`

###