🗓️ Data: 09/10/2025

`while` significa **enquanto**. O bloco de código do `while` será executado **ENQUANTO** aquela condição for verdadeira.

```python
condicao = True
while condicao:
	print(1)
	print(2)
	print(3)
```

O código acima vai gerar um loop infinito, pois a variável `condicao` está com o valor `True`, o que automaticamente faz com que `while condicao` seja sempre `True`. Ou seja, ele ficará **REPETINDO** o bloco de código, executando os 3 prints infinitamente **ENQUANTO** a condição for verdadeira.

---

O processo de execução é simples. Como vimos, ele executa o bloco do `while` **ENQUANTO** a condição for verdadeira.

* A variável `condicao` tem o valor `True`.
* Consequentemente, `while condicao:` será sempre verdadeiro.
* Executará o bloco de código que contém os 3 prints.
* Depois, ele **VOLTARÁ** novamente para `while condicao:`, verificando se a condição é verdadeira ou não.
* O que irá resultar em uma nova execução dos prints. E isso fica se repetindo infinitamente, pois **NÃO** existe nada tornando a variável da condição em `False`.
* Condição verdadeira → Executa o bloco → Volta e verifica se ainda é verdadeiro. Se for → Executa o bloco → Volta novamente e verifica se ainda é verdadeiro. Se for → Executa o bloco → E assim infinitamente **ENQUANTO** a condição for verdadeira.

---

```python
condicao = True

while condicao:
	nome = input('Qual o seu nome: ')
	print(f'Seu nome é {nome}')
	
	if nome == 'sair':
		break
```

Já no código acima, estamos utilizando algo para **FORÇAR** a quebra de repetição, que é utilizando o `break`.

Veja que, ainda sim, a condição do `while` continua sempre sendo verdadeira, resultando sempre com o código perguntando o nome e exibindo o nome com `f-String`. Porém, existe uma condição `if`: SE o usuário digitar "sair", a condição do if será verdadeira e irá executar o `break`.

O `break`, **dentro de um laço**, irá SEMPRE procurar o laço de repetição mais próximo dele.

---
