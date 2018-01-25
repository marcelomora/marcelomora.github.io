---
layout: post
title: Cifrado César con Python
author: Marcelo Mora
---

En esta entrada del blog vamos a ver un poco de criptografía y algunos fundamentos de Python

## Cifrado César con Python 
-----

El cifrado César es un tipo de encriptación que utiliza como método el modificar la posición de un símbolo o caracter a otro basado en un número entero denominado llave.

Una forma de cifrar y descifrar un mensaje sería utilizando una [rueda de cifado]({{https://inventwithpython.com/cipherwheel/}}) para encontrar las equivalencias entre el símbolo original y el cifrado.

Vamos a implementar el cifrado César en Python
La posición la señalaríamos con la siguiente cadena de caracteres.
```python
simbolos = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
```

La siguiente instrucción nos permitiría cifrar el mensaje.
```python
encriptado = "".join(map(lambda x: simbolos.find(x) >= 0 and (simbolos.find(x) > 13 and simbolos[simbolos.find(x) - 13]  or simbolos[simbolos.find(x) + 13]) or x, mensaje)) 
```

Esta instrucción va a permitir descifrar el mensaje.
```python
mensaje = "".join(map(lambda x: simbolos.find(x) >= 0 and (simbolos.find(x) >= 13 and simbolos[simbolos.find(x) - 13]  or simbolos[simbolos.find(x) + 13]) or x, encriptado))
```


