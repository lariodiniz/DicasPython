# Dicas Python

1 - Strings ignorando barra de escape.
---

Adicione a letra `r` antes da primeira aspas, ou aspas duplas, da string para ela tratar a `/` como um caracter normal.

### Exemplo:

a seguinte linha de comando

```python
numeros = '1234\5'
print(numeros)
```

mostrará:
```
1234
```

a seguinte linha de comando

```python
numeros = r'1234\5'
print(numeros)
```

mostrará:
```
1234\5
```

2 - Atribuição Multipla
---

Você pode adicionar informações em multiplas variaveis ao mesmo tempo, na mesma linha.

### Exemplo:

a seguinte linha de comando

```python
var1, var2, var3 = 'span', 42, 'Caerbannog'

print(var1)
print(var2)
print(var3)
```

mostrará:
```
span
42
Caerbannog
```

3 - Laço em dicionario com chave e valor.
---

Quando precisar fazer um laço em um dicionario que você utilizará a chave e o valor, use o método `items()` do prório dicionario.

### Exemplo:

a seguinte linha de comando

```python
dicionario = {'gallahad': 'the pure', 'robin': 'the brave'}

for key, valor in dicionario.items():
	print(f'{key} - {valor}')
```

mostrará:
```
gallahad - the pure
robin - the brave
```

4 - Laço em lista com index e valor.
---

Quando precisar fazer um laço em uma lista que você utilizará o index da lista e o valor, use o `enumerate()`

### Exemplo:

a seguinte linha de comando

```python
lista = ['Graham Chapman', 'Michael Palin', 'Eric Idle']

for index, valor in enumerate(lista):
	print(f'{index} - {valor}')
```

mostrará:
```
0 - Graham Chapman
1 - Michael Palin
2 - Eric Idle
```

5 - Somar todos os valores numericos contidos em uma lista
---

Quando precisar somar todos os valores numericos em uma lista, use o `sum()`

### Exemplo:

a seguinte linha de comando

```python
lista = [3,7.3,8,4,6.8,4,2.2]

print(sum(lista))
```

mostrará:
```
35.300000000000004
```

6 - Ordenar uma lista
---

Quando precisar ordenar uma lista, use o método `sort()` da própria lista

### Exemplo:

a seguinte linha de comando

```python
lista = [3,7.3,8,4,6.8,4,2.2]

lista.sort()

print(lista)
```

mostrará:
```
[2.2, 3, 4, 4, 6.8, 7.3, 8]
```

7 - Criando listas com laço for e if de outras listas
---

você pode criar listas com clausula if de outras listas colocando o for e o if dentro de colchetes.

### Exemplo 1:

a seguinte linha de comando

```python
numeros = [1, 3, 5, 4, 9, 6, 12, 35, 47, 6312]
par = [n for n in numeros if n % 2 == 0] 

print(par)
```

mostrará:
```
[4, 6, 12, 6312]
```

### Exemplo 2:

Você pode usar o laço for para aplicar uma função a cada item da lista.

```python
def soma2(numero):
	return numero + 2

numeros = [1, 3, 5, 4, 9, 6, 12, 35, 47, 6312]
numeros2 = [soma2(n) for n in numeros if n % 2 == 0]
numeros3 = list(map(lambda x: x+2, numeros)) 

print(numeros2)
print(numeros3)
```

mostrará:
```
[6, 8, 14, 6314]
[3, 5, 7, 6, 11, 8, 14, 37, 49, 6314]
```

8 - Percorrendo duas listas ao mesmo tempo
---

caso você queira alinhar duas listas diferentes para percorrelas ao mesmo tempo você pode usar o `zip`.

### Exemplo:

a seguinte linha de comando

```python
pergunta = ['Qual o seu nome?', 'Qual a sua missão?', 'qual sua cor favorita?']
resposta = ['Lancelot', 'Encontrar o santo Graal', 'Azul']

for p, r in zip(pergunta, resposta): 
    print(f'Homem da ponte: - {p}')
    print(f'Lancelot: - {r}')
else:
    print('Homem da ponte: - Ok pode passar...')
```

mostrará:
```
Homem da ponte: - Qual o seu nome?
Lancelot: - Lancelot
Homem da ponte: - Qual a sua missão?
Lancelot: - Encontrar o santo Graal
Homem da ponte: - qual sua cor favorita?
Lancelot: - Azul
Homem da ponte: - Ok pode passar...
```

9 - Argumentos via linha de comando.
---

Para passar argumentos para um script python você lê o atributo argv (uma lista) do modulo sys.

-  _**Nota:** Essa lista tem sempre ao menos um elemento; quando nenhum script ou argumento for passado para o interpretador, sys.argv[0] será uma string vazia. Quando o nome do script for '-' (significando entrada padrão), o conteúdo de sys.argv[0] será '-'. Quando for utilizado -c comando, sys.argv[0] conterá '-c'. Quando for utilizado -m módulo, sys.argv[0] conterá o caminho completo do módulo localizado. Opções especificadas após -c comando ou -m módulo não serão consumidas pelo interpretador mas deixadas em sys.argv._

### Exemplo:
> um script chamado exemplo.py com as sequintes linhas

```python
import sys

argumentos = sys.argv

for cont, arg in enumerate(argumentos):
	print(f'Argumento {cont}: {arg}')
```
ao ser chamado na linha de comando dessa maneira:
```
python exemplo01.py
```

mostrará:
```
Argumento 0: exemplo01.py
```
ao ser chamado na linha de comando dessa maneira:
```
python exemplo01.py argumento1 argumento2
```

mostrará:
```
Argumento 0: exemplo01.py
Argumento 1: argumento1
Argumento 2: argumento2
```
ao ser chamado na linha de comando dessa maneira:
```
python exemplo01.py argumento1 argumento2 'Graham Chapman' 'Michael Palin'
```

mostrará:
```
Argumento 0: exemplo01.py
Argumento 1: argumento1
Argumento 2: argumento2
Argumento 3: 'Graham
Argumento 4: Chapman'
Argumento 5: 'Michael
Argumento 6: Palin'
```

10 - Blocos for e while aceitam um bloco else
---

laços podem ter uma cláusula else; que é executada sempre que o laço se encerra, mas nunca quando o laço é interrompido por um break.

### Exemplo:

a seguinte linha de comando

```python
lista = ['Graham Chapman', 'Michael Palin', 'Eric Idle']

for item in lista:
	print(item)
else:
	print('Quando terminou o laço')
```

mostrará:
```
Graham Chapman
Michael Palin
Eric Idle
Quando terminou o laço
```
a seguinte linha de comando

```python
lista = ['Graham Chapman', 'Michael Palin', 'Eric Idle']

for item in lista:
	print(item)
	if item == 'Eric Idle':
		break
else:
	print('Quando terminou o laço')
```

mostrará:
```
Graham Chapman
Michael Palin
Eric Idle
```

11 - Exemplos de Doc String
---


### Exemplo função:


```python
def funcao(parametro1:int, parametro2:str, parametro3:float, parametro4:list):
	"""[DESCRIÇÂO RESUMIDA DA FUNÇÂO]

	[DESCRIÇÃO MAIS APROFUNDADA DA FUNÇÃO]

	Arguments:
		parametro1 {int} -- [DESCRIÇÃO DO PARAMETRO]
		parametro2 {str} -- [DESCRIÇÃO DO PARAMETRO]
		parametro3 {float} -- [DESCRIÇÃO DO PARAMETRO]
		parametro4 {list} -- [DESCRIÇÃO DO PARAMETRO]

	Returns:
		[type] -- [DESCRIÇÃO DO RETORNO]
	"""
```

### Exemplo classe:

```python
class Classe:
	"""[DESCRIÇÂO RESUMIDA DA CLASSE]
	
	Args:
		argumento1 {int} -- [description]
		argumento2 {list} -- [description]

	Attributes:
		atributo1 {int} -- [description]
		atributo2 {list} -- [description]
	"""

	def __init__(self, argumento1: int, argumento2:list):
		self.atributo1 = argumento1
		self._argumento2 = argumento2

	@property
	def atributo2(self):
		return self._argumento2

	def metodo_com_retorno(self):
		"""[DESCRIÇÂO RESUMIDA DO METODO]

		[DESCRIÇÂO DO METODO]

		Returns:
			[type] -- [description]
		"""

		return self._argumento1

	def metodo_sem_retorno(self, argumento1:str):
		"""[DESCRIÇÂO RESUMIDA DO METODO]

		[DESCRIÇÂO DO METODO]

		Arguments:
			argumento1 {str} -- [description]
		"""
		pass

```

12 - Lendo arquivo da forma correta
---

Use a palavra-chave `with`  para leitura e escrita de arquivos, assim o arquivo é fechado corretamente após o término de sua utilização, mesmo que uma exceção seja levantada em algum momento.

### Exemplo:

a seguinte linha de comando

```python
with open('texto.txt', 'r') as f:
	read_data = f.read()
```

13 - Ao trabalhar com dinheiro use Decimal
---

O módulo `decimal` oferece o tipo `Decimal` para aritmética decimal com ponto flutuante e reproduz a aritmética como fazemos à mão.

### Exemplo:

a seguinte linha de comando

```python
from decimal import Decimal
```

14 - Fazendo uma classe se comportar como uma lsita
---

Para uma classe se comportar como uma lista você precisa definir os médodos especiais `__getitem__` e `__setitem__`

### Exemplo:

```python
class Fila:
	def __init__(self, *args):
		#setar um atributo com underline é o 
		#padrão para os clientes da sua classe 
		#não utilizarem esse atributo
		self._itens = list(args)


	#adiciona o comportamento de slice e for
	def __getitem__(self, pos):
			return self._itens[pos]

	#adiciona o comportamento de setar item
	def __setitem__(self, pos, val):
		self._itens[pos] = val

	#define como sua classe será imprimida
	def __repr__(self):
		return f'{self._itens}'
```