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

mostrarar:
```
1234
```

a seguinte linha de comando

```python
numeros = r'1234\5'
print(numeros)
```

mostrarar:
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

mostrarar:
```
span
42
Caerbannog
```


3 - Laço em lista com index e valor.
---

Quando precisar fazer um laço em uma lista que você utilizará o index da lista e o valor, use o `enumerate()`

### Exemplo:

a seguinte linha de comando

```python
numeros = '1234\5'
print(numeros)
```

mostrarar:
```
1234
```

a seguinte linha de comando

```python
lista = ['Graham Chapman', 'Michael Palin', 'Eric Idle']

for index, valor in enumerate(lista):
	print(f'{index} - {valor}')
```

mostrarar:
```
0 - Graham Chapman
1 - Michael Palin
2 - Eric Idle
```

4 - Somar todos os valores numericos contidos em uma lista
---

Quando precisar somar todos os valores numericos em uma lista, use o `sum()`

### Exemplo:

a seguinte linha de comando

```python
lista = [3,7.3,8,4,6.8,4,2.2]

print(sum(lista))
```

mostrarar:
```
35.300000000000004
```

5 - Argumentos via linha de comando.
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
mostrarar:
```
Argumento 0: exemplo01.py
```
ao ser chamado na linha de comando dessa maneira:
```
python exemplo01.py argumento1 argumento2
```
mostrarar:
```
Argumento 0: exemplo01.py
Argumento 1: argumento1
Argumento 2: argumento2
```
ao ser chamado na linha de comando dessa maneira:
```
python exemplo01.py argumento1 argumento2 'Graham Chapman' 'Michael Palin'
```
mostrarar:
```
Argumento 0: exemplo01.py
Argumento 1: argumento1
Argumento 2: argumento2
Argumento 3: 'Graham
Argumento 4: Chapman'
Argumento 5: 'Michael
Argumento 6: Palin'
```


