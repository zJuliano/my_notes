🗓️ **Data:** 22/09/2025
### Exemplo básico:

``` python
print("Meu nome é {} e tenho {} anos.".format(nome, idade))
```

-   O primeiro `{}` recebe o primeiro argumento, que é a variável `nome`.
-   O segundo `{}` recebe o segundo argumento, que é a variável `idade`.

✔️ Sempre é respeitada a ordem dos argumentos.

Também podemos passar valores literais diretamente no método que seguirá a mesma regra:

``` python
print("Meu nome é {} e tenho {} anos.".format("Juliano", 20))
```

⚠️ **Atenção:** Um marcador `{}` sem um argumento correspondente gera
erro.

### Como o método format() funciona

🔁 O método `.format()` funciona como um *loop*, substituindo os `{}` na
string pela ordem dos argumentos (da esquerda para a direita).

### Formatação numérica com format:

``` python
print("{:.2f}".format(3.14159))  # Saída: 3.14
```

### Índice Posicional

```python
nome = "Juliano"
idade = 20
print("Meu nome é {1} e tenho {0} anos".format(nome, idade))

# Saída: Meu nome é 20 e tenho Juliano anos
```

* `{1}` é substituído pelo argumento `idade`
* `{0}` é substituído pelo argumento `nome`

Os índices **sempre** começam a partir do *zero*, sendo o zero seu primeiro argumento.

⚠️ **Atenção:** Não misture índices com placeholders sem índice, pois isso gera erro no Python 3:

```python
print("Meu nome é {} e tenho {1} anos".format(nome, idade))
```

### Argumentos Nomeados (ou *Keyword Arguments*)

```python
print("Meu nome é {a} e tenho {b} anos".format(a=nome, b=idade))
```

* `{a}` e `{b}` são substituídos pelos valores nomeados `a=nome` e `b=idade`

Resultado:

```
Meu nome é Juliano e tenho 20 anos
```

⚠️ **Atenção:** Depois que você começa a usar argumentos nomeados, **todos os argumentos seguintes também devem ser nomeados**. Por exemplo, este código abaixo gera erro:

```python
print("Meu nome é {a} e tenho {b} anos".format(a=nome, idade))
```

Sempre nomeie todos os argumentos que vêm após o primeiro nomeado:

```python
print("Meu nome é {a} e tenho {b} anos".format(a=nome, b=idade))
```
