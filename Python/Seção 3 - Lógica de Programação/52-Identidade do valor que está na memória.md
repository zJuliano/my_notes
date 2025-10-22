🗓️ Data: 06/10/2025

Quando declaramos uma variável, estamos dando um apelido (ou referência) para um **objeto** (valor) que está na memória.

Mas quando esse objeto está na memória, o Python precisa saber como localizar. Cada **objeto** possui um **identificador único**, e é possível obter esse identificador com a função `id()`.

Veja o exemplo abaixo:

```python
nome = "Julaino"
print(id(nome))  # Saída: 140151488951520 (exemplo de identificador do objeto)
```

---

* Variáveis são apenas **nomes** que apontam para objetos.
* `id()` retorna o identificador do **objeto**, não da variável.
* Esse ID representa a **posição na memória** (ou algo próximo disso, dependendo da implementação).i
