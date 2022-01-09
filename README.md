# democore6api
Api en NET Core demo para despliegue.

## Para iniciar con Docker la demo, lo siguiente:

### Construir imagen:
```
docker build -t democore6api .  
```
### Correr contenedor de la imagen:
```
docker run -d -p 8085:80 --name demoapi -e ASPNETCORE_ENVIRONMENT='Development'  democore6api
```
Luego abrir http://localhost:8085/swagger/index.html (puerto 8085).
Esto porque está configurado en ambiente 'Development'

Si no está activo sólo funcionará: http://localhost:8085/WeatherForecast

La imagen ya está en Docker Hub, para llamar sin código es el siguiente comando:
```
docker run -d -p 8085:80 --name demoapi -e ASPNETCORE_ENVIRONMENT='Development'  mperedo/democore6api
```
## Levantar con minikube en Windows

```
kubectl apply -f deployment.yml
kubectl apply -f service.yml
```
Luego para levantar en Windows ->
```
minikube service demokubeapi
```
En ese instante mostrará al final una URL (en Windows), algo así como:
```
http://127.0.0.1:64737
```
En este caso 64737 podría variar, así que solo será **puerto**
Así para probar en el navegador debe abrir las siguientes URL:
```
http://127.0.0.1:**puerto**/swagger/index.html
http://127.0.0.1:**puerto**/WeatherForecast
```

## Pipeline

Se prueban ejecución webhooks hacia el local.
Prueba 1.
Prueba 2.
Prueba 3
