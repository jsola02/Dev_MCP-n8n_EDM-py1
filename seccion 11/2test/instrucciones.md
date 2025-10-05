<div align="center">
  <img src="https://ollama.com/public/gpt-oss.png"  width="300px" />
  </div>
  
  

## Instrucciones para descargar Ollama

- Descargar Ollama client
https://ollama.com/



## Descargar modelos
https://ollama.com/search

Ejemplo para [descargar](https://ollama.com/library/gpt-oss) `gpt-oss:20b`
```bash
ollama pull gpt-oss
```

## Probar 
* Probar localmente en la terminal
```bash
ollama run gpt-oss
```

### Mediante Postman
1- Realizar una petición POST a: localhost:11434/api/generate
2- Enviar este body:
```json
{
    "model":"gpt-oss:20b",
    "prompt": "Hola, que tal estás?",
    "stream": false
}
```

## Servir Ollama a la red
```
ollama serve
```
En caso de que no se logre conectar:
```bash
OLLAMA_HOST=0.0.0.0:11434 ollama serve
```




# Docker
Descargar la imagen de Ollama
https://hub.docker.com/r/ollama/ollama

```
docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama
```
### Importante
Tenga en cuenta que, dependiendo del modelo a ejecutar, será necesario asignar mayor espacio en memoria para obtener respuestas en tiempos razonables.


* Confirmar modelos instalados vía Docker
```curl
curl http://<TU_HOST>:11434/api/tags
```
* Instalar los modelos que necesites
```
OLLAMA_HOST=<TU_HOST>:11434 ollama pull gpt-oss
```



