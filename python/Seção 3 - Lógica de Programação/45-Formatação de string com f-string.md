🗓️ **Data:** 24/09/2025

Agora vamos definir uma largura fixa na variável. Isso se ela não atingir a quantidade de caracteres que estamos pedindo

```python
variavel = "ABC"
print(variavel) # Saída: ABC
````

Suponhamos que o código acima, a gente queira preencher com espaços o lado esquerdo até preencher 10 caracteres. Então, são 3 caracteres ali em cima `ABC` e faltam 7.

```python
variavel = "ABC"
print(f'{variavel: >10}') # Saída:        ABC
```

Saída: `       ABC`

* No código acima, veja que definimos um `:` onde ele representa onde vai começar a parte da formatação da variável ou valor.
* Logo após o `:`, temos um espaço vazio ` ` que representa o caractere de preenchimento que será exibido, nesse caso, é um caractere vazio, uma string.
* O operador de maior `>` indica o alinhamento à direita. Ou seja, a string da variável vai ficar colada à direita do espaço reservado, o caractere vazio ficará na esquerda.
  * O operador de menor `<` indica o contrário, alinhamento à esquerda. A string da variável fica colada à esquerda do espaço reservado, o caractere vazio ficará na direita.
* `10` é a **largura mínima**. O Python vai garantir que ocupe **pelo menos 10 caracteres**, preenchendo com o caractere definido, que é o espaço vazio. Simples, 3 caracteres da variável (`"ABC"`) mais 7 caracteres vazios, que resulta em 10 caracteres

Então `f'{variavel: >10}'` quer dizer:

- preencher o espaço vazio com espaços vazios
- alinhado à direita
* largura mínima 10
* Resultado: `       ABC`

Ao contrário:

```python
variavel = "ABC"
print(f'{variavel: <10}') # Saída: ABC       
```

Saída: `ABC       `

Também é possível adicionar essa formatação no centro. Não dá para ser 100% preciso, mas ele faz o possível para dividir os caracteres dos dois lados. Tentar fazer o valor da variável ficar no **meio** entre a esquerda e direita.

```python
print(f'{variavel: ^10}')
```

Saída: `   ABC    ` - Veja que essa saída tem 10 caracteres igual, tendo o preenchimento de 3 caracteres para a esquerda e 4 para a direita

É importante ressaltar que, ao invés de caractere vazio, você pode utilizar QUALQUER caractere, e não se limitar apenas a um.

| Código               | Alinhamento | Saída        |
| -------------------- | ----------- | ------------ |
| `f'{variavel:$^10}'` | Centro      | `$$$ABC$$$$` |
| `f'{variavel:&<10}'` | Esquerda    | `ABC&&&&&&&` |
| `f'{variavel:*>10}'` | Direita     | `*******ABC` |

Podemos também utilizar aquele `:.2f` na formatações de números flutuantes. Porém, não é SÓ isso que podemos fazer.

Já vimos que para limitar as casas decimais com f-string, basta acrescentar `:.2f` na formatação do valor:

```python
print(f'{1000.29838423822:.2f}') # Saída: 1000.30
```

Também vimos que podemos acrescentar a separação de milhar utilizando vírgula (`,`), acrescentando ela logo após os `:`, ficando: `:,.2f`

```python
print(f'{1000.29838423822:,.2f}') # Saída: 1,000.30
```

Um outro sinal que a gente ainda não viu, é o `+`, que sempre mostra o sinal do número `+` para positivos e `-` para negativos.

```python
numero = 1000.30
print(f'{numero:+,.2f}') # +1,000.30
```

Agora, utilizando o `-` ao invés do `+`, ele **não** é o contrário do `+`. Ele na verdade não faz nada e é ignorado, como se você tivesse digitado sem nenhum caractere de preenchimento ou controlador de sinal, veja o exemplo abaixo:

```python
# Como se você tivesse digitado assim:
print(f'{numero:,.2f}')
```

### Diferença de controlador de sinal para caractere de preenchimento e estrutura

Só existem apenas 3 controladores de sinais válidos em `f-strings`:

| Sinal            | Resultado p/ positivo  | Resultado p/ negativo |
| ---------------- | ---------------------- | --------------------- |
| `+`              | Mostra `+`             | Mostra `-`            |
| espaço vazio ( ) | Mostra um espaço vazio | Mostra `-`            |
| **nada**         | Não mostra nada        | Mostra `-`            |

Agora os caracteres de preenchimento, ou fill character, têm que ter exatamente 1 caractere e devem ir antes do alinhamento. Caractere de preenchimento são caracteres, `*`, `$`, `=`, etc...

Essa é a estrutura geral de uma formatação:

```
{valor:[fill][align][sign][#][0][width][,][.precision][type]}
```

* `fill` → caractere de preenchimento (como `*`, `0`, `=`, etc.)
* `align` → alinhamento (`<`, `>`, `^`, `=`)
* `sign` → controlador de sinal (`+`, espaço, ou nada)
* `width` → largura mínima
* `type` → tipo (como `f` para float, `d` para decimal, `s` para string, etc.)

```python
f'{numero:*<+020,.2f}'
```

| Parte | Função                                                                           |
| ----- | -------------------------------------------------------------------------------- |
| `*`   | **caractere de preenchimento** (`fill`)                                          |
| `<`   | **alinhamento** à esquerda (`align`)                                             |
| `+`   | **controlador de sinal** (exibe `+` para positivos, `-` para negativos)          |
| `0`   | **indica preenchimento com zeros** → **mas só funciona se `fill` não for usado** |
| `20`  | **largura mínima** de 20 caracteres                                              |
| `,`   | **separador de milhar** (usa vírgula para separar mil, milhão, etc.)             |
| `.2f` | **2 casas decimais**, tipo `float`                                               |
