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

# 1.4 lista de de modelos 

```` bash
  ollama list
````  
# 1.5 ejeucutar modelo en por terminal modo solo respuesta

``` bash
$ollama run gemma:2b ¿por qué el cielo es azúl?
```
# 1.6  modo chat desde la terminal 

``` bash 
$ollama run gemma:2b
```


# hacer petecion mediante curl en terminal

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


despues de esto podemo hacer http dede cualquier servicon de codigo implementado los diferetes modelo y formas de usar el servicio de ollama con los lenguajes naturales.