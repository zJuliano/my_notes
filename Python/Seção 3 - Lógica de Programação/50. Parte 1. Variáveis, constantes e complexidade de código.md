🗓️ Data: 27/09/2025
## Variáveis constantes

É uma variável com valor fixo, uma variável que **nunca** vai mudar. No JavaScript, existe uma declaração `const`, que não permite alterar o valor da variável. Mas no Python, isso não existe.

Então, quando você quiser criar uma variável **constante** que não terá o seu valor alterado, você cria uma variável com letras maiúsculas, que irá indicar que aquela variável é uma constante.

```python
RADAR_1 = 60 # Velocidade máxima do radar 1
LOCAL_1 = 100 # Local onde o radar 1 está
RADAR_RANGE = 1 # A distância onde o radar pega
```
## Muitas condições no mesmo if (ruim)

Quanto mais condições você tiver dentro de um `if`, mais complexo fica seu código. Vai começar a ficar difícil entender se vai ou não entrar naquele fluxo de código.

## Clean Code

Quando trabalhamos na área e escrevemos código, não estamos escrevendo só para nós mesmos, mas para **as pessoas da nossa equipe**. Por isso, um código complexo deve ser evitado, e um código limpo deve ser priorizado, para que outras pessoas entendam com mais facilidade.

---

### Código complexo

#### Variáveis

```python
velocidade = 61 # Velocidade atual do carro
local_carro = 101 # Local que o carro está na estrada

RADAR_1 = 60 # Velocidade máxima do radar 1
LOCAL_1 = 100 # Local onde o radar 1 está
RADAR_RANGE = 1 # A distância onde o radar pega
```

#### Código Principal

```python
if local_carro >= (LOCAL_1 - RADAR_RANGE) and local_carro <= (LOCAL_1 + RADAR_RANGE) and velocidade > RADAR_1:
    print("Multado!")
else:
    print("Não está multado!")
```

O `if` acima está fazendo o seguinte: se as 3 condições com operadores `and` retornarem `True`, irá imprimir "Multado".

* Se o local do carro estiver entre `99` e `101` e a velocidade do carro `61` for maior que a velocidade máxima que é `60`.
* Imprima "Multado"
#### Por que é complexo?

Só de alguém olhar esse código, até mesmo se tiver experiência, vai ter que pensar um pouco e entender o que está fazendo. Agora abaixo vai um código um pouco Clean Code.

#### Mesmo código, só que um pouco Clean Code

```python
velocidade_maior_que_o_limite = velocidade > RADAR_1

carro_passou_radar_1 = local_carro >= (LOCAL_1 - RADAR_RANGE) and local_carro <= (LOCAL_1 + RADAR_RANGE)

if carro_passou_radar_1 and velocidade_maior_que_o_limite:
    print("Multado!")
else:
    print("Não está multado!")
```

Agora, veja que a condição do `if` está falando: "se o carro passou no radar 1 **E** a velocidade do carro for maior que o limite, imprima 'Multado' na tela". Diferente do que você vê na condição longa.

Apesar das condições estarem dentro das variáveis, ainda sim daria para deixar elas mais clean code também, mas isso envolve o uso de funções, que ainda não vimos, deixando super limpo e autoexplicativo