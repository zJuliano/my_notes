🗓️ **Data:** 23/09/2025

## O que é `input()`

`input()` é uma função que solicita dados do usuário.

```python
input("Digite o seu nome: ")
```

Ela **pergunta algo para o usuário**, espera a entrada e retorna por padrão uma string. No exemplo acima, o valor digitado não é armazenado, apenas é coletado e descartado.

### Armazenando o valor em uma variável

Para usar o valor digitado, podemos armazená-lo em uma variável:

```python
nome = input("Digite o seu nome: ")
print(nome)
```

Aqui, o input coleta o nome do usuário, armazena na variável `nome` e imprime o valor.

Você também pode mostrar o nome da variável junto com o valor usando `nome=` dentro de um f-string:

```python
print(f"O seu nome é {nome=}")
# Resultado: O seu nome é nome='Juliano'
```

## Input por padrão é string

```python
numero_1 = input("Digite o primeiro número: ")
numero_2 = input("Digite o segundo número: ")
print(f"Sua soma é {numero_1 + numero_2}")
# Se digitarmos 5 e 5, o resultado será: 55
```

Como o `input()` retorna uma string, o operador `+` faz **concatenação** ao invés de soma numérica.

### Convertendo para números

Para somar numericamente, podemos converter a entrada para `int`:

```python
numero_1 = int(input("Digite o primeiro número: ")) # 5
numero_2 = int(input("Digite o segundo número: ")) # 5
print(f"Sua soma é {numero_1 + numero_2}")
# Resultado: Sua soma é 10
```

⚠️ **Atenção:** Profissionalmente, converter diretamente pode causar erro se o usuário digitar algo que não seja número. Nesse caso, seria melhor validar a entrada antes da conversão.
