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
Esto porque est� configurado en ambiente 'Development'

Si no est� activo s�lo funcionar�: http://localhost:8085/WeatherForecast

La imagen ya est� en Docker Hub, para llamar sin c�digo es el siguiente comando:
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
En ese instante mostrar� al final una URL (en Windows), algo as� como:
```
http://127.0.0.1:64737
```
En este caso 64737 podr�a variar, as� que solo ser� <puerto>
As� para probar en el navegador debe abrir las siguientes URL:
```
http://127.0.0.1:<puerto>/swagger/index.html
http://127.0.0.1:<puerto>/WeatherForecast
```