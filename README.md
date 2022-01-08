# democore6api
Api en NET Core demo para despliegue.

## Para iniciar con Docker la demo, lo siguiente:

### Construir imagen:

...
docker build -t democore6api .  
...

### Correr contenedor de la imagen:

...
docker run -d -p 8085:80 --name demoapi -e ASPNETCORE_ENVIRONMENT='Development'  democore6api
...

Luego abrir http://localhost:8085/swagger/index.html (puerto 8085).
Esto porque está configurado en ambiente 'Development'

Si no está activo sólo funcionará: http://localhost:8085/WeatherForecast

