# illm_dfernafa

Repositorio para inteligencia artufiacial

# LLM

Repositorio de prueba de modelos de lenguaje largo usandao ollama

# 1.instalacion

como primer parte instalar ollama para la maquina de ubunto con el comando [ollama](https://ollama.com/download/linux) de ejemplo

````bash
 $ curl -fsSL https://ollama.com/install.sh | sh
````

# 1.2 Para crear levantar ollama se pone el comado  

dejamos el servidor activo y abrimos otra terminal

```` bash
$ ollama  server
````

# 1.3 Descagar un modelo

se descaga el modelo con ayuda de  [ollama libreria](https://ollama.com/library)

````bash
$ ollama pull gemma:2b
````

# 1.4 lista de de modelos 

```` bash
$ ollama list
````  
curl http://localhost:11434/api/generate -d '{
  "model": "tinyllama",
  "prompt":"¿por qué el cielo es azúl?"
}'

curl -X  POST  http://localhost:11434/api/generate -d '{
  "model": "tinyllama",
  "prompt":"¿por qué el cielo es azúl?",
  "stream":false
}' -O salida2.JSON