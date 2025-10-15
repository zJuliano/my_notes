## Introdução

`IF` e `ELSE` são basicamente "SE" e "SENÃO". Eles servem para criar condições que mudam o fluxo do código. Internamente, o computador só entende se algo é `True` ou `False`.

Por exemplo, imagine este código:

```python
entrada = input('Você quer "entrar" ou "sair"? Digite: ')

print("Você entrou no sistema")
print("Você saiu do sistema")
```

Aqui, o objetivo seria imprimir **apenas** a ação correspondente ao que o usuário digitou. Sem condições, o código simplesmente executa todos os `print`, independentemente da entrada.

## Condição IF (SE)

O `if` permite executar um bloco de código **apenas se uma condição for verdadeira**:

```python
entrada = input('Você quer "entrar" ou "sair"? Digite: ')

if entrada == "entrar":
    print("Você entrou no sistema")
```

* Se `entrada` for igual a "entrar", a condição retorna `True` e o `print` é executado.
* Se não, retorna `False` e nada acontece.

⚠️ **Atenção:** Python exige **identação** (geralmente com tab ou 4 espaços) para indicar o bloco de código que pertence à condição.

## Condição ELIF (SE NÃO SE)

O `elif` funciona como "SE NÃO SE", ou seja, ele só é verificado se o `if` anterior foi `False`:

```python
if entrada == "entrar":
    print("Você entrou no sistema")
elif entrada == "sair":
    print("Você saiu do sistema")
```

* Se o `if` for `False`, o programa verifica a condição do `elif`.
* Se `True`, executa o bloco do `elif`.

## Condição ELSE (SE NÃO / CASO CONTRÁRIO)

O `else` captura todas as situações que não foram atendidas pelo `if` ou `elif`:

```python
if entrada == "entrar":
    print("Você entrou no sistema")
elif entrada == "sair":
    print("Você saiu do sistema")
else:
    print("Você não digitou nem entrar nem sair")
```

* `else` não tem condição, ele executa o bloco se todos os `if` e `elif` anteriores forem `False`.

## Dependência

* `if` pode ser usado sozinho.
* `elif` **depende de um `if` anterior**.
* `else` **depende de um `if` ou `elif` anterior**.

Somente **um bloco de código** com condição `True` será executado em cada execução do programa.