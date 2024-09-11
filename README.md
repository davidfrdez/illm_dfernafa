# illm_dfernafa

Repositorio para inteligencia artufiacial

# LLM

Repositorio de prueba de modelos de lenguaje largo usandao ollama

# 1.1 Instalación en GNU Linux

como primer parte instalar ollama para la maquina de ubunto con el comando [ollama](https://ollama.com/download/linux) de ejemplo

````bash
 $curl -fsSL https://ollama.com/install.sh | sh
````

# 1.2 Para crear levantar ollama se pone el comado  

dejamos el servidor activo y abrimos otra terminal

```` bash
  $ollama  server
````

# 1.3 Descagar un modelo

se descaga el modelo con ayuda de  [ollama libreria](https://ollama.com/library)

````bash
 ollama pull gemma:2b
````

# 1.4 Listar modelos disponibles:

```` bash
  ollama list
````  
# 1.5 ejeucutar modelo en por terminal modo solo respuesta

``` bash
$ollama run gemma:2b ¿por qué el cielo es azúl?
```
# 1.6  Ejecutar un modelo en modo chat:

``` bash 
$ollama run gemma:2b
```


# Hacer una petición HTTP (ejemplo):

```` bash
curl http://localhost:11434/api/generate -d '{
  "model": "tinyllama",
  "prompt":"¿por qué el cielo es azúl?"
}'
````  

salida de modo json para ver la informacion impresa en archivo json
```` bash
curl -X  POST  http://localhost:11434/api/generate -d '{
  "model": "tinyllama",
  "prompt":"¿por qué el cielo es azúl?",
  "stream":false
}' -O salida2.JSON
````  

# Python Para consumo
A partir de aquí, podemos crear servicios personalizados en cualquier lenguaje de programación para interactuar con la API de Llama y aprovechar al máximo las capacidades de los modelos de lenguaje natural.
## 1 Instalar la librería requests:
Esta librería es fundamental para hacer peticiones HTTP en Python. Puedes instalarla usando pip:


```` bash
pip install requests
````

## 1.1 Importar la librería:

``` Python
import requests
```

## 1.2 Definir la URL y los datos de la petición:
La URL será la dirección de tu servidor Llama. Los datos de la petición incluirán el modelo que deseas utilizar, el prompt (la pregunta o solicitud) y otros parámetros opcionales.
``` Python
url = "http://localhost:11434/api/generate"  # Ajusta la URL si tu servidor está en otro puerto
datos = {
    "model": "tinyllama",
    "prompt": "¿Cuál es la capital de Francia?"
}
```
## 1.3 Realizar la petición POST:
Utilizamos el método **post()** de la librería requests para enviar la petición al servidor:
``` Python
respuesta = requests.post(url, json=datos)
```
## 1.4 Procesar la respuesta:
La respuesta del servidor generalmente es un objeto JSON. Puedes acceder al contenido de la respuesta de la siguiente manera:

``` Python
if respuesta.status_code == 200:
    resultado = respuesta.json()
    print(resultado)
else:
    print("Error:", respuesta.text)
```
### Ejemplo completo

``` Python
import requests

url = "http://localhost:11434/api/generate"
datos = {
    "model": "tinyllama",
    "prompt": "¿Cuál es la capital de Francia?"
}

respuesta = requests.post(url, json=datos)

if respuesta.status_code == 200:
    resultado = respuesta.json()
    print(resultado['choices'][0]['text'].strip())
else:
    print("Error:", respuesta.text)
```